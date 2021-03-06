---
title: Compilerwarnung (Stufe 1) C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 195e5532b6555210077e43ad3086ee3106f3e757
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966009"
---
# <a name="compiler-warning-level-1-c4461"></a>Compilerwarnung (Stufe 1) C4461

'Typ' : Diese Klasse hat einen Finalizer 'Finalizer', jedoch keinen Destruktor 'dtor'

Das Vorhandensein eines Finalizers in einem Typ impliziert, dass zu löschende Ressourcen vorhanden sind. Sofern ein Finalizer nicht explizit durch den Destruktor des Typs aufgerufen wird, ermittelt die Common Language Runtime den Zeitpunkt für die Ausführung des Finalizers, nachdem der Gültigkeitsbereich des Objekts verlassen wurde.

Wenn Sie einen Destruktor in einem Typ definieren und den Finalizer explizit im Destruktor aufrufen, können Sie auf diese Weise den Ausführungszeitpunkt des Finalizers eindeutig festlegen.

Weitere Informationen finden Sie unter [debugtoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4461 generiert.

```cpp
// C4461.cpp
// compile with: /W1 /clr /c
ref class A {
protected:
   !A() {}   // C4461
};

// OK
ref struct B {
   ~B() {
      B::!B();
   }

   !B() {}
};
```