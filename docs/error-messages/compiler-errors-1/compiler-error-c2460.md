---
title: Compilerfehler C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: a7d20a7658a75a492e19b9e81acaa3b6fce5cae7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743938"
---
# <a name="compiler-error-c2460"></a>Compilerfehler C2460

"Bezeichner1": verwendet "Bezeichner2", das definiert wird.

Eine Klasse oder Struktur (`identifier2`) ist als Member von sich selbst (`identifier1`) deklariert. Rekursive Definitionen von Klassen und Strukturen sind nicht zulässig.

Im folgenden Beispiel wird C2460 generiert:

```cpp
// C2460.cpp
class C {
   C aC;    // C2460
};
```

Verwenden Sie stattdessen einen Zeiger Verweis in der-Klasse.

```cpp
// C2460.cpp
class C {
   C * aC;    // OK
};
```
