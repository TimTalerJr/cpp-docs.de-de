---
title: Compilerfehler C2120
ms.date: 11/04/2016
f1_keywords:
- C2120
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
ms.openlocfilehash: 6b188f4f3e898a17a5f8fbeafaa2d1c3c6e08552
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737971"
---
# <a name="compiler-error-c2120"></a>Compilerfehler C2120

"void" mit allen Typen unzulässig

Der `void`-Typ wird in einer Deklaration mit einem anderen Typ verwendet.

Im folgenden Beispiel wird C2120 generiert:

```cpp
// C2120.cpp
int main() {
   void int i;   // C2120
   int j;   // OK
}
```
