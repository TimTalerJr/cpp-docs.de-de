---
title: 2. Anweisungen
ms.date: 01/18/2019
ms.assetid: d1a69374-6c03-45fb-8c86-e91cea8adae8
ms.openlocfilehash: 125d2d83b277e62d007e3a208e426ea717d52790
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424194"
---
# <a name="2-directives"></a>2. Direktiven

Direktiven basieren auf `#pragma` Direktiven, die in den C++ C-und-Standards definiert sind.  Compiler, die OpenMP C und C++ API unterstützen, enthalten eine Befehlszeilenoption, die aktiviert und die Interpretation aller OpenMP-Compilerdirektiven ermöglicht.

## <a name="21-directive-format"></a>2,1 direktivenformat

Die Syntax einer OpenMP-Direktive wird formal von der Grammatik in [Anhang C](c-openmp-c-and-cpp-grammar.md)und informell wie folgt angegeben:

```cpp
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

Jede Direktive beginnt mit `#pragma omp`, um das potenzielle Auftreten von Konflikten mit anderen (nicht-OpenMP-oder Lieferanten Erweiterungen von OpenMP) Pragma-Direktiven mit denselben Namen zu reduzieren. Der Rest der Direktive befolgt die Konventionen der C-und C++ Standards für Compilerdirektiven. Insbesondere kann Leerraum vor und nach dem `#`verwendet werden. manchmal müssen Leerräume verwendet werden, um die Wörter in einer-Direktive voneinander zu trennen. Vorverarbeitungs Token, die auf die `#pragma omp` folgen, unterliegen dem Makro Austausch.

Bei Anweisungen wird die Groß-/Kleinschreibung beachtet Die Reihenfolge, in der Klauseln in Direktiven vorkommen, ist nicht signifikant. Klauseln für Direktiven können bei Bedarf wiederholt werden, je nach den Einschränkungen, die in der Beschreibung der einzelnen Klauseln aufgeführt sind. Wenn " *Variable-list* " in einer-Klausel angezeigt wird, müssen nur Variablen angegeben werden. Pro Direktive kann nur ein *Direktivenname* angegeben werden.  Beispielsweise ist die folgende Anweisung nicht zulässig:

```cpp
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

Eine OpenMP-Direktive gilt für höchstens eine nachfolgende Anweisung, bei der es sich um einen strukturierten Block handeln muss.

## <a name="22-conditional-compilation"></a>2,2 bedingte Kompilierung

Der `_OPENMP` Makro Name wird durch OpenMP-kompatible Implementierungen als Dezimal Konstante *yyyymm*definiert, die das Jahr und den Monat der genehmigten Spezifikation ist. Dieses Makro darf nicht der Betreff eines `#define` oder einer `#undef` Vorverarbeitungs Direktive sein.

