---
title: Eigenschaftenseiten für das Tool XML-Dokument-Generator
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
ms.openlocfilehash: c99677d7fc53ae3343e15e54997fe0101322fbcf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316157"
---
# <a name="xml-document-generator-tool-property-pages"></a>Eigenschaftenseiten für das Tool XML-Dokument-Generator

Die Eigenschaftenseite des XML-Dokument-Generators stellt die Funktionen der „xdcmake.exe“ zur Verfügung. Die „xdcmake.exe“ führt XDC-Dateien in eine XML-Datei zusammen, wenn Ihr Quellcode Dokumentationskommentare enthält und [/doc (Verarbeiten von Dokumentationskommentaren) (C/C++)](doc-process-documentation-comments-c-cpp.md) angegeben ist. Informationen zum Hinzufügen von Dokumentationskommentaren in Quellcode finden Sie unter [Recommended Tags for Documentation Comments (Empfohlene Tags für Dokumentationskommentare)](recommended-tags-for-documentation-comments-visual-cpp.md).

> [!NOTE]
>  Die Optionen von „xdcmake.exe“ in der Entwicklungsumgebung (Eigenschaftenseiten) unterscheiden sich von den Optionen, wenn „xdcmake.exe“ in der Befehlszeile verwendet wird. Informationen zur Verwendung von „xdcmake.exe“ in der Befehlszeile finden Sie unter [XDCMake Reference (XDCMake-Verweis)](xdcmake-reference.md).

## <a name="uielement-list"></a>UIElement-Liste

- **Startbanner unterdrücken**

   Copyrightmeldung unterdrücken

- **Zusätzliche Dokumentdateien**

   Zusätzliche Verzeichnisse, in denen das Projektsystem nach XDC-Dateien suchen soll. XDCMake sucht immer nach XDC-Dateien, die vom Projekt generiert wurden. Mehrere Verzeichnisse können angegeben werden.

- **Ausgabedokumentdatei**

   Der Name und der Speicherort des Verzeichnisses der XML-Ausgabedatei. Finden Sie unter [gängige Makros für Buildbefehle und-Eigenschaften](common-macros-for-build-commands-and-properties.md) Informationen zur Verwendung von Makros Verzeichnispfade angeben.

- **Dokumentbibliothekabhängigkeiten**

   Wenn Ihr Projekt von einem LIB-Projekt in der Projektmappe abhängig ist, können Sie XDC-Dateien des LIB-Projekts in die XML-Dateien für das aktuelle Projekt verarbeiten.

## <a name="see-also"></a>Siehe auch

[Referenz für C++-Projekt Seite](property-pages-visual-cpp.md)