---
title: Für Visual Studio C++ -Projekte erstellte Dateitypen
ms.date: 04/08/2019
helpviewer_keywords:
- header files [C++], Visual Studio projects
- ActiveX controls [C++], Help files
- def files
- project items [C++], files
- Visual Studio C++ projects, files and directories
- resource files, created by wizard
- files [C++], extensions
- Help files, for ActiveX controls
- Web projects [C++], adding items
- .def files
- licensing ActiveX controls
ms.assetid: 2b0ee2e0-ae81-4185-9bb9-11da3c99a283
ms.openlocfilehash: 078c83a9c95c1b143af2037240d5cc0a16211827
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492868"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Für Visual Studio C++ -Projekte erstellte Dateitypen

Viele Typen von Dateien sind Visual Studio-Projekten für klassische Desktop Anwendungen zugeordnet. Die in Ihrem Projekt tatsächlich enthaltenen Dateien sind vom Projekttyp und von Ihnen mithilfe eines Assistenten ausgewählten Optionen abhängig.

- [Projekt- und Projektmappendateien](project-and-solution-files.md)

- [CLR Projects (CLR-Projekte)](files-created-for-clr-projects.md)

- [ATL-Programm oder Steuern von Quell- und Headerdateien](atl-program-or-control-source-and-header-files.md)

- [MFC-Programm oder Steuern von Quell- und Headerdateien](mfc-program-or-control-source-and-header-files.md)

- [Vorkompilierte Headerdateien](../creating-precompiled-header-files.md)

- [Ressourcendateien](resource-files-cpp.md)

- [Hilfedateien (WinHelp)](help-files-winhelp.md)

- [Hinweisdateien](hint-files.md)

Wenn Sie ein Visual Studio-Projekt erstellen, können Sie es in einer neuen Projekt Mappe erstellen, oder Sie können ein Projekt zu einer vorhandenen Projekt Mappe hinzufügen. Nicht triviale Anwendungen werden häufig mit mehreren Projekten in einer Projektmappe entwickelt.

Projekte generieren für gewöhnlich entweder eine EXE- oder eine DLL-Datei. Projekte können voneinander abhängig sein. während des Buildprozesses überprüft die Visual Studio-Umgebung Abhängigkeiten sowohl innerhalb von als auch zwischen Projekten. Jedes Projekt verfügt üblicherweise über Kern Quell Code. Abhängig von der Art des Projekts sind möglicherweise viele weitere Dateien vorhanden, die verschiedene Aspekte des Projekts enthalten. Die Inhalte dieser Dateien werden durch die Dateierweiterung angegeben. Die Visual Studio-Entwicklungsumgebung verwendet die Dateierweiterungen, um zu bestimmen, wie die Dateiinhalte während eines Builds verarbeitet werden.

In der folgenden Tabelle werden allgemeine Dateien in einem Visual Studio-Projekt angezeigt und mit ihrer Dateierweiterung identifiziert.

