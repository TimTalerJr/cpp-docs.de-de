---
title: Ressourcen
ms.date: 08/28/2019
ms.topic: article
ms.assetid: dade2f6b-c51f-4c33-9023-41956ae4b5f6
f1_keywords:
- VC.Project.VCResourceCompilerTool.PreprocessorDefinitions
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- VC.Project.VCResourceCompilerTool.Culture
- VC.Project.VCResourceCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCResourceCompilerTool.IgnoreStandardIncludePath
- VC.Project.VCResourceCompilerTool.ShowProgress
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.ResourceOutputFileName
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: 916b6615d80000d601c909f771a1ec8f1b947927
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177341"
---
# <a name="resources-property-page"></a>Ressourcen (Eigenschaften Seite)

Bei nativen Windows-Desktop Programmen ruft der Build den [Ressourcen Compiler (RC. exe)](/windows/win32/menurc/resource-compiler) auf, um der Binärdatei Bilder, Zeichen folgen Tabellen und *Res* -Dateien hinzuzufügen. Die Eigenschaften, die auf dieser Eigenschaften Seite verfügbar gemacht werden, werden an den Ressourcen Compiler C++ und nicht an den Compiler oder den Linker übermittelt. Weitere Informationen zu den hier aufgeführten Eigenschaften und deren Zuordnung zu den RC-Befehlszeilenoptionen finden Sie unter [Verwenden von RC (RC-Befehlszeile)](/windows/win32/menurc/using-rc-the-rc-command-line-). Informationen zum Zugreifen auf die Eigenschaften Seiten für **Ressourcen** finden Sie unter [festlegen C++ von Compiler-und Buildeigenschaften in Visual Studio](../working-with-project-properties.md). Informationen zum programmgesteuerten Zugriff auf diese Eigenschaften finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool>.

Eigenschaften für .NET-Ressourcen C++in/CLI-Anwendungen werden auf der Eigenschaften [Seite verwaltete Ressourcen](managed-resources-property-page.md)verfügbar gemacht.

## <a name="preprocessor-definitions"></a>Präprozessordefinitionen

Gibt eine oder mehrere Definitionen für den Ressourcen Compiler an. (/d [Makro])

## <a name="undefine-preprocessor-definitions"></a>Präprozessordefinitionen aufheben

Aufheben der Definition eines Symbols. /u

## <a name="culture"></a>Culture

Listet die in den Ressourcen verwendete Kultur (z. b. US-Englisch oder Italienisch) auf. (/l [NUM])

## <a name="additional-include-directories"></a>Zusätzliche Includeverzeichnisse

Gibt mindestens ein Verzeichnis an, das dem Include-Pfad hinzugefügt werden soll. Verwenden Sie Semikolons als Trennzeichen, wenn mehr als ein Trennzeichen verwendet wird. (/I [Pfad])

## <a name="ignore-standard-include-paths"></a>Standardincludepfade ignorieren

Verhindert, dass der Ressourcen Compiler in Verzeichnissen, die in den INCLUDE-Umgebungsvariablen angegeben sind, nach Includedateien sucht. /X

## <a name="show-progress"></a>Status anzeigen

Statusmeldungen an Ausgabefenster senden. /v

## <a name="suppress-startup-banner"></a>Startbanner unterdrücken

Unterdrücken der Anzeige des Start Banners und der Informations Meldung (/nologo)

## <a name="resource-file-name"></a>Ressourcen Dateiname

Gibt den Namen der Ressourcen Datei an (/FO [File]).

## <a name="null-terminate-strings"></a>NULL-Zeichen folgen beenden 

Fügen Sie NULL an alle Zeichen folgen in den Zeichen folgen Tabellen an. /n

## <a name="see-also"></a>Siehe auch

[C++Referenz zur Projekteigenschaften Seite](property-pages-visual-cpp.md)