---
title: Bearbeiten und Umgestalten von C++-Code in Visual Studio
description: Verwenden Sie den C++-Code-Editor in Visual Studio, um Ihren Code zu formatieren, in ihm zu navigieren, ihn zu verstehen und umzugestalten.
ms.date: 05/31/2019
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
ms.topic: overview
ms.openlocfilehash: da3f4e7d783561dba8250652a0715e51e71cc387
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438166"
---
# <a name="edit-and-refactor-c-code-in-visual-studio"></a>Bearbeiten und Umgestalten von C++-Code in Visual Studio

In Visual Studio sind mehrere Tools enthalten, mit denen Sie Ihren Code schreiben, bearbeiten und umgestalten können.

##  <a name="intellisense"></a>IntelliSense

IntelliSense ist ein leistungsstarkes Tool zur Codevervollständigung, das Ihnen bei der Eingabe Symbole und Codeausschnitte vorschlägt. C++-IntelliSense in Visual Studio wird in Echtzeit ausgeführt und analysiert Ihre Codebasis, während Sie diese bearbeiten, und macht Vorschläge. Je mehr Zeichen Sie eingeben, desto kürzer wird die Liste mit Vorschlägen.

![Dropdownliste mit Membern (C&#43;&#43;)](../ide/media/cpp-statement-completion.png)

Einige Symbole werden automatisch weggelassen, um die Ergebnisse einzugrenzen. Wenn Sie z. b. auf die Member eines Klassen Objekts von außerhalb der Klasse zugreifen, sind standardmäßig keine privaten Member oder geschützte Member sichtbar (wenn Sie sich nicht im Kontext einer untergeordneten Klasse befinden). Sie können die Filter über die Schaltflächen am unteren Rand anpassen.

Nachdem Sie das Symbol aus der Dropdown Liste ausgewählt haben, können Sie es mit **Tab**, **Eingabe**Taste oder einem der anderen Commit-Zeichen (standardmäßig `{ } [ ] ( ) . , : ; + - * / % & | ^ ! = ? @ # \`) automatisch vervollständigen. Suchen Sie nach „IntelliSense“ im **Schnellstart** (STRG + Q), und wählen Sie **Text-Editor > C/C++ > Erweitert** aus, um Symbole aus dieser Liste zu entfernen oder dieser hinzuzufügen. Mit der Option **Commitzeichen der Memberliste** können Sie die gewünschten Änderungen an der Liste vornehmen.

Mit der Option **Memberlistenfilter-Modus** können Sie festlegen, welche IntelliSense-Vervollständigungsvorschläge angezeigt werden. Standardmäßig ist diese auf **Fuzzy** (unscharf) festgelegt. Bei einer unscharfen Suche können Sie „MAC“ eingeben und die Klasse *MyAwesomeClass* über die Vervollständigungsvorschläge finden. Der unscharfe Algorithmus legt einen Mindestschwellenwert fest, den Symbole erfüllen müssen, um in der Liste angezeigt zu werden. **Intelligentes Filtern** zeigt alle Symbole an, die Teilzeichenfolgen enthalten, die der Eingabe entsprechen. **Präfixfiltern** sucht nach Zeichenfolgen, die mit den eingegebenen Zeichen beginnen.

Weitere Informationen zu C++-IntelliSense finden Sie unter [IntelliSense-Features für Visual C++](/visualstudio/ide/visual-cpp-intellisense) und [Konfigurieren eines C++-Projekts für IntelliSense](/visualstudio/ide/visual-cpp-intellisense-configuration).

## <a name="intellicode"></a>IntelliCode

IntelliCode ist das KI-gestützte Äquivalent zu IntelliSense. Die Funktion zeigt den wahrscheinlichsten Treffer oben in der Liste an. IntelliCode-Empfehlungen basieren auf Tausenden von Open-Source-Projekten auf GitHub, die alle über 100 Sterne haben. Basierend auf dem Kontext Ihres Codes ist die Vervollständigungsliste so konzipiert, dass sie bewährte Vorgehensweisen fördert.

IntelliCode eignet sich beim Schreiben von C++ insbesondere dann, wenn häufig eingesetzte Bibliotheken wie die C++-Standardbibliothek verwendet werden. Der Kontext Ihres Codes wird verwendet, um die besten Empfehlungen zuerst anzuzeigen. Im folgenden Beispiel wird die `size`-Memberfunktion häufig mit der `sort`-Funktion verwendet, weshalb sie ganz oben in der Ergebnisliste angezeigt wird.

![C&#43; &#43; -intellicode](../ide/media/intellicode-cpp.png "C++IntelliCode")

::: moniker range="vs-2019"

In Visual Studio 2019 ist IntelliCode als optionale Komponente in der **Desktopentwicklung mit C++** -Workload verfügbar. Wenn Sie überprüfen möchten, ob IntelliCode für C++ aktiviert ist, navigieren Sie zu **Extras** > **Optionen** > **IntelliCode** > **Allgemein**, und legen Sie **C++-Basismodell** auf **Aktiviert** fest.

::: moniker-end

::: moniker range="vs-2017"

In Visual Studio 2017 ist IntelliCode als Erweiterung über den Visual Studio Marketplace verfügbar.

::: moniker-end

## <a name="predictive-intellisense-experimental"></a>Predictive IntelliSense (Experimentell)

**Predictive IntelliSense** ist eine experimentelle Funktion, die den Kontext beachtet, um die Anzahl der Ergebnisse in der IntelliSense-Dropdownliste zu reduzieren. Der Algorithmus wendet einen Typenabgleich an, um nur die Ergebnisse anzuzeigen, die dem erwarteten Typ entsprechen. Wenn Sie im einfachsten Fall z. B. `int x =` eingeben und die Dropdownliste in IntelliSense aufrufen, werden Ihnen nur ganze Zahlen oder Funktionen angezeigt, die ganze Zahlen zurückgeben. Diese Funktion ist standardmäßig deaktiviert, weil sie sich noch in der Entwicklung befindet. Sie funktioniert am besten mit globalen Symbolen. Memberfunktionen werden noch nicht unterstützt. Sie können die Funktion aktivieren, indem Sie „Predictive“ in den **Schnellstart** eingeben oder indem Sie zu **Extras** > **Optionen** > **Text-Editor** > **C/C++**  > **Experimentell** > **Predictive IntelliSense aktivieren** navigieren.

Um **Predictive IntelliSense** zu überschreiben und die längere Liste anzuzeigen, drücken Sie **STRG + J**. Wenn **Predictive IntelliSense** auf on on ist, wird durch den Aufruf von **STRG + J** der Vorhersage Filter entfernt. Wenn Sie **STRG + J** noch mal drücken, wird der Barrierefreiheitsfilter aus den Memberlistenergebnisse entfernt (falls zutreffend). Die Schaltfläche ([+]) unter der IntelliSense-Dropdown Liste bewirkt dasselbe wie **STRG + J**. Zeigen Sie auf die Schaltfläche, um QuickInfo-Informationen zu den angezeigten Informationen anzuzeigen.

![Vorhersagbare IntelliSense für C&#43; &#43;](../ide/media/predictive-intellisense-cpp.png "Predictive IntelliSense")

Auf dem obigen Screenshot werden mehrere Schaltflächen unter der Dropdownliste angezeigt. Über diese Schaltflächen können Sie IntelliSense-Filter für unterschiedliche Ergebnisse anwenden:

- Variablen und Konstanten
- Functions
- Typen
- Makros
- Enumerationen
- Namespaces

Eine Schaltfläche wird nur dann angezeigt, wenn sie auch für Ihre aktuelle IntelliSense-Sitzung relevant ist. Normalerweise werden nicht alle Schaltflächen gleichzeitig angezeigt.

## <a name="template-intellisense"></a>IntelliSense für Vorlagen

Wenn sich die Einfügemarke in einer Vorlagendefinition befindet, wird eine **Vorlagenleiste** angezeigt, über die Sie Beispielvorlagenargumente für IntelliSense angeben können. 

![C&#43; &#43; -Vorlage IntelliSense zeigt vorhandene Instanziierungen an](../ide/media/template-intellisense-cpp-1.png "Vorlage IntelliSense zeigt vorhandene Instanziierungen an")

Klicken Sie auf das Symbol **\<t >** , um die **Vorlagen Leiste**zu erweitern bzw. zu reduzieren. Klicken Sie auf das Stiftsymbol, oder doppelklicken Sie auf die **Vorlagenleiste**, um das **Bearbeitungsfenster** zu öffnen. 

![C&#43; &#43; -Vorlage (IntelliSense)](../ide/media/template-intellisense-cpp-3.png "IntelliSense für Vorlagen")

Im Fenster vorgenommene Änderungen werden direkt im Quellcode widergespiegelt, sodass Sie die Auswirkungen in Echtzeit sehen können. 

Die Vorlagenleiste kann Kandidaten basierend auf Instanziierungen in Ihrem Code automatisch auffüllen. Klicken Sie auf **Alle vorhandenen Instanziierungen hinzufügen**, um eine Liste aller konkreten Argumente anzuzeigen, die verwendet wurden, um die Vorlage in Ihrer Codebasis zu instanziieren.

![C&#43; &#43; -Vorlage IntelliSense-Ergebnisliste](../ide/media/template-intellisense-cpp-2.png "Vorlage IntelliSense-Ergebnisliste")

Am unteren Rand des Editors wird ein Fenster mit der Position jeder Instanziierung und deren Argumente angezeigt.

![C&#43; &#43; -Vorlage IntelliSense-Instanziierung (Map)](../ide/media/template-intellisense-cpp-4.png "Vorlage IntelliSense-Instanziierung (Map)")

Die Informationen in der **Vorlagenleiste** werden als benutzerspezifisch angesehen. Sie werden im VS-Ordner gespeichert und nicht im Quellcode widergespiegelt.

##  <a name="error-squiggles-and-quick-fixes"></a>Wellenlinien für Fehler und Schnellkorrekturen

Wenn der Editor Probleme in Ihrem Code erkennt, fügt er farbige Wellenlinien unter den betreffenden problematischen Teilen ein. Rote Wellenlinien werden unter Code angezeigt, der nicht kompiliert werden kann. Grüne Wellenlinien geben an, dass ein anderes Problem vorliegt, das dennoch schwerwiegend sein kann. Sie können ein Fenster mit einer **Fehlerliste** öffnen, um mehr Informationen zu den Problemen zu erhalten.

Bei einigen Fehlern und häufigen Codemustern schlägt der Editor eine **Schnellkorrektur** mit einem Glühbirnensymbol vor, das angezeigt wird, wenn Sie mit dem Mauszeiger auf die Wellenlinie zeigen. Klicken Sie auf den Pfeil nach unten, um die Vorschläge anzuzeigen. 

Im folgenden Beispiel wurde ein `vector`-Objekt deklariert, aber es konnte keine Definition gefunden werden, weshalb der Editor vorschlägt, die nötige Headerdatei einzubeziehen:

![C&#43; &#43; -schnell Korrektur](../ide/media/quick-fix-for-header-cpp.png "C++Schnell Korrektur")

Der Editor bietet zudem Schnellkorrekturen für mögliche Refactorings. Wenn Sie beispielsweise eine Klasse in einer Headerdatei deklarieren, schlägt Visual Studio für diese eine Definition in einer separaten CPP-Datei vor. 

![C&#43; &#43; -schnell Korrektur](../ide/media/quick-fix.png "C++Schnell Korrektur")

## <a name="change-tracking"></a>Änderungsnachverfolgung

Jedes Mal, wenn Sie eine Datei ändern, wird eine gelbe Leiste auf der linken Seite angezeigt, um anzugeben, dass Änderungen vorgenommen wurden, die noch nicht gespeichert wurden. Wenn Sie die Datei speichern, wird die Leiste grün. Die grüne und gelbe Leiste werden solange angezeigt, wie das Dokument im Editor geöffnet ist. Sie zeigen die Änderungen an, die seit der letzten Öffnung des Dokuments vorgenommen wurden.

![C&#43; &#43; -Änderungs Nachverfolgung](../ide/media/change-tracking-cpp.png "Änderungsnachverfolgung")

## <a name="move-code"></a>Verschieben von Code

Sie können Codezeilen nach oben oder unten verschieden, indem Sie diese auswählen, die ALT-TASTE gedrückt halten und die **NACH-OBEN-/NACH-UNTEN-TASTEN** verwenden.

##  <a name="insert-snippets"></a>Einfügen von Codeausschnitten

Ein Ausschnitt ist ein vordefinierter Teil des Quellcodes. Klicken Sie mit der rechten Maustaste auf einen einzelnen Punkt oder auf ausgewählten Text, um einen Ausschnitt einzufügen oder den ausgewählten Text mit dem jeweiligen Ausschnitt zu umschließen. Die folgende Abbildung zeigt die drei Schritte zum Umschließen einer ausgewählten-Anweisung mit einer „for“-Schleife. Die gelben Markierungen im endgültigen Bild sind veränderbare Felder, auf die Sie mit der TAB-Taste zugreifen. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).

![C&#43; &#43; & amp; Drop&#45;Ausschnitt einfügen](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

##  <a name="add-class"></a>Hinzufügen

Über das Menü **Projekt** oder über das Kontextmenü im **Projektmappen-Explorer** können Sie eine neue Klasse hinzufügen:

![Neue Klasse in C hinzufügen&#43;&#43;](../ide/media/vs2017-add-class.png "vs2015_cpp_add_class")

Sie können auch den Klassen-Assistenten verwenden, um eine vorhandene Klasse zu ändern oder zu untersuchen.

![C&#43;&#43;-Klassen-Assistent](../ide/media/vs2017-class-wizard.png)

Weitere Informationen finden Sie unter [Adding Functionality with Code Wizards (C++) (Hinzufügen neuer Funktionen mit Code-Assistenten (C++))](../ide/adding-functionality-with-code-wizards-cpp.md).

##  <a name="refactoring"></a>Umgestaltung

Refactorings stehen unter dem Kontextmenü „Schnelle Aktion“ oder durch Klicken auf eine [Glühbirne](/visualstudio/ide/perform-quick-actions-with-light-bulbs) im Editor zur Verfügung.  Einige befinden sich auch im Menü **Bearbeiten > Umgestalten**.  Zu den Features zählen:

* [Umbenennen](refactoring/rename.md)
* [&Funktion extrahieren](refactoring/extract-function.md)
* [Rein virtuelle Aufrufe implementieren](refactoring/implement-pure-virtuals.md)
* [Deklaration/Definition erstellen](refactoring/create-declaration-definition.md)
* [Funktionsdefinition](refactoring/move-definition-location.md)
* [Zu Rohzeichenfolgenliteral konvertieren](refactoring/convert-to-raw-string-literal.md)
* [Signatur ändern](refactoring/change-signature.md)

## <a name="code-style-enforcement-with-clangformat-and-editorconfig"></a>Erzwingung von Codeformat mit ClangFormat und EditorConfig

Visual Studio 2017 und höher enthält integrierte Unterstützung für [ClangFormat](https://clang.llvm.org/docs/ClangFormat.html), ein beliebtes Dienstprogramm zum Formatieren von Code für C++, das auf Clang/LLVM basiert. Geben Sie „ClangFormat“ in den [Schnellstart](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) ein, um festzulegen, welches der folgenden gängigen Formate es verwenden soll:

- LLVM
- Google
- Chromium
- Mozilla
- WebKit
- Visual Studio

Sie können auch Ihr eigenes CLANG-Format oder eine _clang-format-Datei angeben, um benutzerdefinierte Regeln auf alle Codedateien auf der gleichen Ebene oder auf einer niedrigeren Ebene anzuwenden.

Die Dateien können über die Quellcodeverwaltung leicht freigegeben werden, sodass Sie Programmierkonventionen in Ihrem gesamten Entwicklungsteam erzwingen können.

![C&#43; &#43; -clang-Format](../ide/media/clang-format-cpp.png "Clang-Format")

Visual Studio 2017 und höher unterstützt zudem [EditorConfig](https://editorconfig.org/), welches ähnlich funktioniert. ClangFormat hat jedoch mehr Formatoptionen als EditorConfig, z. B. auch C++-spezifische Regeln. Mit **EditorConfig** können Sie **EDITORCONFIG**-Dateien erstellen und diese in unterschiedlichen Ordnern Ihrer Codebasis ablegen, um Codeformate für diese Ordner und ihre Unterordner anzugeben. Eine **EDITORCONFIG**-Datei ersetzt alle anderen **EDITORCONFIG**-Dateien in übergeordneten Ordnern und überschreibt alle Formatierungseinstellungen, die über **Extras** > **Optionen** vorgenommen wurden. Sie können z. B. Regeln für Tabs, Leerzeichen und Einzugsgröße festlegen. Weitere Informationen finden Sie unter [Create portable, custom editor settings with EditorConfig (Erstellen von portablen, benutzerdefinierten Editor-Einstellungen mit EditorConfig)](/visualstudio/ide/create-portable-custom-editor-options).

## <a name="other-formatting-options"></a>Andere Formatierungsoptionen

Über das **Schnellstart**-Suchfeld können Sie eine Einstellung oder ein Tool am schnellsten finden. Das Feld befindet sich im Hauptmenü. Beginnen Sie mit der Eingabe, und die Autovervollständigungsliste filtert die Ergebnisse.

![Visual Studio-Schnellstart](../ide/media/vs2015_cpp_quick_launch.png "Schnellstart")

Geben Sie zum Festlegen von Formatierungsoptionen, z. B. Einzügen, Klammerabschluss und Farbgebung, „C++-Formatierung“ im Fenster **Schnellstart** ein.

![C++-Formatierungsoptionen](media/cpp-formatting-options.png)

Andere Formatierungsoptionen finden Sie unter **Bearbeiten** > **Erweitert** im Hauptmenü.

![Erweiterte C++-Bearbeitungsfunktionen](media/edit-advanced-cpp.png)

Optionen zum Aktivieren und Konfigurieren von C++-spezifischen Bearbeitungsfeatures finden Sie unter **Extras** > **Optionen** > **Text-Editor** > **C/C++** . Wenn Sie die gewünschte Option ausgewählt haben, können Sie mit **F1** weitere Hilfethemen abrufen, wenn das Dialogfeld im Fokus ist. Geben Sie `Editor C++` in den **Schnellstart** ein, um allgemeine Codeformatierungsoptionen abzurufen.

![Optionen für Visual Studio-Tools >](../ide/media/tools-options.png "Editor-Optionen")

Experimentelle Features, die möglicherweise nicht in einer zukünftigen Version von Visual Studio enthalten sind, finden Sie im Dialogfeld [Text Editor C++ Experimental](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) (C++-Text-Editor „Experimentell“). In Visual Studio 2017 und höher können Sie **Predictive IntelliSense** in diesem Dialogfeld aktivieren.

## <a name="see-also"></a>Weitere Informationen

[Read and understand C++ code (Lesen und Verstehen von C++-Code)](read-and-understand-code-cpp.md)</br>
[Navigate your C++ code base in Visual Studio (Navigieren in Ihrer C++-Codebasis in Visual Studio)](navigate-code-cpp.md)</br>
[Collaborate with Live Share for C++ (Zusammenarbeit über Live Share für C++)](live-share-cpp.md)
