---
title: Compilerwarnung (Stufe 4) C4408
ms.date: 11/04/2016
f1_keywords:
- C4408
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
ms.openlocfilehash: 27d3bb7b66b3f3d5ce4e48b56c7e3ae2a71cf115
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990898"
---
# <a name="compiler-warning-level-4-c4408"></a>Compilerwarnung (Stufe 4) C4408

"anonymousstruct" oder "Union" hat keine Datenmember deklariert.

Eine anonyme Struktur oder Union muss mindestens einen Datenmember aufweisen.

Im folgenden Beispiel wird C4408 generiert:

```cpp
// C4408.cpp
// compile with: /W4 /LD
static union
{
   // int i;
};
// a named union can have no data members
// } MyUnion;
```
