---
title: __thiscall
ms.date: 11/04/2016
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: e51879ae62b2881e0adadbe59859605f6cc58947
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221910"
---
# <a name="thiscall"></a>__thiscall

**Microsoft-spezifisch**

Die **__thiscall** Aufrufkonvention wird für Memberfunktionen verwendet und ist der Standardwert ein, die Aufrufkonvention C++ Memberfunktionen, die keine Variablen Argumente verwenden. Klicken Sie unter **__thiscall**, der aufgerufene entleert den Stapel, handelt es sich nicht `vararg` Funktionen. Argumente werden von rechts nach links, auf dem Stapel abgelegt, mit der **dies** Zeiger übergeben wird, über das Register "ECX" und nicht auf dem Stapel, auf die X86 Architektur.

Ein Grund für die Verwendung **__thiscall** ist in Klassen, deren Memberfunktionen `__clrcall` standardmäßig. In diesem Fall können Sie **__thiscall** auf einzelne Member von systemeigenem Code funktioniert.

Beim Kompilieren mit [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), alle Funktionen und Funktionszeiger `__clrcall` sofern nicht anders angegeben. Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

In Versionen vor Visual Studio 2005 die **__thiscall** Aufrufkonvention nicht explizit angegeben werden in einem Programm, da **__thiscall** kein Schlüsselwort war.

`vararg` Memberfunktionen der **__cdecl** Aufrufkonvention. Alle Funktionsargumente werden auf dem Stapel abgelegt, mit der **dies** Zeiger zuletzt auf dem Stapel abgelegt

Da diese Aufrufkonvention nur für C++ gültig ist, gibt es kein Schema zur C-Namensergänzung.

Auf ARM und X64 Computern **__thiscall** akzeptiert und vom Compiler ignoriert.

Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden. Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)