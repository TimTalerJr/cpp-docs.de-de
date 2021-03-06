---
title: Compilerwarnung C4950
ms.date: 11/04/2016
f1_keywords:
- C4950
helpviewer_keywords:
- C4950
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
ms.openlocfilehash: 784179af68ff55ba70c61255c88688105ecb1738
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208095"
---
# <a name="compiler-warning-c4950"></a>Compilerwarnung C4950

„type_or_member“: als veraltet markiert.

Ein Member oder Typ wurde mit als veraltet markiert die <xref:System.ObsoleteAttribute> Attribut.

C4950 wird immer als Fehler ausgegeben. Sie können diese Warnung deaktivieren, mit der [Warnung](../../preprocessor/warning.md) Pragma-Direktive oder [/WD](../../build/reference/compiler-option-warning-level.md) -Compileroption.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4950 generiert.

```cpp
// C4950.cpp
// compile with: /clr
using namespace System;

// Any reference to Func3 should generate an error with message
[System::ObsoleteAttribute("Will be removed in next version", true)]
Int32 Func3(Int32 a, Int32 b) {
   return (a + b);
}

int main() {
   Int32 MyInt3 = ::Func3(2, 2);   // C4950
}
```