---
title: Compilerwarnung (Stufe 1) C4075
ms.date: 11/04/2016
f1_keywords:
- C4075
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
ms.openlocfilehash: b4181059a406d85514c3941ed2856d9e95673957
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626951"
---
# <a name="compiler-warning-level-1-c4075"></a>Compilerwarnung (Stufe 1) C4075

Initialisierungen stehen in nicht erkanntem Initialisierungsbereich

In einem [#pragma init_seg](../../preprocessor/init-seg.md) wird ein unbekannter Abschnittsname verwendet. Der Compiler ignoriert den **pragma** -Befehl.

Im folgenden Beispiel wird C4075 generiert:

```cpp
// C4075.cpp
// compile with: /W1
#pragma init_seg("mysegg")   // C4075

// try..
// #pragma init_seg(user)

int main() {
}
```