---
title: "Partielle Klassen (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 69d93575-636c-4564-8cca-6dfba0c7e328
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# Partielle Klassen (C++/CX)
Eine partielle Klasse ist ein Konstrukt, das Szenarien unterstützt, in denen Sie einen Teil einer Klassendefinition ändern. Software, die automatisch Code generiert – beispielsweise der XAML Designer – ändert ebenfalls Code in der gleichen Klasse. Durch die Verwendung einer partiellen Klasse können Sie verhindern, dass der Designer Ihren Code überschreibt. In einem Visual Studio\-Projekt wird der Modifizierer `partial` automatisch auf die generierte Datei angewendet.  
  
## Syntax  
 Um eine partielle Klasse zu definieren, verwenden Sie das Schlüsselwort `partial` direkt vor dem Klassenschlüssel. Andernfalls wäre dies eine normale Klassendefinition. Ein Schlüsselwort wie `partial ref class` ist ein Kontextschlüsselwort, das Leerzeichen enthält. Partielle Definitionen werden in den folgenden Konstrukten unterstützt.  
  
-   `class` oder `struct`  
  
-   `ref class` oder `ref struct`  
  
-   `value class` oder `value struct`  
  
-   `enum` oder `enum class`  
  
-   `ref interface`, `interface class`, `interface struct` oder `__interface`  
  
