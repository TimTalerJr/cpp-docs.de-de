---
title: Compilerwarnung (Stufe 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 3a56e58d9bec1034a55f4e588dbddd0dba03f348
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208026"
---
# <a name="compiler-warning-level-1-c4076"></a>Compilerwarnung (Stufe 1) C4076

> "*Typmodifizierer*": kann nicht verwendet werden, mit dem Typ '*Typename*"

## <a name="remarks"></a>Hinweise

Ein Typmodifizierer kann, ob **signiert** oder **ohne Vorzeichen**, kann nicht mit einem nicht ganzzahligen Datentyp verwendet werden. *Typmodifizierer* wird ignoriert.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4076 generiert; Um dies zu beheben, entfernen Sie die **ohne Vorzeichen** Typmodifizierer:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```