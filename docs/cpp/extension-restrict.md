---
title: __restrict
ms.date: 10/10/2018
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
ms.openlocfilehash: 76cdf9424e6eab33a3a92b3f98d9c2b0b04ff667
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183751"
---
# <a name="restrict"></a>__restrict

Wie die **__declspec ( [einschränken](../cpp/restrict.md) )** Modifizierer, die **"__restrict"** -Schlüsselwort Gibt an, dass ein Symbol nicht in den aktuellen Bereich ein Alias zugeordnet ist. Die **"__restrict"** Schlüsselwort unterscheidet sich von der `__declspec ( restrict )` Modifizierer auf folgende Weise:

- Die **"__restrict"** Schlüsselwort ist nur auf Variablen gültig und `__declspec ( restrict )` ist nur auf Funktionsdeklarationen und-Definitionen gültig.

- **"__restrict"** ähnelt **einschränken** aus der Spezifikation C99, aber **"__restrict"** kann verwendet werden, C++ oder C-Programmen.

- Wenn **"__restrict"** wird verwendet, der Compiler nicht weiter die kein-Alias-Eigenschaft einer Variablen. Also wenn Sie Zuweisen einer **"__restrict"** Variablen nicht **"__restrict"** Variablen, der Compiler wird immer noch, dass der nicht-__restrict-Variable, um ein Alias erforderlich. Dies unterscheidet sich vom Verhalten der **einschränken** -Schlüsselwort aus der Spezifikation C99.

Wenn Sie das Verhalten einer vollständigen Funktion beeinflussen, ist es im Allgemeinen besser, `__declspec ( restrict )` anstatt das Schlüsselwort zu verwenden.

Für die Kompatibilität mit früheren Versionen **_restrict** ist ein Synonym für **"__restrict"** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

In Visual Studio 2015 und höher **"__restrict"** kann verwendet werden, auf C++ verweisen.

> [!NOTE]
>  Wenn für eine Variable verwendet werden soll, die auch über die [flüchtige](../cpp/volatile-cpp.md) -Schlüsselwort, **flüchtige** Vorrang.

## <a name="example"></a>Beispiel

```cpp
// __restrict_keyword.c
// compile with: /LD
// In the following function, declare a and b as disjoint arrays
// but do not have same assurance for c and d.
void sum2(int n, int * __restrict a, int * __restrict b,
          int * c, int * d) {
   int i;
   for (i = 0; i < n; i++) {
      a[i] = b[i] + c[i];
      c[i] = b[i] + d[i];
    }
}

// By marking union members as __restrict, tell compiler that
// only z.x or z.y will be accessed in any given scope.
union z {
   int * __restrict x;
   double * __restrict y;
};
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)