---
title: Compilerfehler C2369
ms.date: 11/04/2016
f1_keywords:
- C2369
helpviewer_keywords:
- C2369
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
ms.openlocfilehash: ed7bcbf24ec7ef88ec12d83af4f08b12d56b347b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745758"
---
# <a name="compiler-error-c2369"></a>Compilerfehler C2369

'Array': Neudefinition. Unterschiedliche Feldindizes

Das Array wurde bereits mit einem anderen Feldindex deklariert.

Im folgenden Beispiel wird C2369 generiert:

```cpp
// C2369.cpp
// compile with: /c
int a[10];
int a[20];   // C2369
int b[20];   // OK
```
