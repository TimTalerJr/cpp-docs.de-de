---
title: Exportieren aus einer DLL mithilfe von DEF-Dateien
ms.date: 05/06/2019
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
ms.openlocfilehash: 92a140c6491e9e3f0d356509862dee39ebe3fae6
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220786"
---
# <a name="exporting-from-a-dll-using-def-files"></a>Exportieren aus einer DLL mithilfe von DEF-Dateien

Eine Moduldefinitionsdatei oder DEF-Datei (*.def) ist eine Textdatei mit der eine oder mehrere Module-Anweisungen, die verschiedene Attribute einer DLL beschreiben. Wenn Sie nicht verwenden, werden die **"__declspec(dllexport)" "** Schlüsselwort zum Exportieren von DLL Funktionen die DLL benötigt eine Definitionsdatei.

Eine minimale Definitionsdatei muss die folgenden moduldefinitionsanweisungen enthalten:

- Die erste Anweisung in der Datei muss die LIBRARY-Anweisung sein. Diese Anweisung gibt die Zugehörigkeit zu einer DLL die DEF-Datei. Auf die LIBRARY-Anweisung folgt der Name der DLL. Der Linker speichert diesen Namen in der Importbibliothek der DLL.

- Durch die EXPORTS-Anweisung werden die Namen und optional die Ordinalwerte der von der DLL exportierten Funktionen aufgelistet. Sie weisen der Funktion einen Ordinalwert zu, indem Sie dem Funktionsnamen ein @-Zeichen und eine Zahl nachstellen. Die Ordinalzahlen müssen sich in einem Bereich von 1 bis N befinden, wobei N die Gesamtzahl der von der DLL exportierten Funktionen angibt. Wenn Sie Funktionen anhand der Ordinalzahl exportieren möchten, finden Sie unter [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über Namen](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) sowie in diesem Thema.

Die DEF-Datei für eine DLL, die den Code für die Implementierung einer binären Suchstruktur enthält, könnte z. B. folgendermaßen aussehen:

```
LIBRARY   BTREE
EXPORTS
   Insert   @1
   Delete   @2
   Member   @3
   Min   @4
```

Bei Verwendung der [MFC DLL-Assistenten](../mfc/reference/mfc-dll-wizard.md) zum Erstellen einer MFC-DLL der Assistent eine DEF-Gerüstdatei für Sie erstellt und automatisch wieder zu Ihrem Projekt hinzugefügt. Fügen Sie die Namen der zu exportierenden Funktionen in diese Datei ein. Erstellen Sie für MFC - fremde DLLs die DEF-Datei selbst, und fügen sie dem Projekt hinzu. Navigieren Sie zu **Projekt** > **Eigenschaften** > **Linker** > **Eingabe**  >  **Moduldefinitionsdatei** und geben Sie den Namen der DEF-Datei. Wiederholen Sie diesen Schritt für jede Konfiguration und Plattform, oder führen Sie es auf einmal dazu **Configuration = alle Konfigurationen**, und **Plattform = alle Plattformen**.

Wenn Sie Funktionen in einer C++-Datei exportieren, müssen Sie entweder die ergänzten Namen in der DEF-Datei zu platzieren oder die exportierten Funktionen mit standard-C-Bindung definieren, indem Sie die Verwendung von Extern "C". Wenn Sie die ergänzten Namen in der DEF-Datei angeben müssen, können Sie sie abrufen, indem Sie mit der [DUMPBIN](../build/reference/dumpbin-reference.md) tool oder mit der Linker [/MAP](../build/reference/map-generate-mapfile.md) Option. Beachten Sie, dass die vom Compiler erzeugten, ergänzten Namen compilerspezifisch sind. Setzen Sie das Microsoft produzierten ergänzten Namen C++ -Compiler (MSVC) in einer DEF-Datei, Anwendungen, die mit der DLL verknüpft müssen auch erstellt werden mit derselben Version von MSVC, so dass die ergänzten Namen in der aufrufenden Anwendung mit die exportierten Namen in übereinstimmen die DLLs DEF-Datei. 

> [!NOTE]
> Eine DLL, die mit Visual Studio 2015 erstellte kann von Anwendungen, die mit Visual Studio 2017 oder Visual Studio-2019 genutzt werden.

Wenn Sie erstellen eine [Erweiterungs-DLL](../build/extension-dlls-overview.md), und Exportieren mit einer DEF-Datei, platzieren Sie den folgenden Code am Anfang und Ende der Headerdateien ein, die die exportierten Klassen enthalten:

```
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

Diese Zeilen stellen Sie sicher, dass MFC-Variablen, die intern verwendet oder hinzugefügt werden, Ihre Klassen, werden exportiert (oder nicht importiert), von der MFC-Erweiterungs-DLL. Wenn Sie z. B. eine Klasse mithilfe von `DECLARE_DYNAMIC` ableiten, wird das Makro erweitert und Ihrer Klasse wird eine Membervariable `CRuntimeClass` hinzugefügt. Ohne diese vier Zeilen wird die DLL u. U. nicht einwandfrei kompiliert bzw. verknüpft, oder es tritt ein Fehler auf, wenn die Clientanwendung mit der DLL verknüpft wird.

Beim Erstellen der DLL, verwendet der Linker die DEF-Datei, um eine Exportdatei (.exp) zu erstellen und einer Importdatei für die Bibliothek (.lib). Anschließend verwendet der Linker die Exportdatei zum Erstellen der DLL-Datei. Ausführbare, implizit mit der DLL verknüpfte Dateien werden bei ihrer Erstellung mit der Importbibliothek verknüpft.

Beachten Sie, dass MFC selbst DEF-Dateien verwendet, um die Funktionen und Klassen aus MFCx0.dll zu exportieren.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Exportieren von C-Funktionen für die Verwendung in ausführbaren C oder C++-Dateien](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Bestimmen Sie die Exportmethode verwendet werden](determining-which-exporting-method-to-use.md)

- [Importieren in eine Anwendung mithilfe von __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Initialisieren einer DLL](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [DEF-Dateien](reference/module-definition-dot-def-files.md)

- [Regeln für moduldefinitionsanweisungen](reference/rules-for-module-definition-statements.md)

- [Ergänzte Namen](reference/decorated-names.md)

- [Importieren und Exportieren von Inlinefunktionen](importing-and-exporting-inline-functions.md)

- [Gegenseitige Importe](mutual-imports.md)

## <a name="see-also"></a>Siehe auch

[Exportieren aus einer DLL](exporting-from-a-dll.md)
