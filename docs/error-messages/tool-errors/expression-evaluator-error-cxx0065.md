---
title: Ausdrucksauswertungsfehler CXX0065
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: 7b62e42da2a74d910e2dc56ce2dfcb5cb38f2bfa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299316"
---
# <a name="expression-evaluator-error-cxx0065"></a>Ausdrucksauswertungsfehler CXX0065

Variable erfordert Stapelrahmen

Ein Ausdruck enthält eine Variable, die im aktuellen Gültigkeitsbereich vorhanden ist, aber nicht noch erstellt wurde.

Dieser Fehler kann auftreten, wenn Sie der Prolog einer Funktion aber noch nicht richten Sie den Stapelrahmen der Funktion schrittweise ausführen oder Sie haben den Exitcode für die Funktion schrittweise.

Durchlaufen der Prologcode aus, bis der Stapelrahmen eingerichtet wurde, bevor die Auswertung des Ausdrucks.

Dieser Fehler ist mit CAN0065 identisch.