|Dateierweiterung|Typ|Inhalt|
|--------------------|----------|--------------|
|.asmx|Quelle|Bereitstellungsdatei.|
|.asp|Source|Aktive Serverseitendatei|
|.atp|Projekt|Anwendungsvorlagen-Projektdatei.|
|.bmp, .dib, .gif, .jpg, .jpeg, .png|Ressource|Allgemeine Bilddateien.|
|.bsc|Kompilieren|Browsercodedatei.|
|. cpp,. c|Source|Haupt-Quellcodedateien für Ihre Anwendung.|
|.cur|Ressource|Cursorbitmap-Grafikdatei.|
|.dbp|Projekt|Datenbankprojektdatei.|
|.disco|Source|Dynamische Ermittlungsdokumentdatei. Verarbeitet die XML-Webdienstermittlung.|
|.exe, .dll|Projekt|Ausführbare oder Dynamic-Link Library-Dateien.|
|H|Source|Headerdatei (include).|
|.htm, .html, .xsp, .asp, .htc, .hta, .xml|Ressource|Allgemeine Webdateien.|
|.HxC|Projekt|Hilfsprojektdatei.|
|.ico|Ressource|Symbolbitmap-Grafikdatei.|
|.idb|Kompilieren|Die Zustands Datei mit Abhängigkeitsinformationen zwischen Quelldateien und Klassendefinitionen. Sie kann vom Compiler während der inkrementellen Kompilierung verwendet werden. Verwenden Sie die Compileroption [/Fd](fd-program-database-file-name.md) zum Angeben des Namens der IDB-Datei.|
|.idl|Kompilieren|Eine IDL-Datei. Weitere Informationen finden Sie im Windows SDK unter [Interface Definition (IDL) File (Schnittstellendefinitionsdatei)](/windows/win32/Rpc/the-interface-definition-language-idl-file).|
|.ilk|Verknüpfen|Datei für inkrementelle Verknüpfung. Weitere Informationen finden Sie unter [/Incremental](incremental-link-incrementally.md).|
|.map|Verknüpfen|Eine Textdatei mit Linkerinformationen. Verwenden Sie die Compileroption [/Fm](fm-name-mapfile.md) , um die MAP-Datei zu benennen. Weitere Informationen finden Sie unter [/map](map-generate-mapfile.md).|
|.mfcribbon-ms|Ressource|Eine Ressourcen Datei, die den XML-Code enthält, der die MFC-Schaltflächen, Steuerelemente und Attribute im Menüband definiert. Weitere Informationen finden Sie unter [Ribbon Designer](../../mfc/ribbon-designer-mfc.md).|
|.obj, .o||Objektdateien, kompiliert, aber nicht verknüpft.|
|.pch|Debug|Vorkompilierte Headerdatei.|
|.rc, .rc2|Ressource|[Ressourcenskriptdateien](../../windows/working-with-resource-files.md) zum Generieren von Ressourcen.|
|.sbr|Kompilieren|Zwischendatei des Quellbrowsers. Die Eingabedatei für [BSCMAKE](bscmake-options.md).|
|.sln|Lösung|Die [Projektmappen](/visualstudio/ide/solutions-and-projects-in-visual-studio) datei.|
|.suo|Lösung|Die Datei mit den Projektmappenoptionen.|
|.txt|Ressource|Eine Textdatei, in der Regel die Infodatei.|
|.vap|Projekt|Eine Visual Studio Analyzer-Projektdatei.|
|.vbg|Lösung|Eine kompatible Projektgruppendatei.|
|.vbp, .vip, .vbproj|Projekt|Die Visual Basic-Projektdatei.|
|.vcxitems|Projekt|Ein Projekt mit freigegebenen Elementen zum Freigeben von Codedateien zwischen mehreren C++-Projekten. Weitere Informationen finden Sie unter [Projekt-und Projektmappendateien](project-and-solution-files.md).|
|.vcxproj|Projekt|Die Visual Studio-Projektdatei. Weitere Informationen finden Sie unter [Projekt-und Projektmappendateien](project-and-solution-files.md).|
|.vcxproj.filters|Projekt|Wird verwendet, wenn Sie Projektmappen-Explorer zum Hinzufügen einer Datei zu einem Projekt verwenden. Die Filterdatei definiert, wo die Datei in der Projektmappen-Explorer Strukturansicht basierend auf der Dateinamenerweiterung hinzugefügt wird.|
|.vdproj|Projekt|Die Visual Studio-Bereitstellungsprojektdatei.|
|.vmx|Projekt|Die Makro-Projektdatei.|
|.vup|Projekt|Der Hilfsprogramm-Projektdatei.|

Weitere Informationen über andere mit Visual Studio verknüpfte Dateien finden Sie unter [Dateitypen und Dateierweiterungen in Visual Studio .NET](/visualstudio/ide/reference/project-and-solution-file-types).

Projektdateien sind in Ordnern im Projektmappen-Explorer organisiert. Visual Studio erstellt einen Ordner für Quelldateien, Header Dateien und Ressourcen Dateien. Sie können diese Ordner jedoch neu organisieren oder neue erstellen. Sie können Ordner verwenden, um logische Cluster von Dateien innerhalb der Hierarchie eines Projekts explizit zu organisieren. Beispielsweise könnten Sie Ordner erstellen, die alle Ihre Benutzeroberflächen-Quelldateien enthalten. Oder, Ordner für Spezifikationen, Dokumentationen oder Test Sammlungen. Alle Dateiordnernamen sollten eindeutig sein.

Wenn Sie einem Projekt ein Element hinzufügen, fügen Sie das Element allen Konfigurationen für dieses Projekt hinzu. Das Element wird hinzugefügt, unabhängig davon, ob es Erstell Bar ist. Wenn Sie beispielsweise über ein Projekt mit dem Namen „MeinProjekt“ verfügen, wird das Element durch das Hinzufügen zu den Debug- und Release-Projektkonfigurationen hinzugefügt.

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwalten von Visual C++ Studio-Projekten](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio C++ -Projekttypen](visual-cpp-project-types.md)<br>