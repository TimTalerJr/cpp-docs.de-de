---
title: Compilerfehler C2680
ms.date: 11/04/2016
f1_keywords:
- C2680
helpviewer_keywords:
- C2680
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
ms.openlocfilehash: 37535c9ffbafd0d312646d5f3cfdb0c4411bc790
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760308"
---
# <a name="compiler-error-c2680"></a>Compilerfehler C2680

"Typ": Ungültiger Zieltyp für Name

Ein Umwandlungs Operator hat versucht, in einen Typ zu konvertieren, der kein Zeiger oder Verweis ist. Der [dynamic_cast](../../cpp/dynamic-cast-operator.md) -Operator kann nur für Zeiger oder Verweise verwendet werden.

Im folgenden Beispiel wird C2680 generiert:

```cpp
// C2680.cpp
// compile with: /c
class A { virtual void f(); };
class B : public A {};

void g(B b) {
   A a;
   a = dynamic_cast<A>(b);   // C2680  target not a reference type
   a = dynamic_cast<A&>(b);   // OK
}
```

C2680 kann auch auftreten, wenn das Ziel nicht definiert ist:

```cpp
// C2680b.cpp
// compile with: /clr /c
// C2680 expected
using namespace System::Collections;

// Delete the following line to resolve.
ref class A;   // not defined

// Uncomment the following line to resolve.
// ref class A{};

public ref class B : ArrayList {
   property A^ C[int] {
      A^ get(int index) {
         return dynamic_cast<A^>(this->default::get(index));
      }
      void set(int index, A^ value) {
         this->default::set(index, value);
      }
   }
};
```
