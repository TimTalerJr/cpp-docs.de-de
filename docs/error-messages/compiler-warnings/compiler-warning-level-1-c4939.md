---
title: Compilerwarnung (Stufe 1) C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: c2c8f794356ea429f7cf647af18e06e7ebe9183e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050278"
---
# <a name="compiler-warning-level-1-c4939"></a>Compilerwarnung (Stufe 1) C4939

\#Pragma vtordisp ist veraltet und wird in einer zukünftigen Version von Visual entferntC++

Das [vtordisp](../../preprocessor/vtordisp.md) -Pragma wird in einer der nächsten Versionen von Visual C++ entfernt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4939 generiert.

```cpp
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```