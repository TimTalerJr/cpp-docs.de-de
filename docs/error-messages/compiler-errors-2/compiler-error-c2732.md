---
title: Compilerfehler C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 61bac8c1b5c9e029cc5833f458669b490fed8c91
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755797"
---
# <a name="compiler-error-c2732"></a>Compilerfehler C2732

Bindungsangaben widersprechen vorheriger Angabe für 'function'

Die Funktion wurde bereits mit einem anderen Bindungsspezifizierer deklariert.

Dieser Fehler kann durch das Einbeziehen von Dateien mit unterschiedlichen Bindungsspezifizierern verursacht werden.

Um diesen Fehler zu beheben, ändern Sie die `extern`-Anweisungen, sodass die Bindungen übereinstimmen. Brechen Sie im Besonderen `#include`-Direktive nicht in `extern "C"`-Blöcke um.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2732 generiert:

```cpp
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```
