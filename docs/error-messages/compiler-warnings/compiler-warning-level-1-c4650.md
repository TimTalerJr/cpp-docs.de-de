---
title: Compilerwarnung (Stufe 1) C4650
ms.date: 11/04/2016
f1_keywords:
- C4650
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
ms.openlocfilehash: ea3f1b6e792239692960e74c8360c6c3a1323815
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393531"
---
# <a name="compiler-warning-level-1-c4650"></a>Compilerwarnung (Stufe 1) C4650

die Debuginformationen nicht in vorkompilierter Headerdatei vorhanden; nur globale Symbole aus dieser Datei werden verfügbar sein.

Die vorkompilierte Headerdatei wurde nicht mit Microsoft symbolische Debuginformationen kompiliert.

Wenn verknüpft, berücksichtigt die resultierende ausführbare Datei oder eine Dynamic Link Library-Datei keine Debuginformationen für das lokale Symbole in der vorkompilierten Headerdatei.

Diese Warnung kann vermieden werden, durch das erneute Kompilieren der vorkompilierten Headerdatei mit dem ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) Befehlszeilenoption.