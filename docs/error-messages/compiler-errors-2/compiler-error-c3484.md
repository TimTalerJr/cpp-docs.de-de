---
title: Compilerfehler C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: c9895a3e5a8ae7e941fccde2da85fedfb3d2c6dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743119"
---
# <a name="compiler-error-c3484"></a>Compilerfehler C3484

Vor dem Rückgabetyp wird '->' erwartet.

Sie müssen vor dem Rückgabetyp eines Lambdaausdrucks `->` bereitstellen.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Stellen Sie `->` vor dem Rückgabetyp bereit.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Fehler C3484 generiert:

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C3484 durch Bereitstellen von `->` vor dem Rückgabetyp des Lambdaausdrucks behoben:

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)
