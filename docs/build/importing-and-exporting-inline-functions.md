---
title: Importieren und Exportieren von Inlinefunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
ms.openlocfilehash: ed523d84228124d4a8d99e443c0c744f362f1c56
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273442"
---
# <a name="importing-and-exporting-inline-functions"></a>Importieren und Exportieren von Inlinefunktionen

Importierte Funktionen können als Inline definiert werden. Die Wirkung gleicht ungefähr identisch mit eine standard-Funktion Inline zu definieren; Aufrufe der Funktion werden als Inlinecode, ähnlich wie ein Makro erweitert. Dies eignet sich hauptsächlich als eine Methode zur Unterstützung von C++ in einer DLL Klassen dieser ggf. Inline einiger ihrer Member-Funktionen für Effizienz.

Ein Feature von importierten Inlinefunktion ist, dass Sie die Adresse in C++ durchführen können. Der Compiler gibt die Adresse der Kopie der Inlinefunktion, die in der DLL zurück. Ein weiteres Feature von importierten Inlinefunktionen ist, dass Sie die statische lokale Daten der importierten Funktion, im Gegensatz zu globalen importierten Daten initialisieren können.

> [!CAUTION]
>  Sie sollte Sorgfalt walten, wenn Inlinefunktionen Bereitstellung importiert werden, da sie die Möglichkeit, Konflikte zwischen Versionen erstellt werden können. Eine Inlinefunktion Ruft im Anwendungscode erweitert. aus diesem Grund, wenn Sie später die Funktion umschreiben, wird es nicht aktualisiert, wenn die Anwendung selbst neu kompiliert wird. (In der Regel können DLL-Funktionen aktualisiert werden ohne Neuerstellung von Anwendungen, die sie verwenden.)

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Exportieren aus einer DLL](exporting-from-a-dll.md)

- [Exportieren Sie aus einer DLL. DEF-Dateien](exporting-from-a-dll-using-def-files.md)

- [Exportieren Sie aus einer DLL mithilfe von __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](exporting-and-importing-using-afx-ext-class.md)

- [Exportieren von C++-Funktionen für die Verwendung in ausführbaren c-Dateien](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Bestimmen Sie die Exportmethode verwendet werden](determining-which-exporting-method-to-use.md)

- [Importieren in eine Anwendung mithilfe von __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>Siehe auch

[Importieren und Exportieren](importing-and-exporting.md)
