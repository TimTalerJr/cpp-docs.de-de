---
title: Compilerfehler C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: 1d82d367c5b77f54548403b7b142aa740919b6c2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756564"
---
# <a name="compiler-error-c3465"></a>Compilerfehler C3465

Um den Typ 'typ' zu verwenden, müssen Sie auf die Assembly 'assembly' verweisen.

Typweiterleitung funktioniert im Fall einer Clientanwendung bis zur erneuten Kompilierung des Clients. Bei der erneuten Kompilierung benötigen Sie einen Verweis auf jede Assembly, die die Definition eines in Ihrer Clientanwendung verwendeten Typs enthält.

Weitere Informationen finden Sie unter [TypweiterleitungC++(/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel erstellt eine Assembly, die den neuen Speicherort eines Typs enthält.

```cpp
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Assembly erstellt, die ursprünglich die Definition des Typs enthielt, jetzt jedoch Weiterleitungssyntax für den Typ enthält.

```cpp
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3465 generiert:

```cpp
// C3465_c.cpp
// compile with: /clr
// C3465 expected
#using "C3465_b.dll"
// Uncomment the following line to resolve.
// #using "C3465.dll"

int main() {
   R^ r = gcnew R();
}
```
