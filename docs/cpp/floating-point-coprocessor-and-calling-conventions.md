---
title: Gleitkomma-Coprozessor und Aufrufkonventionen
ms.date: 11/04/2016
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
ms.openlocfilehash: 7e9184d66bde26ab0e2b345f8f10c2e28619fd2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154242"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>Gleitkomma-Coprozessor und Aufrufkonventionen

Wenn Sie Assemblyroutinen für den zeigen Coprozessor Assembly schreiben sind, müssen Sie beibehalten, die floating-Steuerwort zeigen und den koprozessorstapel bereinigen, es sei denn, die Sie zurückgeben möchten eine **"float"** oder **doppelte** Wert (der die Funktion in St(0) zurückgeben sollte.

## <a name="see-also"></a>Siehe auch

[Aufrufkonventionen](../cpp/calling-conventions.md)