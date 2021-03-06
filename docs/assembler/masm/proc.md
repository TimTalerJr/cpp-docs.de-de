---
title: PROC
ms.date: 12/06/2019
f1_keywords:
- PROC
helpviewer_keywords:
- PROC directive
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
ms.openlocfilehash: 85d9a1e82eebcd83cb0f12f5ca751ec9415af18d
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318669"
---
# <a name="proc"></a>PROC

Markiert den Anfang und das Ende eines Prozedur Blocks namens *Bezeichnung*. Die Anweisungen im-Block können mit der Aufruf [Anweisung oder der](invoke.md) **Aufruf** Direktive aufgerufen werden.

## <a name="syntax"></a>Syntax

> *Label* **proc** ⟦*Distance*⟧ ⟦*Language-Type*⟧ ⟦ **Public** | **private** | **Export** ⟧ ⟦ __\<__ *prologuearg* __>__ ⟧ ⟦**verwendet** *reglist*⟧ ⟦ __,__ *Parameter* ⟦ __:__ *Tag*⟧... ⟧\
> ⟦**Frame** ⟦ __:__ *ehandler-Address*⟧ ⟧ \
> *Anweisungen*\
> *Bezeichnung* **ENDP**

## <a name="remarks"></a>Hinweise

Die ⟦*Distance*⟧-und ⟦*Language-Type*⟧-Argumente sind nur in 32-Bit-MASM gültig.

⟦**Frame** ⟦ __:__ *ehandler-Address*⟧ ⟧ ist nur mit ml64. exe gültig und bewirkt, dass MASM einen Funktionstabellen Eintrag in. pdata generiert und Informationen in. XData für die strukturierte Ausnahmebehandlung beim Entladen einer Funktion entlädt.

Wenn das **Frame** -Attribut verwendet wird, muss ihm ein gefolgt werden [. ENDPROLOG](dot-endprolog.md) -Direktive.

Weitere Informationen zur Verwendung von "ml64. exe" finden Sie unter [MASM für x64 (ml64. exe)](masm-for-x64-ml64-exe.md) .

## <a name="example"></a>Beispiel

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

Der obige Code gibt die folgende Funktions Tabelle und Entladungs Informationen aus:

```Output
FileHeader->Machine 34404
Dumping Unwind Information for file ex2.exe

.pdata entry 1 0x00001000 0x00001023

  Unwind data: 0x00002000

    Unwind version: 1
    Unwind Flags: None
    Size of prologue: 0x08
    Count of codes: 3
    Frame register: rbp
    Frame offset: 0x0
    Unwind codes:

      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00
      Code offset: 0x05, ALLOC_SMALL, size=0x10
      Code offset: 0x01, PUSH_NONVOL, register=rbp
```

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
