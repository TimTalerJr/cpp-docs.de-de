---
title: Compilerwarnung (Stufe 4) C4514
ms.date: 11/04/2016
f1_keywords:
- C4514
helpviewer_keywords:
- C4514
ms.assetid: cdae966a-9cd4-4e31-af30-2a014e68f614
ms.openlocfilehash: 9ac844e3e1bd1353f7ccbffcda8737ef0453c329
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990742"
---
# <a name="compiler-warning-level-4-c4514"></a>Compilerwarnung (Stufe 4) C4514

"Funktion": nicht referenzierte Inline Funktion wurde entfernt.

Der Optimierer hat eine Inline Funktion entfernt, die nicht aufgerufen wird.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4514 generiert:

```cpp
// C4514.cpp
// compile with: /W4
#pragma warning(default : 4514)
class A
{
   public:
      void func()   // C4514, remove the function to resolve
      {
      }
};

int main()
{
}
```
