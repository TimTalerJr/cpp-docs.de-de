---
title: Compilerwarnung (Stufe 4) C4559
ms.date: 08/27/2018
f1_keywords:
- C4559
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
ms.openlocfilehash: afb4fb493c7c3e34ca691720a30d74517b0ab5b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220872"
---
# <a name="compiler-warning-level-4-c4559"></a>Compilerwarnung (Stufe 4) C4559

> "*Funktion*": Neudefinition; die Funktion Gewinne __declspec (*Modifizierer*)

## <a name="remarks"></a>Hinweise

Eine Funktion neu definiert wurde, oder erneut deklariert und die zweite Definition oder Deklaration hinzugefügt. eine **__declspec** Modifizierer (*Modifizierer*). Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, löschen Sie eine der Definitionen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4559 generiert:

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```