```cpp
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Wenn Anbieter Erweiterungen für OpenMP definieren, können Sie zusätzliche vordefinierte Makros angeben.

## <a name="23-parallel-construct"></a>2,3 paralleles Konstrukt

Die folgende Anweisung definiert einen parallelen Bereich, bei dem es sich um einen Bereich des Programms handelt, der von vielen Threads parallel ausgeführt werden soll. Diese Direktive ist das grundlegende Konstrukt, das die parallele Ausführung startet.

```cpp
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block
```

Die- *Klausel* ist einer der folgenden:

- `if(` *skalaren Ausdrucks* `)`
- `private(` `)` der *Variablen Liste*
- `firstprivate(` `)` der *Variablen Liste*
- `default(shared | none)`
- `shared(` `)` der *Variablen Liste*
- `copyin(` `)` der *Variablen Liste*
- `reduction(` *Operator* `:`*Variable-list* `)`
- `num_threads(` *ganzzahlige Ausdrucks* `)`

Wenn ein Thread zu einem parallelen Konstrukt gelangt, wird ein Thread Team erstellt, wenn einer der folgenden Fälle zutrifft:

- Es ist keine `if`-Klausel vorhanden.
- Der `if` Ausdruck ergibt einen Wert ungleich 0 (null).

Dieser Thread wird zum Master Thread des Teams mit der Thread Nummer 0, und alle Threads im Team, einschließlich des Master Threads, führen die Region parallel aus. Wenn der Wert des `if` Ausdrucks NULL ist, wird der Bereich serialisiert.

Um die Anzahl der angeforderten Threads zu bestimmen, werden die folgenden Regeln in der richtigen Reihenfolge berücksichtigt. Die erste Regel, deren Bedingung erfüllt ist, wird angewendet:

1. Wenn die `num_threads`-Klausel vorhanden ist, entspricht der Wert des ganzzahligen Ausdrucks der Anzahl der angeforderten Threads.

1. Wenn die `omp_set_num_threads` Bibliotheksfunktion aufgerufen wurde, ist der Wert des Arguments im zuletzt ausgeführten Aufruf die Anzahl der angeforderten Threads.

1. Wenn die Umgebungsvariable `OMP_NUM_THREADS` definiert ist, ist der Wert dieser Umgebungsvariablen die Anzahl der angeforderten Threads.

1. Wenn keine der oben genannten Methoden verwendet wird, wird die Anzahl der angeforderten Threads von der Implementierung definiert.

Wenn die `num_threads`-Klausel vorhanden ist, ersetzt Sie die Anzahl der Threads, die von der `omp_set_num_threads` Bibliotheksfunktion angefordert werden, oder die `OMP_NUM_THREADS` Umgebungsvariable nur für den parallelen Bereich, auf den Sie angewendet wird. Spätere parallele Bereiche sind davon nicht betroffen.

Die Anzahl der Threads, die den parallelen Bereich ausführen, hängt auch davon ab, ob die dynamische Anpassung der Thread Anzahl aktiviert ist. Wenn die dynamische Anpassung deaktiviert ist, wird der parallele Bereich durch die angeforderte Anzahl von Threads ausgeführt. Wenn die dynamische Anpassung aktiviert ist, ist die angeforderte Anzahl von Threads die maximale Anzahl von Threads, die den parallelen Bereich ausführen können.

Wenn ein paralleler Bereich festgestellt wird, während die dynamische Anpassung der Thread Anzahl deaktiviert ist, und die Anzahl der für den parallelen Bereich angeforderten Threads größer ist als die Anzahl, die das Laufzeitsystem bereitstellen kann, ist das Programmverhalten. Implementierungs definiert. Eine Implementierung kann z. b. die Ausführung des Programms unterbrechen, oder der parallele Bereich kann serialisiert werden.

Die `omp_set_dynamic` Bibliotheksfunktion und die `OMP_DYNAMIC`-Umgebungsvariable können verwendet werden, um die dynamische Anpassung der Anzahl von Threads zu aktivieren und zu deaktivieren.

Die Anzahl der physischen Prozessoren, die die Threads tatsächlich zu einem bestimmten Zeitpunkt gehostet haben, ist von der Implementierung definiert. Nach der Erstellung bleibt die Anzahl der Threads im Team für die Dauer dieses parallelen Bereichs konstant. Sie kann entweder explizit vom Benutzer oder automatisch vom Laufzeitsystem von einem parallelen Bereich in einen anderen geändert werden.

Die Anweisungen innerhalb des dynamischen Bereichs des parallelen Bereichs werden von jedem Thread ausgeführt, und jeder Thread kann einen Pfad von Anweisungen ausführen, die sich von den anderen Threads unterscheiden. Direktiven, die außerhalb des lexikalischen Umfangs eines parallelen Bereichs auftreten, werden als verwaiste Direktiven bezeichnet.

Am Ende eines parallelen Bereichs gibt es eine implizite Barriere. Nur der Master Thread des Teams setzt die Ausführung am Ende eines parallelen Bereichs fort.

Wenn ein Thread in einem Team, der einen parallelen Bereich ausführt, ein anderes paralleles Konstrukt findet, erstellt es ein neues Team und wird zum Master dieses neuen Teams. Die in der Standardeinstellung ausgefallenen parallelen Bereiche werden serialisiert. Daher wird standardmäßig ein geschsted paralleler Bereich von einem Team ausgeführt, das aus einem Thread besteht. Das Standardverhalten kann geändert werden, indem entweder die Lauf Zeit Bibliotheksfunktion `omp_set_nested` oder die Umgebungsvariable `OMP_NESTED`verwendet wird. Die Anzahl der Threads in einem Team, die einen genetzten parallelen Bereich ausführen, ist jedoch Implementierungs definiert.

Einschränkungen für die `parallel`-Direktive lauten wie folgt:

- Höchstens eine `if`-Klausel kann in der Direktive angezeigt werden.

- Es ist nicht angegeben, ob Nebeneffekte innerhalb des if-Ausdrucks oder `num_threads` Ausdrucks auftreten.

- Eine `throw`, die in einem parallelen Bereich ausgeführt wird, muss bewirken, dass die Ausführung innerhalb des dynamischen Umfangs desselben strukturierten Blocks fortgesetzt wird, und Sie muss durch denselben Thread abgefangen werden, der die Ausnahme ausgelöst hat.

- Nur eine einzige `num_threads`-Klausel kann in der Direktive angezeigt werden. Der `num_threads` Ausdruck wird außerhalb des Kontexts des parallelen Bereichs ausgewertet und muss zu einem positiven ganzzahligen Wert ausgewertet werden.

- Die Reihenfolge der Auswertung der `if` und `num_threads` Klauseln ist nicht angegeben.

### <a name="cross-references"></a>Querverweise

- `private`, `firstprivate`, `default`, `shared`, `copyin`und `reduction` Klauseln ([Abschnitt 2.7.2](#272-data-sharing-attribute-clauses))
- Umgebungsvariable [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) Bibliotheksfunktion
- Umgebungsvariable [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)
- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) -Funktion
- Umgebungsvariable [OMP_NESTED](4-environment-variables.md#44-omp_nested)
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) Bibliotheksfunktion

## <a name="24-work-sharing-constructs"></a>2,4 work-Sharing-Konstrukte

Mit einem Arbeits Freigabe Konstrukt wird die Ausführung der zugeordneten-Anweisung auf die Mitglieder des Teams verteilt, in denen es auftritt. Die Anweisungen für die gemeinsame Verwendung von Arbeits Freigaben starten keine neuen Threads, und es gibt keine implizite Barriere beim Einstieg in ein Arbeits Freigabe Konstrukt.

Die Reihenfolge der Arbeits Freigabe-Konstrukte und `barrier` Direktiven, die gefunden wurden, muss für jeden Thread in einem Team identisch sein.

In OpenMP werden die folgenden Konstrukte für die Arbeits Freigabe definiert. diese Konstrukte werden in den folgenden Abschnitten beschrieben:

- [for](#241-for-construct) -Direktive
- [Abschnitts](#242-sections-construct) Direktive
- [einzelne](#243-single-construct) Direktive

### <a name="241-for-construct"></a>2.4.1 für Konstrukt

Die `for`-Direktive identifiziert ein iteratives Arbeits Freigabe Konstrukt, das angibt, dass die Iterationen der zugeordneten Schleife parallel ausgeführt werden. Die Iterationen der `for` Schleife werden auf Threads verteilt, die bereits im Team vorhanden sind, das das parallele Konstrukt ausführt, an das Sie gebunden wird. Die Syntax des `for`-Konstrukts lautet wie folgt:

```cpp
#pragma omp for [clause[[,] clause] ... ] new-line for-loop
```

Die-Klausel ist einer der folgenden:

- `private(` `)` der *Variablen Liste*
- `firstprivate(` `)` der *Variablen Liste*
- `lastprivate(` `)` der *Variablen Liste*
- `reduction(` *Operator* `:` *Variable-list* `)`
- `ordered`
- `schedule(` *Kind* [`,` *chunk_size*] `)`
- `nowait`

Die `for`-Direktive schränkt die Struktur der entsprechenden `for` Schleife ein. Insbesondere muss die entsprechende `for`-Schleife eine kanonische Form aufweisen:

`for (` *Init-expr* `;` *var Logical-op b* `;` *INCR-expr* `)`

*init-expr*<br/>
Eine der folgenden Komponenten:

- *var* = *lb*
- *ganzzahliger Typ var* = *lb*

*INCR-expr*<br/>
Eine der folgenden Komponenten:

- `++` *var*
- *var* -`++`
- `--` *var*
- *var* -`--`
- *var* `+=` *INCR*
- *var* `-=` *INCR*
- *var* `=` *var* `+` *INCR*
- *var* `=` *INCR* `+` *var*
- *var* `=` *var* `-` *INCR*

*var*<br/>
Eine ganzzahlige Variable mit Vorzeichen. Wenn diese Variable andernfalls freigegeben wäre, wird Sie für die Dauer der `for`implizit als privat festgelegte. Ändern Sie diese Variable nicht innerhalb des Texts der `for` Anweisung. Wenn die Variable nicht `lastprivate`angegeben wird, ist der Wert nach der Schleife unbestimmt.

*logisches op*<br/>
Eine der folgenden Komponenten:

- `<`
- `<=`
- `>`
- `>=`

*lb*, *b*und *INCR*<br>
Invariante ganzzahlige Ausdrücke der Schleife. Während der Auswertung dieser Ausdrücke wird keine Synchronisierung durchführen, sodass alle ausgewerteten Nebeneffekte zu unbestimmten Ergebnissen führen.

Die kanonische Form ermöglicht die Berechnung der Anzahl von Schleifen Iterationen für den Eintrag in der Schleife. Diese Berechnung erfolgt mit Werten im Typ " *var*", nachdem ganzzahlige Erweiterungen vorgenommen wurden. Insbesondere, wenn der Wert von *b* `-` *lb* `+` *INCR* nicht in diesem Typ dargestellt werden kann, ist das Ergebnis unbestimmt. Wenn *Logical-op* `<` oder `<=`ist, muss " *INCR-expr* " bewirken, dass *var* bei jeder Iterationen der Schleife zunimmt.   Wenn *Logical-op* `>` oder `>=`ist, muss " *INCR-expr* " bewirken, dass *var* bei jeder Iterationen der Schleife kleiner wird.

Die `schedule`-Klausel gibt an, wie Iterationen der `for` Schleife zwischen den Threads des Teams aufgeteilt werden. Die Richtigkeit eines Programms darf nicht davon abhängen, welcher Thread eine bestimmte Iterationen ausführt. Der Wert *chunk_size*muss, falls angegeben, ein invarianter Schleifen Ausdruck mit einem positiven Wert sein. Während der Auswertung dieses Ausdrucks wird keine Synchronisierung durchführen, sodass alle ausgewerteten Nebeneffekte zu unbestimmten Ergebnissen führen. Die *Art* des Zeitplans kann einen der folgenden Werte aufweisen:

Tabelle 2-1: Werte Werte *für* `schedule`-Klausel

|||
|-|-|
|Statisch|Wenn `schedule(static,` *chunk_size* `)` angegeben wird, werden Iterationen in Blöcke der von *chunk_size*angegebenen Größe aufgeteilt. Die Blöcke werden den Threads im Team im Team in der Reihenfolge der Thread Nummer statisch zugewiesen. Wenn kein *chunk_size* angegeben wird, wird der Iterations Bereich in Blöcke unterteilt, die ungefähr gleich groß sind, wobei jedem Thread ein Block zugeordnet ist.|
|Dynamische|Wenn `schedule(dynamic,` *chunk_size* `)` angegeben wird, werden die Iterationen in eine Reihe von Blöcken aufgeteilt, die jeweils *chunk_size* Iterationen enthalten. Jeder Block wird einem Thread zugewiesen, der auf eine Zuweisung wartet. Der Thread führt den Teil der Iterationen aus und wartet dann auf seine nächste Zuweisung, bis keine Blöcke mehr zugewiesen werden. Der letzte Block, der zugewiesen werden soll, kann eine geringere Anzahl von Iterationen aufweisen. Wenn kein *chunk_size* angegeben wird, wird der Standardwert 1 verwendet.|
|durch|Wenn `schedule(guided,` *chunk_size* `)` angegeben wird, werden die Iterationen Threads in Blöcken mit absteigender Größe zugewiesen. Wenn ein Thread den zugewiesenen Teil der Iterationen beendet, wird ihm dynamisch ein weiterer Block zugewiesen, bis keine vorhanden ist. Bei einem *chunk_size* von 1 entspricht die Größe jedes Blocks ungefähr der Anzahl der nicht zugewiesenen Iterationen dividiert durch die Anzahl der Threads. Diese Größen verringern sich fast exponentiell auf 1. Bei einer *chunk_size* mit dem Wert *k* größer als 1 verringern sich die Größen fast exponentiell auf *k*, mit der Ausnahme, dass der letzte Block weniger als *k* Iterationen aufweisen kann. Wenn kein *chunk_size* angegeben wird, wird der Standardwert 1 verwendet.|
|Laufzeit|Wenn `schedule(runtime)` angegeben wird, wird die Entscheidung bezüglich der Planung bis zur Laufzeit verzögert. Die *Art* des Zeitplans und die Größe der Blöcke können zur Laufzeit ausgewählt werden, indem die Umgebungsvariable `OMP_SCHEDULE`festgelegt wird. Wenn diese Umgebungsvariable nicht festgelegt ist, wird der resultierende Zeitplan von der Implementierung definiert. Wenn `schedule(runtime)` angegeben wird, darf *chunk_size* nicht angegeben werden.|

Wenn keine explizit definierte `schedule`-Klausel vorhanden ist, wird die Standard `schedule` von der Implementierung definiert.

Ein OpenMP-kompatibles Programm sollte sich nicht auf einen bestimmten Zeitplan für die korrekte Ausführung verlassen. Ein Programm sollte sich nicht auf einen Zeit Plantyp verlassen, der genau mit der oben angegebenen Beschreibung übereinstimmen, da es möglich ist, Abweichungen in den Implementierungen derselben Zeit Plantyp über verschiedene *Compiler hinweg zu* haben. Mithilfe der Beschreibungen können Sie den Zeitplan auswählen, der für eine bestimmte Situation geeignet ist.

Die `ordered`-Klausel muss vorhanden sein, wenn `ordered` Direktiven an das `for`-Konstrukt gebunden werden.

Es gibt eine implizite Barriere am Ende eines `for` Konstrukt, es sei denn, eine `nowait`-Klausel wird angegeben.

Einschränkungen für die `for`-Direktive lauten wie folgt:

- Die `for`-Schleife muss ein strukturierter Block sein, und außerdem darf die Ausführung nicht durch eine `break`-Anweisung beendet werden.

- Die Werte der Schleifen Steuerungs Ausdrücke der `for` Schleife, die mit einer `for` Direktive verknüpft ist, müssen für alle Threads im Team identisch sein.

- Die `for` Schleifen-Iterations Variable muss einen ganzzahligen Typ mit Vorzeichen aufweisen.

- Nur eine einzige `schedule`-Klausel kann in einer `for`-Direktive angezeigt werden.

- Nur eine einzige `ordered`-Klausel kann in einer `for`-Direktive angezeigt werden.

- Nur eine einzige `nowait`-Klausel kann in einer `for`-Direktive angezeigt werden.

- Es ist nicht angegeben, ob oder wie oft Nebeneffekte innerhalb der *chunk_size*-, *lb*-, *b*-oder *INCR* -Ausdrücke auftreten.

- Der Wert des *chunk_size* Ausdrucks muss für alle Threads im Team identisch sein.

#### <a name="cross-references"></a>Querverweise

- `private`-, `firstprivate`-, `lastprivate`-und `reduction`-Klauseln ([Abschnitt 2.7.2](#272-data-sharing-attribute-clauses))
- Umgebungsvariable [OMP_SCHEDULE](4-environment-variables.md#41-omp_schedule)
- [geordnetes](#266-ordered-construct) Konstrukt
- [Schedule](d-using-the-schedule-clause.md) -Klausel

### <a name="242-sections-construct"></a>2.4.2 Abschnitts Konstrukt

Die `sections`-Direktive identifiziert ein noniteratives Arbeits Freigabe Konstrukt, das einen Satz von Konstrukten angibt, die in einem Team in Threads aufgeteilt werden sollen. Jeder Abschnitt wird einmal von einem Thread im Team ausgeführt. Die Syntax der `sections`-Direktive lautet wie folgt:

```cpp
#pragma omp sections [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block ]
...
}
```

Die-Klausel ist einer der folgenden:

- `private(` `)` der *Variablen Liste*
- `firstprivate(` `)` der *Variablen Liste*
- `lastprivate(` `)` der *Variablen Liste*
- `reduction(` *Operator* `:`*Variable-list* `)`
- `nowait`

Jedem Abschnitt ist eine `section`-Direktive vorangestellt, obwohl die `section`-Direktive für den ersten Abschnitt optional ist. Die `section`-Direktiven müssen innerhalb des lexikalischen Wertebereichs der `sections`-Direktive vorkommen. Am Ende eines `sections` Konstrukts gibt es eine implizite Barriere, es sei denn, es wurde ein `nowait` angegeben.

Einschränkungen für die `sections`-Direktive lauten wie folgt:

- Eine `section`-Direktive darf nicht außerhalb des lexikalischen Wertebereichs der `sections` Direktive stehen.

- Nur eine einzige `nowait`-Klausel kann in einer `sections`-Direktive angezeigt werden.

#### <a name="cross-references"></a>Querverweise

- `private`-, `firstprivate`-, `lastprivate`-und `reduction`-Klauseln ([Abschnitt 2.7.2](#272-data-sharing-attribute-clauses))

### <a name="243-single-construct"></a>2.4.3 einzelnes Konstrukt

Die `single`-Direktive identifiziert ein Konstrukt, das angibt, dass der zugeordnete strukturierte Block nur von einem Thread im Team (nicht notwendigerweise vom Master Thread) ausgeführt wird. Die Syntax der `single`-Direktive lautet wie folgt:

```cpp
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

