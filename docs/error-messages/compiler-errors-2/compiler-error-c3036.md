---
title: Compilerfehler C3036
ms.date: 11/04/2016
f1_keywords:
- C3036
helpviewer_keywords:
- C3036
ms.assetid: 10c6993e-bc42-4a07-85c7-cdc34ac30906
ms.openlocfilehash: daf3730f6ad294dcdb3d1d944c320862d5fb80da
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755004"
---
# <a name="compiler-error-c3036"></a>Compilerfehler C3036

"Operator": Ungültiges Operatortoken in der "reduction"-Klausel von OpenMP.

Eine [reduction](../../parallel/openmp/reference/reduction.md) -Klausel wurde nicht ordnungsgemäß angegeben.

Im folgenden Beispiel wird C3036 generiert:

```cpp
// C3036.cpp
// compile with: /openmp
static float a[1000], b[1000], c[1000];
void test1(int first, int last) {
   static float dp = 0.0f;
   #pragma omp for nowait reduction(.:dp)   // C3036
   // try the following line instead
   // #pragma omp for nowait reduction(+: dp)
   for (int i = first ; i <= last ; ++i)
      dp += a[i] * b[i];
}
```
