---
title: Compilerfehler C2902
ms.date: 11/04/2016
f1_keywords:
- C2902
helpviewer_keywords:
- C2902
ms.assetid: 89d78d0e-78e5-4c2c-a0f9-a60110e9395e
ms.openlocfilehash: 43ba7f6ddb18d86410de852ffc3e2834083f031c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735876"
---
# <a name="compiler-error-c2902"></a>Compilerfehler C2902

"Token": Unerwartetes Token nach "Vorlage", Bezeichner erwartet.

Das auf das Schlüsselwort `template` folgende Token war kein Bezeichner.

Im folgenden Beispiel wird C2902 generiert:

```cpp
// C2902.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template + 1;   // C2902
}

void f() {
   N::template X<int> x1;   // OK
}
```

C2902 kann auch auftreten, wenn Generics verwendet werden:

```cpp
// C2902b.cpp
// compile with: /clr /c
namespace N {
   generic<class T> ref class GC {};
}

void f() {
   N::generic + 1;   // C2902
   N::generic GC<int>^ x;
}
```
