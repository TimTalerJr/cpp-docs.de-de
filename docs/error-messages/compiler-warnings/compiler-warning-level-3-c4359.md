---
title: Compilerwarnung (Stufe 3) C4359
ms.date: 11/04/2016
f1_keywords:
- C4359
helpviewer_keywords:
- C4359
ms.assetid: d8fe993c-ef82-45a0-a43d-c29f9d1bacdb
ms.openlocfilehash: 7da4d231a341f8d4d4e8c1e82fc1fc8b9893778a
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051608"
---
# <a name="compiler-warning-level-3-c4359"></a>Compilerwarnung (Stufe 3) C4359

' Typ ': die tatsächliche Ausrichtung (8) ist größer als der in __declspec (ausrichten ()) angegebene Wert.

Die für einen Typ angegebene Ausrichtung ist kleiner als die Ausrichtung des Typs eines seiner Datenmember.  Weitere Informationen finden Sie unter [Ausrichten](../../cpp/align-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4359 generiert.

```cpp
// C4359.cpp
// compile with: /W3 /c
struct __declspec(align(8)) C8 { __int64 i; };
struct __declspec(align(4)) C4  { C8 m8; };   // C4359
struct __declspec(align(8)) C8_b  { C8 m8; };   // OK
struct __declspec(align(16)) C16  { C8 m8; };   // OK
```