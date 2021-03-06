---
title: stdext-Namespace
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: d40f3f7a99db72784cc9a32a9c37064228597d34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412422"
---
# <a name="stdext-namespace"></a>stdext-Namespace

Mitglieder der [ \<Hash_map >](../standard-library/hash-map.md) und [ \<Hash_set >](../standard-library/hash-set.md) -Headerdateien sind nicht Teil der ISO-Datei C++ standard. Daher wurden diese Typen und Member aus dem `std` -Namespace in den `stdext`-Namespace verschoben, um dem C++-Standard zu entsprechen.

Beim Kompilieren mit [/Ze](../build/reference/za-ze-disable-language-extensions.md), dies ist die Standardeinstellung, der Compiler eine Warnung aus, für die Verwendung von `std` für Mitglieder der \<Hash_map > und \<Hash_set > Headerdateien. Verwenden Sie das [warning](../preprocessor/warning.md) -Pragma, um die Warnung zu deaktivieren.

Damit den Compiler generiert einen Fehler für die Verwendung von `std` für Mitglieder der \<Hash_map > und \<Hash_set > Headerdateien mit **/Ze**, fügen Sie die folgende Anweisung vor der `#include` alle C++ Standard-Bibliothek-Header-Dateien.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

Beim Kompilieren mit **/Za**, generiert der Compiler einen Fehler.

## <a name="see-also"></a>Siehe auch

[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)
