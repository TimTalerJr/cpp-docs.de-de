---
title: Compilerfehler C3117
ms.date: 11/04/2016
f1_keywords:
- C3117
helpviewer_keywords:
- C3117
ms.assetid: dceee392-d4c7-4599-b75e-7aaac7c36fdd
ms.openlocfilehash: 6ef04eca5c059ce1544b62addcaeb0510697d658
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741169"
---
# <a name="compiler-error-c3117"></a>Compilerfehler C3117

"% $S": eine Schnittstelle kann nur eine Basisklasse haben.

Sie haben eine Schnittstelle deklariert, die von mehreren Basisklassen erbt.

Im folgenden Beispiel wird C3117 generiert:

```cpp
// C3117.cpp
#include <windows.h>

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I1
{
};

[ object, uuid("00000000-0000-0000-0000-000000000002") ]
__interface I2
{
};

[ object, uuid("00000000-0000-0000-0000-000000000003") ]
__interface I3 : I1, I2
{   // C3117
};
```
