---
title: Compilerfehler C2702
ms.date: 11/04/2016
f1_keywords:
- C2702
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
ms.openlocfilehash: 03a982ee35f0ac49a12568fc428de333f57f3ffa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758319"
---
# <a name="compiler-error-c2702"></a>Compilerfehler C2702

__except wird möglicherweise nicht in einem Beendigungs Block angezeigt.

Ein Ausnahmehandler (`__try`/`__except`) kann nicht in einem `__finally` Block geschachtelt werden.

Im folgenden Beispiel wird C2702 generiert:

```cpp
// C2702.cpp
// processor: x86 IPF
int Counter;
int main() {
   __try {}
   __finally {
      __try {}   // C2702
      __except( Counter ) {}   // C2702
   }
}
```
