---
title: Compilerwarnung (Stufe 1) C4162
ms.date: 11/04/2016
f1_keywords:
- C4162
helpviewer_keywords:
- C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
ms.openlocfilehash: 7e70898065a40a965b08b090bc59263acd918515
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624849"
---
# <a name="compiler-warning-level-1-c4162"></a>Compilerwarnung (Stufe 1) C4162

"Bezeichner": keine Funktion mit C-Verknüpfung gefunden

Eine Funktion mit C-Verknüpfung ist deklariert, kann jedoch nicht gefunden werden.

Kompilieren Sie in einer c-Datei (Aufrufen des c-Compilers), um diese Warnung zu beheben.  Wenn Sie den C++ Compiler aufrufen müssen, platzieren Sie extern "C" vor der Funktionsdeklaration.

Im folgenden Beispiel wird C4162 generiert.

```cpp
// C4162.cpp
// compile with: /c /W1
unsigned char _bittest(long* a, long b);
#pragma intrinsic (_bittest)   // C4162

int main() {
   bool bit;
   long num = 78002;
   bit = _bittest(&num, 5);
}
```

Mögliche Lösung:

```cpp
// C4162b.cpp
// compile with: /c
extern "C"
unsigned char _bittest(long* a, long b);
#pragma intrinsic (_bittest)

int main() {
   bool bit;
   long num = 78002;
   bit = _bittest(&num, 5);
}
```