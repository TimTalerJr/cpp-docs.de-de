---
title: Compilerfehler C2171
ms.date: 11/04/2016
f1_keywords:
- C2171
helpviewer_keywords:
- C2171
ms.assetid: a80343b5-ab3f-4413-b6f1-3ce9d7e519e5
ms.openlocfilehash: 7d74cec63c0fb74ed8d6589a43c3b82c94633002
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758397"
---
# <a name="compiler-error-c2171"></a>Compilerfehler C2171

„operator“: für Operanden vom Typ „type“ nicht zulässig.

Ein unärer Operator wird zusammen mit einem ungültigen Operandentyp verwendet.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2171 generiert:

```cpp
// C2171.cpp
int main() {
   double d, d1;
   d = ~d1;   // C2171

   // OK
   int d2 = 0, d3 = 0;
   d2 = ~d3;
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2171 generiert:

```cpp
// C2171_b.cpp
// compile with: /c
class A {
public:
   A() { STF( &A::D ); }

   void D() {}
   void DTF() {
      (*TF)();   // C2171
      (this->*TF)();   // OK
   }

   void STF(void (A::*fnc)()) {
      TF = fnc;
   }

private:
   void (A::*TF)();
};
```
