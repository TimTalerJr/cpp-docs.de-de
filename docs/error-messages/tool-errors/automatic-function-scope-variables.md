---
title: Automatische Variablen (Funktionsgültigkeitsbereich)
ms.date: 04/22/2019
helpviewer_keywords:
- automatic variables
- variables, automatic
- functions [C++], scope
- scope, declared within functions
ms.assetid: 6e1a14c2-1fb0-4937-8628-8d963cc35ed4
ms.openlocfilehash: 60dcfe61be24516b96054532931fb65245ab31d0
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856691"
---
# <a name="automatic-function-scope-variables"></a>Automatische Variablen (Funktionsgültigkeitsbereich)

Eine Variable, die innerhalb einer Funktion deklariert, kann nur innerhalb des Bereichs dieser Funktion verwendet werden.

```cpp
// LNK2019_AV.cpp
// compile with: /c
void test(void);

static int lnktest3 = 3;
int lnktest4 = 4;

int main() {
   static int lnktest1 = 1;
   int lnktest2 = 2;
   test();
}
```

Und dann

```cpp
// LNK2019_AV_2.cpp
// compile with: LNK2019_AV.cpp
// LNK2019 expected
extern int lnktest1;
extern int lnktest2;
extern int lnktest3;
extern int lnktest4;

void test(void) {
   int i = 0;
   i = lnktest1;
   i = lnktest2;
   i = lnktest3;
   i = lnktest4;   // OK
}
```

## <a name="see-also"></a>Siehe auch

[Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)