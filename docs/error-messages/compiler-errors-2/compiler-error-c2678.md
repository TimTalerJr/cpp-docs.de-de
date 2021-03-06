---
title: Compilerfehler C2678
ms.date: 11/04/2016
f1_keywords:
- C2678
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
ms.openlocfilehash: 390752d5d34685afc8b5fc5401fd75585bb48dd0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760334"
---
# <a name="compiler-error-c2678"></a>Compilerfehler C2678

Binärer „operator“: Es wurde kein Operator definiert, der einen linksseitigen Operanden vom Typ „type“ akzeptiert (oder keine geeignete Konvertierung möglich)

Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.

## <a name="example"></a>Beispiel

C2678 kann auftreten, wenn der linke Operand konstant qualifiziert ist, der Operator jedoch definiert ist, ein nicht konstantes Argument zu verwenden.

Im folgenden Beispiel wird C2678 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2678a.cpp
// Compile by using: cl /EHsc /W4 C2678a.cpp
struct Combo {
   int number;
   char letter;
};

inline Combo& operator+=(Combo& lhs, int rhs) {
   lhs.number += rhs;
   return lhs;
}

int main() {
   Combo const combo1{ 42, 'X' };
   Combo combo2{ 13, 'Z' };

   combo1 += 6; // C2678
   combo2 += 9; // OK - operator+= matches non-const Combo
}
```

## <a name="example"></a>Beispiel

C2678 kann auch auftreten, wenn Sie ein systemeigenes Member nicht verankern, bevor Sie eine Memberfunktion dafür aufrufen.

Im folgenden Beispiel wird C2678 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2678.cpp
// compile with: /clr /c
struct S { int _a; };

ref class C {
public:
   void M( S param ) {
      test = param;   // C2678

      // OK
      pin_ptr<S> ptest = &test;
      *ptest = param;
   }
   S test;
};
```
