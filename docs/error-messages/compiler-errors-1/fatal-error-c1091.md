---
title: Schwerwiegender Fehler C1091
ms.date: 11/04/2016
f1_keywords:
- C1091
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
ms.openlocfilehash: 9758d4b779f4727012041da60632bcea8ce18d42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208532"
---
# <a name="fatal-error-c1091"></a>Schwerwiegender Fehler C1091

Compilerlimit: Die Zeichenfolge überschreitet die Länge um "Länge" Bytes.

Eine Zeichenfolgekonstante hat die aktuelle Grenze für die Länge von Zeichenfolgen überschritten.

Teilen Sie ggf. die statische Zeichenfolge in zwei (oder mehr) Variablen auf und verwenden Sie [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) , um das Ergebnis im Rahmen der Deklaration oder während der Laufzeit zusammenzuführen.