Die-Klausel ist einer der folgenden:

- `private(` `)` der *Variablen Liste*
- `firstprivate(` `)` der *Variablen Liste*
- `copyprivate(` `)` der *Variablen Liste*
- `nowait`

Es gibt eine implizite Barriere nach dem `single` Konstrukt, es sei denn, eine `nowait`-Klausel wurde angegeben.

Einschränkungen für die `single`-Direktive lauten wie folgt:

- Nur eine einzige `nowait`-Klausel kann in einer `single`-Direktive angezeigt werden.
- Die `copyprivate`-Klausel darf nicht mit der `nowait`-Klausel verwendet werden.

#### <a name="cross-references"></a>Querverweise

- `private`-, `firstprivate`-und `copyprivate`-Klauseln ([Abschnitt 2.7.2](#272-data-sharing-attribute-clauses))

## <a name="25-combined-parallel-work-sharing-constructs"></a>2,5 kombinierte parallele Arbeitsteilungskonstrukte

Kombinierte parallele Arbeits Freigabe-Konstrukte sind Verknüpfungen zum Angeben eines parallelen Bereichs, der nur über ein Arbeits Freigabe Konstrukt verfügt. Die Semantik dieser Direktiven ist identisch mit der expliziten Angabe einer `parallel` Direktive, gefolgt von einem einzelnen Konstrukt für die Arbeits Freigabe.

In den folgenden Abschnitten werden die kombinierten parallelen arbeitsfreigabekonstrukte beschrieben:

- [parallel for](#251-parallel-for-construct) -Direktive
- [parallele Abschnitts](#252-parallel-sections-construct) Direktive

### <a name="251-parallel-for-construct"></a>2.5.1 parallel für Konstrukt

Die `parallel for`-Direktive ist eine Verknüpfung für einen `parallel` Bereich, der nur eine einzige `for`-Direktive enthält. Die Syntax der `parallel for`-Direktive lautet wie folgt:

```cpp
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Diese Direktive ermöglicht alle Klauseln der `parallel`-Direktive und der `for`-Direktive mit Ausnahme der `nowait`-Klausel mit identischer Bedeutung und Einschränkungen. Die Semantik ist identisch mit der expliziten Angabe einer `parallel` Direktive, die unmittelbar auf eine `for` Direktive folgt.

#### <a name="cross-references"></a>Querverweise

- [parallel](#23-parallel-construct) -Direktive
- [for](#241-for-construct) -Direktive
- [Daten Attribut Klauseln](#272-data-sharing-attribute-clauses)

### <a name="252-parallel-sections-construct"></a>2.5.2 parallel-Abschnitts Konstrukt

Die `parallel sections`-Direktive stellt ein Verknüpfungs Formular zum Angeben eines `parallel` Bereichs bereit, der nur über eine einzige `sections`-Direktive verfügt. Die Semantik ist identisch mit der expliziten Angabe einer `parallel` Direktive, die unmittelbar auf eine `sections` Direktive folgt. Die Syntax der `parallel sections`-Direktive lautet wie folgt:

```cpp
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

Die- *Klausel* kann eine der Klauseln sein, die von den `parallel`-und `sections`-Direktiven akzeptiert werden, mit Ausnahme der `nowait`-Klausel.

#### <a name="cross-references"></a>Querverweise

- [parallel](#23-parallel-construct) -Direktive
- [Abschnitts](#242-sections-construct) Direktive

## <a name="26-master-and-synchronization-directives"></a>2,6 Master-und Synchronisierungs Direktiven

In den folgenden Abschnitten wird Folgendes beschrieben:

- [Master](#261-master-construct) -Konstrukt
- [kritisches](#262-critical-construct) Konstrukt
- [Barrier](#263-barrier-directive) -Direktive
- [atomisches](#264-atomic-construct) Konstrukt
- [Flush](#265-flush-directive) -Direktive
- [geordnetes](#266-ordered-construct) Konstrukt

### <a name="261-master-construct"></a>2.6.1 Master-Konstrukt

Die `master`-Direktive identifiziert ein Konstrukt, das einen strukturierten Block angibt, der vom Master Thread des Teams ausgeführt wird. Die Syntax der `master`-Direktive lautet wie folgt:

```cpp
#pragma omp master new-linestructured-block
```

Andere Threads im Team führen den zugeordneten strukturierten Block nicht aus. Es gibt keine implizite Barriere, entweder beim Einstieg in das Master Konstrukt oder beim Beenden.

### <a name="262-critical-construct"></a>2.6.2 Critical-Konstrukt

Die `critical`-Direktive identifiziert ein Konstrukt, das die Ausführung des zugeordneten strukturierten Blocks auf jeweils einen einzelnen Thread einschränkt. Die Syntax der `critical`-Direktive lautet wie folgt:

```cpp
#pragma omp critical [(name)]  new-linestructured-block
```

Ein optionaler *Name* kann verwendet werden, um den kritischen Bereich zu identifizieren. Bezeichner, die zum Identifizieren eines kritischen Bereichs verwendet werden, verfügen über externe Verknüpfungen und befinden sich in einem Namespace, der von den Namensräumen getrennt ist, die von Bezeichnungen, Tags, Membern und normalen Bezeichnern verwendet werden.

Ein Thread wartet am Anfang eines kritischen Bereichs, bis kein anderer Thread einen kritischen Bereich (an einer beliebigen Stelle im Programm) mit demselben Namen ausführt. Alle unbenannten `critical` Direktiven werden dem gleichen nicht angegebenen Namen zugeordnet.

### <a name="263-barrier-directive"></a>2.6.3 Barrier-Direktive

Die `barrier`-Direktive synchronisiert alle Threads in einem Team. Wenn Sie gefunden wird, wartet jeder Thread im Team, bis alle anderen diesen Punkt erreicht haben. Die Syntax der `barrier`-Direktive lautet wie folgt:

```cpp
#pragma omp barrier new-line
```

Nachdem alle Threads im Team die Barriere erreicht haben, beginnt jeder Thread im Team, die Anweisungen nach der Barriere-Anweisung parallel auszuführen. Da die `barrier`-Direktive nicht als Teil ihrer Syntax eine C-sprach Anweisung hat, gibt es einige Einschränkungen hinsichtlich der Platzierung innerhalb eines Programms. Weitere Informationen zur formalen Grammatik finden Sie in [Anhang C](c-openmp-c-and-cpp-grammar.md). Diese Einschränkungen werden im folgenden Beispiel veranschaulicht.

```cpp
/* ERROR - The barrier directive cannot be the immediate
*          substatement of an if statement
*/
if (x!=0)
   #pragma omp barrier
...

/* OK - The barrier directive is enclosed in a
*      compound statement.
*/
if (x!=0) {
   #pragma omp barrier
}
```

### <a name="264-atomic-construct"></a>2.6.4 Atomic-Konstrukt

Die `atomic`-Direktive stellt sicher, dass eine bestimmte Speicheradresse atomarisch aktualisiert wird, anstatt Sie der Möglichkeit von mehreren, gleichzeitigen Schreiben von Threads verfügbar zu machen. Die Syntax der `atomic`-Direktive lautet wie folgt:

```cpp
#pragma omp atomic new-lineexpression-stmt
```

Die Expression-Anweisung muss eine der folgenden Formen aufweisen:

- *x binop* -`=` *expr*
- *x* -`++`
- `++` *x*
- *x* -`--`
- `--` *x*

In den vorangehenden Ausdrücken:

- *x* ist ein Lvalue-Ausdruck mit einem skalaren Typ.

- *expr* ist ein Ausdruck mit einem skalaren Typ, der nicht auf das von *x*angegebene Objekt verweist.

- *binop* ist kein überladener Operator und ist einer der `+`, `*`, `-`, `/`, `&`, `^`, `|`, `<<`oder `>>`.

Obwohl die Implementierung definiert ist, ob eine Implementierung alle `atomic`-Direktiven durch `critical` Direktiven ersetzt, die denselben eindeutigen *Namen*haben, ermöglicht die `atomic`-Direktive eine bessere Optimierung. Häufig sind Hardware Anweisungen verfügbar, die das atomarische Update mit dem geringsten Aufwand ausführen können.

Nur die Last und der Speicher des Objekts, das von *x* bestimmt wird, sind atomarisch. die Auswertung von *expr* ist nicht atomarisch. Um Racebedingungen zu vermeiden, sollten alle Updates des Standorts parallel mit der `atomic`-Direktive geschützt werden, mit Ausnahme derjenigen, die bekanntermaßen keine Racebedingungen haben.

Einschränkungen für die `atomic`-Direktive lauten wie folgt:

- Alle atomaren Verweise auf den Speicherort x im gesamten Programm müssen einen kompatiblen Typ aufweisen.

#### <a name="examples"></a>Beispiele

```cpp
extern float a[], *p = a, b;
/* Protect against races among multiple updates. */
#pragma omp atomic
a[index[i]] += b;
/* Protect against races with updates through a. */
#pragma omp atomic
p[i] -= 1.0f;

extern union {int n; float x;} u;
/* ERROR - References through incompatible types. */
#pragma omp atomic
u.n++;
#pragma omp atomic
u.x -= 1.0f;
```

### <a name="265-flush-directive"></a>2.6.5 FLUSH-Anweisung

Die `flush`-Direktive, ob explizit oder implizit, gibt einen Thread übergreifenden Sequenz Punkt an, an dem die Implementierung erforderlich ist, um sicherzustellen, dass alle Threads in einem Team über eine konsistente Ansicht bestimmter (unten angegebener) Objekte im Arbeitsspeicher verfügen. Dies bedeutet, dass vorherige Auswertungen von Ausdrücken, die auf diese Objekte verweisen, fertig sind und nachfolgende Auswertungen noch nicht begonnen haben. Beispielsweise müssen Compiler die Werte der Objekte aus Registern in den Arbeitsspeicher wiederherstellen, und Hardware muss möglicherweise Schreibpuffer in den Arbeitsspeicher leeren und die Werte der Objekte aus dem Arbeitsspeicher neu laden.

Die Syntax der `flush`-Direktive lautet wie folgt:

```cpp
#pragma omp flush [(variable-list)]  new-line
```

Wenn die Objekte, die synchronisiert werden müssen, durch Variablen festgelegt werden können, können diese Variablen in der optionalen *Variablen Liste*angegeben werden. Wenn ein Zeiger in der *Variablen Liste*vorhanden ist, wird der Zeiger selbst geleert, nicht das Objekt, auf das der Zeiger verweist.

Eine `flush`-Anweisung ohne *Variable-list* synchronisiert alle freigegebenen Objekte außer nicht zugänglichen Objekten mit automatischer Speicherdauer. (Dies hat wahrscheinlich mehr Aufwand als ein `flush` mit einer *Variablen Liste*.) Eine `flush`-Direktive ohne *Variable-list* wird für die folgenden Direktiven impliziert:

- `barrier`
- Beim eingeben und Beenden von `critical`
- Beim eingeben und Beenden von `ordered`
- Beim eingeben und Beenden von `parallel`
- Beim Beenden von `for`
- Beim Beenden von `sections`
- Beim Beenden von `single`
- Beim eingeben und Beenden von `parallel for`
- Beim eingeben und Beenden von `parallel sections`

Die-Direktive wird nicht impliziert, wenn eine `nowait`-Klausel vorhanden ist. Beachten Sie, dass die `flush`-Direktive nicht für Folgendes impliziert:

- Beim Eintrag zu `for`
- Beim eingeben oder Beenden von `master`
- Beim Eintrag zu `sections`
- Beim Eintrag zu `single`

Ein Verweis, der auf den Wert eines Objekts mit einem flüchtig qualifizierten Typ zugreift, verhält sich so, als ob es eine `flush` Direktive gäbe, die das Objekt am vorherigen Sequenz Punkt angibt. Ein Verweis, der den Wert eines Objekts mit einem flüchtig qualifizierten Typ ändert, verhält sich so, als ob es eine `flush` Direktive gäbe, die das Objekt am nachfolgenden Sequenz Punkt angibt.

Da die `flush`-Direktive nicht als Teil ihrer Syntax eine C-sprach Anweisung hat, gibt es einige Einschränkungen hinsichtlich der Platzierung innerhalb eines Programms. Weitere Informationen zur formalen Grammatik finden Sie in [Anhang C](c-openmp-c-and-cpp-grammar.md). Diese Einschränkungen werden im folgenden Beispiel veranschaulicht.

```cpp
/* ERROR - The flush directive cannot be the immediate
*          substatement of an if statement.
*/
if (x!=0)
   #pragma omp flush (x)
...

/* OK - The flush directive is enclosed in a
*      compound statement
*/
if (x!=0) {
   #pragma omp flush (x)
}
```

Einschränkungen für die `flush`-Direktive lauten wie folgt:

- Eine Variable, die in einer `flush`-Direktive angegeben ist, darf keinen Verweistyp aufweisen.

### <a name="266-ordered-construct"></a>2.6.6 geordnetes Konstrukt

Der strukturierte Block, der auf eine `ordered` Direktive folgt, wird in der Reihenfolge ausgeführt, in der Iterationen in einer sequenziellen Schleife ausgeführt werden. Die Syntax der `ordered`-Direktive lautet wie folgt:

```cpp
#pragma omp ordered new-linestructured-block
```

Eine `ordered` Direktive muss innerhalb des dynamischen Wertebereichs eines `for`-oder `parallel for`-Konstrukts liegen. Für den `for` oder `parallel for` Direktive, an die das `ordered` Konstrukt gebunden ist, muss eine `ordered`-Klausel angegeben werden, wie im [Abschnitt 2.4.1](#241-for-construct)beschrieben. Bei der Ausführung eines `for` oder `parallel for`-Konstrukts mit einer `ordered`-Klausel werden `ordered`-Konstrukte streng in der Reihenfolge ausgeführt, in der Sie in einer sequenziellen Ausführung der Schleife ausgeführt werden.

Einschränkungen für die `ordered`-Direktive lauten wie folgt:

- Eine Iterations Schleife mit einem `for`-Konstrukt darf nicht dieselbe geordnete Direktive mehrmals ausführen, und es darf nicht mehr als eine `ordered` Direktive ausgeführt werden.

## <a name="27-data-environment"></a>2,7-Daten Umgebung

In diesem Abschnitt werden eine-Direktive und verschiedene Klauseln zum Steuern der Daten Umgebung während der Ausführung paralleler Regionen wie folgt dargestellt:

- Eine [Thread private](#271-threadprivate-directive) -Direktive wird bereitgestellt, um die Variablen für den Datei Bereich, den Namespace Bereich oder den statischen Block Bereich lokal in einem Thread zu erstellen.

- Klauseln, die in den-Direktiven angegeben werden können, um die Freigabe Attribute von Variablen für die Dauer der parallel-oder work-Sharing-Konstrukte zu steuern, werden im [Abschnitt 2.7.2](#272-data-sharing-attribute-clauses)beschrieben.

### <a name="271-threadprivate-directive"></a>2.7.1 Thread private-Direktive

Die `threadprivate`-Direktive macht den benannten Datei Bereich, den Namespace Bereich oder statische Block Bereichs Variablen, die in der *Variablen Liste* als privat angegeben werden, einem Thread als privat fest. *Variable-list* ist eine durch Trennzeichen getrennte Liste von Variablen, die keinen unvollständigen Typ aufweisen. Die Syntax der `threadprivate`-Direktive lautet wie folgt:

```cpp
#pragma omp threadprivate(variable-list) new-line
```

Jede Kopie einer `threadprivate` Variablen wird einmal, an einem nicht angegebenen Punkt im Programm vor dem ersten Verweis auf diese Kopie und auf die übliche Weise initialisiert (d. h., da die Master Kopie bei einer seriellen Ausführung des Programms initialisiert wird). Beachten Sie Folgendes: Wenn auf ein Objekt in einem expliziten Initialisierer einer `threadprivate` Variablen verwiesen wird und der Wert des Objekts vor dem ersten Verweis auf eine Kopie der Variablen geändert wird, ist das Verhalten nicht angegeben.

Wie bei jeder privaten Variablen darf ein Thread nicht auf eine andere Thread Kopie eines `threadprivate` Objekts verweisen. Während der seriellen und der Hauptbereiche des Programms werden Verweise auf die Kopie des-Objekts des Master Threads durch verwiesen.

Nachdem der erste parallele Bereich ausgeführt wurde, wird sichergestellt, dass die Daten in den `threadprivate` Objekten nur persistent gespeichert werden, wenn der Mechanismus für dynamische Threads deaktiviert wurde und die Anzahl der Threads für alle parallelen Bereiche unverändert bleibt.

Die folgenden Einschränkungen gelten für die `threadprivate`-Direktive:

- Eine `threadprivate`-Direktive für Variablen im Gültigkeitsbereich oder im Namespace Bereich muss außerhalb einer Definition oder Deklaration stehen und muss lexikalisch allen Verweisen auf eine der Variablen in der Liste vorangestellt sein.

- Jede Variable in der *Variablen-List* einer `threadprivate`-Direktive im Datei-oder Namespace-Gültigkeitsbereich muss auf eine Variablen Deklaration im Datei-oder Namespace Bereich verweisen, die lexikalisch der Direktive vorangestellt ist.

- Eine `threadprivate`-Direktive für statische Block Bereichs Variablen muss im Gültigkeitsbereich der Variablen und nicht in einem nicht in einem Bereich befindlichen Bereich enthalten sein. Die Direktive muss lexikalisch allen Verweisen auf eine der Variablen in der Liste vorangestellt sein.

- Jede Variable in der *Variablen-List* einer `threadprivate`-Direktive im Block Bereich muss auf eine Variablen Deklaration im gleichen Bereich verweisen, der der Direktive lexikalisch vorangestellt ist. Die Variablen Deklaration muss den static-Speicherklassenspezifizierer verwenden.

- Wenn eine Variable in einer `threadprivate`-Anweisung in einer Übersetzungseinheit angegeben wird, muss Sie in jeder Übersetzungseinheit, in der Sie deklariert wird, in einer `threadprivate`-Direktive angegeben werden.

- Eine `threadprivate` Variable darf nicht in einer Klausel angezeigt werden, außer der `copyin`, der `copyprivate`, `schedule`, `num_threads`oder der `if`-Klausel.

- Die Adresse einer `threadprivate` Variablen ist keine Adress Konstante.

- Eine `threadprivate` Variable darf keinen unvollständigen Typ oder Verweistyp aufweisen.

- Eine `threadprivate` Variable mit einem nicht-Pod-Klassentyp muss über einen zugänglichen, eindeutigen Kopierkonstruktor verfügen, wenn Sie mit einem expliziten Initialisierer deklariert wird.

Im folgenden Beispiel wird veranschaulicht, wie das Ändern einer Variablen, die in einem Initialisierer angezeigt wird, nicht bestimmtes Verhalten verursachen kann. Außerdem wird erläutert, wie Sie dieses Problem vermeiden, indem Sie ein Hilfsobjekt und einen Kopierkonstruktor verwenden.

```cpp
int x = 1;
T a(x);
const T b_aux(x); /* Capture value of x = 1 */
T b(b_aux);
#pragma omp threadprivate(a, b)

void f(int n) {
   x++;
   #pragma omp parallel for
   /* In each thread:
   * Object a is constructed from x (with value 1 or 2?)
   * Object b is copy-constructed from b_aux
   */
   for (int i=0; i<n; i++) {
      g(a, b); /* Value of a is unspecified. */
   }
}
```

#### <a name="cross-references"></a>Querverweise

- [dynamische Threads](3-run-time-library-functions.md#317-omp_set_dynamic-function)
- Umgebungsvariable [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)

### <a name="272-data-sharing-attribute-clauses"></a>2.7.2-Datenfreigabe-Attribut Klauseln

Mehrere Direktiven akzeptieren Klauseln, die es Benutzern ermöglichen, die Freigabe Attribute von Variablen für die Dauer der Region zu steuern. Freigabe Attribut Klauseln gelten nur für Variablen im lexikalischen Umfang der Direktive, für die die-Klausel angezeigt wird. Nicht alle der folgenden Klauseln sind für alle-Direktiven zulässig. Die Liste der Klauseln, die für eine bestimmte Direktive gültig sind, wird mit der-Direktive beschrieben.

Wenn eine Variable sichtbar ist, wenn ein paralleles oder Arbeits Freigabe Konstrukt gefunden wird und die Variable nicht in einer Freigabe Attribut Klausel oder `threadprivate`-Direktive angegeben ist, wird die Variable freigegeben. Statische Variablen, die innerhalb des dynamischen Wertebereichs eines parallelen Bereichs deklariert werden, werden freigegeben. Der Heap zugeordneter Speicher (z. b. das C++ Verwenden von `malloc()` in C C++oder oder der `new` Operator in) wird freigegeben. (Der Zeiger auf diesen Arbeitsspeicher kann jedoch entweder privat oder freigegeben sein.) Variablen mit automatischer Speicherdauer, die innerhalb des dynamischen Umfangs eines parallelen Bereichs deklariert wird, sind privat.

Die meisten Klauseln akzeptieren ein *Variablen Listen* Argument, bei dem es sich um eine durch Trennzeichen getrennte Liste von Variablen handelt, die sichtbar sind. Wenn eine Variable, auf die in einer Datenfreigabe-Attribut Klausel verwiesen wird, einen Typ aufweist, der von einer Vorlage abgeleitet ist, und keine anderen Verweise auf diese Variable im Programm vorhanden sind, ist das Verhalten nicht definiert.

Alle Variablen, die innerhalb von direktivenklauseln vorkommen, müssen sichtbar sein. Klauseln können bei Bedarf wiederholt werden, es kann jedoch keine Variable in mehr als einer Klausel angegeben werden, mit der Ausnahme, dass eine Variable sowohl in einer `firstprivate` als auch in einer `lastprivate`-Klausel angegeben werden kann.

In den folgenden Abschnitten werden die Klauseln für die Datenfreigabe Attribute beschrieben:

- [private](#2721-private)
- [firstprivate](#2722-firstprivate)
- [lastprivate](#2723-lastprivate)
- [Genu](#2724-shared)
- [default](#2725-default)
- [reduction](#2726-reduction)
- [copyin](#2727-copyin)
- [copyprivate](#2728-copyprivate)

#### <a name="2721-private"></a>2.7.2.1 private

Die `private`-Klausel deklariert die Variablen in Variable-List, damit Sie für jeden Thread in einem Team privat ist. Die Syntax der `private`-Klausel lautet wie folgt:

```cpp
private(variable-list)
```

Das Verhalten einer Variablen, die in einer `private`-Klausel angegeben ist, lautet wie folgt. Ein neues-Objekt mit automatischer Speicherdauer wird dem-Konstrukt zugeordnet. Die Größe und die Ausrichtung des neuen Objekts werden durch den Typ der Variablen bestimmt. Diese Zuordnung erfolgt einmal für jeden Thread im Team, und bei Bedarf wird ein Standardkonstruktor für ein Klassenobjekt aufgerufen. Andernfalls ist der Anfangswert unbestimmt.  Das ursprüngliche Objekt, auf das von der-Variable verwiesen wird, hat einen unbestimmten Wert, wenn der Eintrag in das-Konstrukt geändert wird, darf nicht innerhalb des dynamischen Wertebereichs des Konstrukts geändert werden und hat beim Beenden des Konstrukts einen unbestimmten Wert.

Im lexikalischen Umfang des direktivenkonstrukts verweist die Variable auf das neue private Objekt, das vom Thread zugeordnet wird.

Die Einschränkungen für die `private`-Klausel lauten wie folgt:

- Eine Variable mit einem Klassentyp, der in einer `private`-Klausel angegeben ist, muss über einen zugänglichen, eindeutigen Standardkonstruktor verfügen.

- Eine in einer `private`-Klausel angegebene Variable darf keinen `const`qualifizierten Typ aufweisen, es sei denn, Sie weist einen Klassentyp mit einem `mutable` Member auf.

- Eine in einer `private`-Klausel angegebene Variable darf keinen unvollständigen Typ oder Verweistyp aufweisen.

- Variablen, die in der `reduction`-Klausel einer `parallel`-Direktive angezeigt werden, können nicht in einer `private`-Klausel für eine Arbeits Freigabe Direktive angegeben werden, die an das parallele Konstrukt gebunden ist.

#### <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

Die `firstprivate`-Klausel stellt eine supermenge der Funktionen bereit, die von der `private`-Klausel bereitgestellt werden. Die Syntax der `firstprivate`-Klausel lautet wie folgt:

```cpp
firstprivate(variable-list)
```

In der *Variablen Liste* angegebene Variablen verfügen über `private`-klauselsemantik, wie im [Abschnitt 2.7.2.1](#2721-private)beschrieben. Die Initialisierung oder Konstruktion erfolgt so, als ob Sie einmal pro Thread erfolgt wäre, bevor die Ausführung des Konstrukts des Threads erfolgt. Bei einer `firstprivate`-Klausel für ein paralleles Konstrukt ist der Anfangswert des neuen privaten Objekts der Wert des ursprünglichen Objekts, das unmittelbar vor dem parallelen Konstrukt für den Thread vorhanden ist, der darauf stößt. Bei einer `firstprivate`-Klausel für ein Arbeits Freigabe Konstrukt ist der Anfangswert des neuen privaten Objekts für jeden Thread, der das Konstrukt für die Arbeits Freigabe ausführt, der Wert des ursprünglichen Objekts, das vor dem Zeitpunkt vorhanden ist, an dem derselbe Thread auf das Konstrukt für die Arbeits Freigabe trifft. Außerdem wird für C++ -Objekte das neue private-Objekt für jeden Thread aus dem ursprünglichen-Objekt erstellt.

Die Einschränkungen für die `firstprivate`-Klausel lauten wie folgt:

- Eine in einer `firstprivate`-Klausel angegebene Variable darf keinen unvollständigen Typ oder Verweistyp aufweisen.

- Eine Variable mit einem Klassentyp, der als `firstprivate` angegeben ist, muss über einen zugänglichen, eindeutigen Kopierkonstruktor verfügen.

- Variablen, die in einem parallelen Bereich Privat sind oder in der `reduction`-Klausel einer `parallel`-Direktive angezeigt werden, können nicht in einer `firstprivate`-Klausel für eine Arbeits Freigabe Direktive angegeben werden, die an das parallele Konstrukt gebunden ist.

#### <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

Die `lastprivate`-Klausel stellt eine supermenge der Funktionen bereit, die von der `private`-Klausel bereitgestellt werden. Die Syntax der `lastprivate`-Klausel lautet wie folgt:

```cpp
lastprivate(variable-list)
```

Die Variablen, die in der *Variablen Liste* angegeben sind, haben `private`-klauselsemantik. Wenn eine `lastprivate`-Klausel in der Direktive angezeigt wird, die ein Arbeits Freigabe Konstrukt identifiziert, wird der Wert jeder `lastprivate` Variablen aus der sequenziellen letzten Iterationen der zugeordneten Schleife oder der lexikalisch letzten Abschnitts Direktive dem ursprünglichen Objekt der Variablen zugewiesen. Variablen, denen kein Wert durch die letzte Iterations `for` oder `parallel for`oder im lexikalisch letzten Abschnitt der `sections`-oder `parallel sections` Direktive zugewiesen ist, haben nach dem-Konstrukt indehe-Werte. Nicht zugewiesene unter Objekte verfügen auch über einen unbestimmten Wert nach dem-Konstrukt.

Die Einschränkungen für die `lastprivate`-Klausel lauten wie folgt:

- Alle Einschränkungen für `private` gelten.

- Eine Variable mit einem Klassentyp, der als `lastprivate` angegeben ist, muss über einen zugänglichen, eindeutigen Kopier Zuweisungs Operator verfügen.

- Variablen, die in einem parallelen Bereich Privat sind oder in der `reduction`-Klausel einer `parallel`-Direktive angezeigt werden, können nicht in einer `lastprivate`-Klausel für eine Arbeits Freigabe Direktive angegeben werden, die an das parallele Konstrukt gebunden ist.

#### <a name="2724-shared"></a>2.7.2.4 shared

Diese Klausel gibt Variablen frei, die in der *Variablen Liste* für alle Threads in einem Team angezeigt werden. Alle Threads innerhalb eines Teams greifen für `shared` Variablen auf denselben Speicherbereich zu.

Die Syntax der `shared`-Klausel lautet wie folgt:

```cpp
shared(variable-list)
```

#### <a name="2725-default"></a>2.7.2.5 default

Die `default`-Klausel ermöglicht dem Benutzer, die Datenfreigabe Attribute von Variablen zu beeinflussen. Die Syntax der `default`-Klausel lautet wie folgt:

```cpp
default(shared | none)
```

Das Angeben von `default(shared)` entspricht dem expliziten auflisten jeder derzeit sichtbaren Variablen in einer `shared`-Klausel, es sei denn, Sie ist `threadprivate` oder `const`qualifiziert. Wenn keine explizite `default`-Klausel vorhanden ist, entspricht das Standardverhalten dem, wenn `default(shared)` angegeben wurden.

Wenn Sie `default(none)` angeben, muss mindestens einer der folgenden Punkte für jeden Verweis auf eine Variable im lexikalischen Wertebereich des parallelen Konstrukts auf "true" festgelegt werden:

- Die-Variable wird explizit in einer Datenfreigabe-Attribut Klausel eines-Konstrukts aufgelistet, das den Verweis enthält.

- Die Variable wird innerhalb des parallelen Konstrukts deklariert.

- Die Variable ist `threadprivate`.

- Die Variable verfügt über einen `const`qualifizierten Typ.

- Die-Variable ist die-Schleifen Steuerungs Variable für eine `for`-Schleife, die direkt auf eine `for`-oder `parallel for`-Direktive folgt. der Variablen Verweis wird in der-Schleife angezeigt.

Das Angeben einer Variablen in einer `firstprivate`-, `lastprivate`-oder `reduction`-Klausel einer eingeschlossenen-Direktive bewirkt einen impliziten Verweis auf die Variable im umschließenden Kontext. Solche impliziten Verweise unterliegen auch den oben aufgeführten Anforderungen.

In einer `parallel`-Direktive kann nur eine einzige `default`-Klausel angegeben werden.

Das Standard Attribut für die Datenfreigabe einer Variablen kann mithilfe der Klauseln `private`, `firstprivate`, `lastprivate`, `reduction`und `shared` überschrieben werden, wie im folgenden Beispiel gezeigt:

```cpp
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```

#### <a name="2726-reduction"></a>2.7.2.6 reduction

Diese Klausel führt eine Reduzierung der skalaren Variablen aus, die in *Variable-list*mit dem Operator *op*angezeigt werden. Die Syntax der `reduction`-Klausel lautet wie folgt:

`reduction(` *op* `:` *Variable-list* `)`

Eine Reduzierung wird in der Regel für eine-Anweisung mit einer der folgenden Formen angegeben:

- *x* `=` *x* - *op* - *expr*
- *x* *binop* -`=` *expr*
- *x* `=` *expr* *op* *x* (außer Subtraktion)
- *x* -`++`
- `++` *x*
- *x* -`--`
- `--` *x*

Dabei gilt:

*x*<br/>
Eine der in der Liste angegebenen Reduzierungs Variablen.

*Variable-list*<br/>
Eine durch Trennzeichen getrennte Liste von skalaren Reduzierungs Variablen.

*expr*<br/>
Ein Ausdruck mit einem skalaren Typ, der nicht auf *x*verweist.

*schel*<br/>
Es handelt sich nicht um einen überladenen Operator, sondern um einen der `+`, `*`, `-`, `&`, `^`, `|`, `&&`oder `||`.

*binop*<br/>
Es handelt sich nicht um einen überladenen Operator, sondern um einen der `+`, `*`, `-`, `&`, `^`oder `|`.

Im folgenden finden Sie ein Beispiel für die `reduction`-Klausel:

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

Wie im Beispiel gezeigt, kann ein Operator innerhalb eines Funktions Aufrufes ausgeblendet werden. Der Benutzer muss darauf achten, dass der in der `reduction`-Klausel angegebene Operator mit dem Reduzierungs Vorgang übereinstimmt.

Obwohl der rechte Operand des `||` Operators in diesem Beispiel keine Nebeneffekte hat, sind Sie zulässig, sollten jedoch mit Bedacht verwendet werden. In diesem Kontext kann ein Nebeneffekt, der garantiert nicht während der sequenziellen Ausführung der Schleife auftritt, während der parallelen Ausführung auftreten. Dieser Unterschied kann auftreten, wenn die Reihenfolge der Ausführung der Iterationen unbestimmt ist.

Der-Operator wird verwendet, um den Anfangswert von privaten Variablen zu ermitteln, die vom Compiler für die Reduzierung verwendet werden, und um den Abschluss-Operator zu bestimmen. Wenn Sie den-Operator explizit angeben, kann die Reduction-Anweisung nicht mit dem lexikalischen Wertebereich des Konstrukts identisch sein. In der Direktive können beliebig viele `reduction` Klauseln angegeben werden, eine Variable kann jedoch in höchstens einer `reduction`-Klausel für diese Direktive angezeigt werden.

Eine private Kopie jeder Variablen in der *Variablen Liste* wird erstellt, eine für jeden Thread, als ob die `private`-Klausel verwendet worden wäre. Die private Kopie wird gemäß dem Operator initialisiert (siehe folgende Tabelle).

Am Ende des Bereichs, für den die `reduction`-Klausel angegeben wurde, wird das ursprüngliche-Objekt aktualisiert, um das Ergebnis der Kombination des ursprünglichen Werts mit dem endgültigen Wert der einzelnen privaten Kopien mithilfe des angegebenen Operators widerzuspiegeln. Die Reduzierungs Operatoren sind alle assoziativ (außer der Subtraktion), und der Compiler kann die Berechnung des endgültigen Werts frei zuordnen. (Die partiellen Ergebnisse einer Subtraktions Reduzierung werden hinzugefügt, um den endgültigen Wert zu bilden.)

Der Wert des ursprünglichen Objekts wird unbestimmt, wenn der erste Thread die enthaltende Klausel erreicht und so lange bleibt, bis die Verringerung der Berechnung beendet ist.  Normalerweise wird die Berechnung am Ende des Konstrukts abgeschlossen. Wenn jedoch die `reduction`-Klausel für ein Konstrukt verwendet wird, auf das `nowait` ebenfalls angewendet wird, bleibt der Wert des ursprünglichen Objekts unbestimmt, bis eine Barriere-Synchronisierung durchgeführt wurde, um sicherzustellen, dass alle Threads die `reduction`-Klausel abgeschlossen haben.

In der folgenden Tabelle werden die gültigen Operatoren und deren kanonische Initialisierungs Werte aufgelistet. Der tatsächliche Initialisierungs Wert ist mit dem Datentyp der Reduzierungs Variablen konsistent.

|Operator|Initialisierung|
|--------------|--------------------|
|`+`|0|
|`*`|1|
|`-`|0|
|`&`|~0|
|`|`|0|
|`^`|0|
|`&&`|1|
|`||`|0|

Die Einschränkungen für die `reduction`-Klausel lauten wie folgt:

- Der Typ der Variablen in der `reduction`-Klausel muss für den Reduction-Operator gültig sein, mit dem Unterschied, dass Zeiger Typen und Verweis Typen nie zulässig sind.

- Eine in der `reduction`-Klausel angegebene Variable darf nicht `const`qualifiziert sein.

- Variablen, die in einem parallelen Bereich Privat sind oder in der `reduction`-Klausel einer `parallel`-Direktive angezeigt werden, können nicht in einer `reduction`-Klausel für eine Arbeits Freigabe Direktive angegeben werden, die an das parallele Konstrukt gebunden ist.

   ```cpp
   #pragma omp parallel private(y)
   { /* ERROR - private variable y cannot be specified
                in a reduction clause */
      #pragma omp for reduction(+: y)
      for (i=0; i<n; i++)
         y += b[i];
   }

   /* ERROR - variable x cannot be specified in both
              a shared and a reduction clause */
   #pragma omp parallel for shared(x) reduction(+: x)
   ```

#### <a name="2727-copyin"></a>2.7.2.7 copyin

Die `copyin`-Klausel bietet einen Mechanismus, um `threadprivate` Variablen für jeden Thread im Team, der den parallelen Bereich ausführt, denselben Wert zuzuweisen. Für jede Variable, die in einer `copyin`-Klausel angegeben ist, wird der Wert der Variablen im Master Thread des Teams bei der Zuweisung zu den Thread privaten Kopien am Anfang des parallelen Bereichs kopiert. Die Syntax der `copyin`-Klausel lautet wie folgt:

```cpp

copyin(
variable-list
)
```

Die Einschränkungen für die `copyin`-Klausel lauten wie folgt:

- Eine Variable, die in der `copyin`-Klausel angegeben ist, muss über einen zugänglichen, eindeutigen Kopier Zuweisungs Operator verfügen.

- Eine Variable, die in der `copyin`-Klausel angegeben ist, muss eine `threadprivate` Variable sein.

#### <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

Die `copyprivate`-Klausel stellt einen Mechanismus bereit, mit dem eine private Variable verwendet werden soll, um einen Wert von einem Teammitglied an die anderen Elemente zu übertragen. Es ist eine Alternative zur Verwendung einer freigegebenen Variablen für den Wert, wenn eine solche freigegebene Variable schwierig wäre (z. b. in einer Rekursion, die eine andere Variable auf jeder Ebene erfordert). Die `copyprivate`-Klausel kann nur in der `single`-Direktive angezeigt werden.

Die Syntax der `copyprivate`-Klausel lautet wie folgt:

```cpp

copyprivate(
variable-list
)
```

Die Auswirkung der `copyprivate`-Klausel auf die Variablen in der Variablen Liste tritt nach der Ausführung des strukturierten Blocks auf, der mit dem `single` Konstrukt verknüpft ist, und bevor Threads im Team die Barriere am Ende des Konstrukts verlassen haben. In allen anderen Threads im Team wird diese Variable für jede Variable in der *Variablen Liste*(wie bei der Zuweisung) mit dem Wert der entsprechenden Variablen in dem Thread definiert, der den strukturierten Block des Konstrukts ausgeführt hat.

Einschränkungen für die `copyprivate`-Klausel lauten wie folgt:

- Eine Variable, die in der `copyprivate`-Klausel angegeben wird, darf nicht in einer `private`-oder `firstprivate`-Klausel für dieselbe `single` Direktive vorkommen.

- Wenn eine `single`-Direktive mit einer `copyprivate`-Klausel im dynamischen Bereich eines parallelen Bereichs gefunden wird, müssen alle in der `copyprivate`-Klausel angegebenen Variablen im einschließenden Kontext privat sein.

- Eine Variable, die in der `copyprivate`-Klausel angegeben ist, muss über einen zugänglichen eindeutigen Kopier Zuweisungs Operator verfügen.

## <a name="28-directive-binding"></a>2,8 direktivenbindung

Die dynamische Bindung von-Direktiven muss den folgenden Regeln entsprechen:

- Die `for`-, `sections`-, `single`-, `master`-und `barrier`-Direktiven werden an den dynamisch einschließenden `parallel`gebunden, sofern vorhanden, unabhängig vom Wert einer beliebigen `if`-Klausel, die möglicherweise in dieser Direktive vorhanden ist. Wenn zurzeit kein paralleler Bereich ausgeführt wird, werden die Direktiven von einem Team ausgeführt, das nur aus dem Haupt Thread besteht.

- Die `ordered`-Direktive bindet an den dynamisch einschließenden `for`.

- Die `atomic`-Direktive erzwingt exklusiven Zugriff in Bezug auf `atomic` Direktiven in allen Threads, nicht nur auf das aktuelle Team.

- Die `critical`-Direktive erzwingt exklusiven Zugriff in Bezug auf `critical` Direktiven in allen Threads, nicht nur auf das aktuelle Team.

- Eine-Direktive kann niemals eine Bindung an eine-Direktive außerhalb der nächstgelegenen dynamisch einschließenden `parallel`.

## <a name="29-directive-nesting"></a>2,9

Die dynamische Schachtelung von-Direktiven muss den folgenden Regeln entsprechen:

- Eine `parallel`-Anweisung in einer anderen `parallel` logisch ein neues Team, das nur aus dem aktuellen Thread besteht, wenn die geschachtelte Parallelität aktiviert ist.

- `for`, `sections`und `single` Direktiven, die an denselben `parallel` gebunden werden, dürfen nicht ineinander geschachtelt werden.

- `critical`-Direktiven mit demselben Namen dürfen nicht ineinander geschachtelt werden. Beachten Sie, dass diese Einschränkung nicht ausreicht, um Deadlocks zu verhindern.

- `for`-, `sections`-und `single`-Direktiven sind im dynamischen Ausmaß der `critical`, `ordered`und `master` Regionen nicht zulässig, wenn die Direktiven an denselben `parallel` wie die Regionen gebunden werden.

- `barrier`-Direktiven sind im dynamischen Umfang von `for`, `ordered`, `sections`, `single`, `master`und `critical` Regionen nicht zulässig, wenn die Direktiven an denselben `parallel` wie die Regionen gebunden werden.

- `master`-Anweisungen sind im dynamischen Ausmaß von `for`-, `sections`-und `single`-Direktiven nicht zulässig, wenn die `master` Direktiven an denselben `parallel` gebunden werden wie die Arbeits Freigabe Direktiven.

- `ordered`-Anweisungen sind im dynamischen Bereich von `critical` Regionen nicht zulässig, wenn die Direktiven an denselben `parallel` wie die Regionen gebunden werden.

- Jede Direktive, die zulässig ist, wenn Sie in einem parallelen Bereich dynamisch ausgeführt wird, ist auch bei der Ausführung außerhalb eines parallelen Bereichs zulässig. Bei der dynamischen Ausführung außerhalb eines vom Benutzer angegebenen parallelen Bereichs wird die-Direktive von einem Team ausgeführt, das nur aus dem Master Thread besteht.
