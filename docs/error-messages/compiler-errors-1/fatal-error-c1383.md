---
title: Schwerwiegender Fehler C1383
ms.date: 11/04/2016
f1_keywords:
- C1383
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
ms.openlocfilehash: 4ab96c0516ee5593a969669c03ae22f0c211ae27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208582"
---
# <a name="fatal-error-c1383"></a>Schwerwiegender Fehler C1383

Die Compileroption /GL ist nicht mit der installierten Version der Common Language Runtime kompatibel.

C1383 tritt auf, wenn Sie eine frühere Version der Common Language Runtime mit einem neueren Compiler verwenden und bei der Kompilierung **/clr** und **/GL.** verwenden.

Verwenden Sie entweder nicht **/GL** mit **/clr** , oder installieren Sie die im Lieferumfang des Compilers enthaltene Version der Common Language Runtime.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) und [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).