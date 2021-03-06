---
title: Compilerwarnung (Stufe 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: 88ed48e9bf7057c55ee4004ca1bb1eb18cd4be51
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626162"
---
# <a name="compiler-warning-level-1-c4090"></a>Compilerwarnung (Stufe 1) C4090

"Operation": unterschiedliche Modifizierer-Qualifizierer

Eine Variable, die in einem Vorgang verwendet wird, wird mit einem angegebenen Modifizierer definiert, der verhindert, dass Sie ohne Erkennung durch den Compiler geändert wird. Der Ausdruck wird ohne Änderung kompiliert.

Diese Warnung kann darauf zurückzuführen sein, dass ein Zeiger **auf eine Konstante oder ein `volatile`** Element einem Zeiger zugewiesen wird, der nicht als **Verweis auf "** Konstante" oder "`volatile`" deklariert wurde.

Diese Warnung wird für C-Programme ausgegeben. In einem C++ Programm gibt der Compiler einen Fehler aus: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

Im folgenden Beispiel wird C4090 generiert:

```c
// C4090.c
// compile with: /W1
int *volatile *p;
int *const *q;
int **r;

int main() {
   p = q;   // C4090
   p = r;
   q = p;   // C4090
   q = r;
   r = p;   // C4090
   r = q;   // C4090
}
```