-   `union`  
  
 Dieses Beispiel zeigt eine partielle `ref class`:  
  
 [!code-cpp[cx_partial#01](../snippets/cpp/VS_Snippets_Misc/cx_partial/cpp/class1.h#01)]  
  
## Inhalt  
 Eine partielle Klassendefinition kann alles enthalten, was die vollständige Klassendefinition enthalten kann, wenn das Schlüsselwort `partial` ausgelassen wird. Mit einer Ausnahme schließt dies jedes gültige Konstrukt ein, z. B. Basisklassen, Datenmember, Memberfunktionen, Enumerationen, Friend\-Deklarationen und Attribute. Inlinedefinitionen statischer Datenmember sind zulässig.  
  
 Die eine Ausnahme ist die Klassen\-Barrierefreiheit. Beispielsweise ist die Anweisung `public partial class MyInvalidClass {/* ... */};` fehlerhaft. Zugriffsspezifizierer, die in einer partiellen Klassendefinition für MyInvalidClass verwendet werden, wirken sich nicht auf die Standard\-Barrierefreiheit in einer nachfolgenden partiellen oder vollständigen Klassendefinition für MyInvalidClass aus.  
  
 Das folgende Codefragment zeigt die Barrierefreiheit. In der ersten partiellen Klasse ist `Method1` öffentlich, weil die Barrierefreiheit öffentlich ist. In der zweiten partiellen Klasse ist `Method2` privat, weil die standardmäßige Klassenbarrierefreiheit privat ist.  
  
 [!code-cpp[cx_partial#02](../snippets/cpp/VS_Snippets_Misc/cx_partial/cpp/class1.h#02)]  
  
## Deklaration  
 Eine partielle Definition einer Klasse, wie etwa *MyClass*, ist lediglich eine Deklaration von „MyClass“. Das heißt, sie führt nur den Namen *MyClass* ein.*MyClass* kann in keiner Weise verwendet werden, für die eine Klassendefinition erforderlich ist, z. B. wenn die Größe von *MyClass* bekannt sein muss oder eine Basis oder ein Member von *MyClass* verwendet werden soll.*MyClass* gilt nur dann als definiert, wenn der Compiler auf eine nicht partielle Definition von *MyClass* trifft.  
  
 Im folgenden Beispiel wird das Deklarationsverhalten einer partiellen Klasse demonstriert. Nach Deklaration Nr. 1 kann *MyClass* verwendet werden, als ob sie als Vorwärtsdeklaration geschrieben wäre, `ref class MyClass;`. Deklaration Nr. 2 ist mit Deklaration Nr. 1 äquivalent. Deklaration Nr. 3 ist gültig, da sie eine Vorwärtsdeklaration für eine Klasse ist. Deklaration Nr. 4 ist jedoch ungültig, da  
  
 *MyClass* ist nicht vollständig definiert.  
  
 Deklaration Nr. 5 verwendet nicht das Schlüsselwort `partial`, und die Deklaration definiert *MyClass* vollständig. Daher ist Deklaration Nr. 6 gültig.  
  
 [!code-cpp[Cx_partial#03](../snippets/cpp/VS_Snippets_Misc/cx_partial/cpp/class1.h#03)]  
  
## Anzahl und Reihenfolge  
 Es kann null oder mehr partielle Klassendefinitionen für jede vollständige Definition einer Klasse geben.  
  
 Jede partielle Klassendefinition einer Klasse muss lexikalisch der einen vollständigen Definition dieser Klasse vorausgehen, braucht jedoch Vorwärtsdeklarationen der Klasse nicht vorauszugehen. Wenn es keine vollständige Definition der Klasse gibt, können die partiellen Klassendeklarationen nur Vorwärtsdeklarationen sein.  
  
 Alle Klassenschlüssel, z. B. `class` und `struct`, müssen übereinstimmen. Beispielsweise ist der Code `partial class`  *X*`{};``struct` *X*`{};` fehlerhaft.  
  
 Das folgende Beispiel zeigt Anzahl und Reihenfolge. Bei der letzten partiellen Deklaration tritt ein Fehler auf, da die Klasse bereits definiert ist.  
  
 [!code-cpp[cx_partial#04](../snippets/cpp/VS_Snippets_Misc/cx_partial/cpp/class1.h#04)]  
  
## Vollständige Definition  
 Zum Zeitpunkt der vollständigen Definition der Klasse ist X ist das Verhalten das Gleiche, als ob die Definition von X alle Basisklassen, Member usw. in der Reihenfolge deklariert hätte, in der sie in der partiellen Klasse gefunden und definiert wurden. Das bedeutet, dass der Inhalt der partiellen Klassen so behandelt wird, als ob er zum Zeitpunkt der vollständigen Definition der Klasse geschrieben wäre. Namenssuche und andere Sprachregeln werden zum Zeitpunkt der vollständigen Definition der Klasse angewendet, als ob der Inhalt der partiellen Klassen an dieser Stelle geschrieben wäre.  
  
 Die folgenden zwei Codebeispiele haben identische Bedeutung und Auswirkungen. Im ersten Beispiel wird eine partielle Klasse verwendet, im zweiten jedoch nicht.  
  
 [!code-cpp[cx_partial#05](../snippets/cpp/VS_Snippets_Misc/cx_partial/cpp/class1.h#05)]  
  
 [!code-cpp[cx_partial#06](../snippets/cpp/VS_Snippets_Misc/cx_partial/cpp/class1.h#06)]  
  
## Vorlagen  
 Eine partielle Klasse kann keine Vorlage sein.  
  
## Beschränkungen  
 Eine partielle Klasse kann nicht über eine Übersetzungseinheit hinausgehen.  
  
 Das Schlüsselwort `partial` wird nur in Verbindung mit dem Schlüsselwort `ref class` oder dem Schlüsselwort `value class` unterstützt.  
  
## Beispiele  
 Im folgenden Beispiel wird die Klasse `Address` für zwei Codedateien definiert. Der Designer ändert `Address.details.h`, und Sie ändern `Address.h`. Nur die Klassendefinition in der ersten Datei verwendet das Schlüsselwort `partial`.  
  
 [!code-cpp[cx_partial#07](../snippets/cpp/VS_Snippets_Misc/cx_partial/cpp/address.details.h#07)]  
  
 [!code-cpp[cx_partial#09](../snippets/cpp/VS_Snippets_Misc/cx_partial/cpp/address.h#09)]  
  
## Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)