---
title: Compilerwarnung (Stufe 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 893364183594782b825377f57fa4e525338d62d8
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052561"
---
# <a name="compiler-warning-level-1-c4630"></a>Compilerwarnung (Stufe 1) C4630

"Symbol": der Speicherklassenspezifizierer "extern" ist für die Element Definition unzulässig.

Ein Datenmember oder eine Member-Funktion wird als `extern`definiert. Member können nicht extern sein, auch wenn ganze Objekte dies möglich sind. Der Compiler ignoriert das `extern`-Schlüsselwort. Im folgenden Beispiel wird C4630 generiert:

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```