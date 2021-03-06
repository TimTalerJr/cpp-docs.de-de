---
title: __shiftright128
ms.date: 09/02/2019
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: a18a9958a51f291e4997c23e87ee48f739562416
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220016"
---
# <a name="__shiftright128"></a>__shiftright128

**Microsoft-spezifisch**

Verschiebt eine 128-Bit-Menge, dargestellt als zwei 64-Bit-Mengen `LowPart` und `HighPart`, um eine angegebene Anzahl von Bits, die durch `Shift` definiert wird, nach rechts und gibt die unteren 64 Bits des Ergebnisses zurück.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>Parameter

*LowPart*\
in Die unteren 64 Bits der zu Verschiebungs enden 128-Bit-Menge.

*HighPart*\
in Die hohen 64 Bits der 128-Bit-Menge, die verschoben werden soll.

*Schuss*\
in Die Anzahl der zu Verschiebungs enden Bits.

## <a name="return-value"></a>Rückgabewert

Die unteren 64 Bits des Ergebnisses.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__shiftright128`|x64|

**Header Datei** \<intrin. h->

## <a name="remarks"></a>Hinweise

Der `Shift`-Wert ist immer modulo 64. So verschiebt z. B. beim Aufrufen von `__shiftright128(0, 1, 64)` die Funktion die `0`-Bits des oberen Teils nach rechts und gibt einen unteren Teil von `0` und nicht von `1` zurück, wie man annehmen könnte.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter [__shiftleft128](../intrinsics/shiftleft128.md).

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__shiftleft128](../intrinsics/shiftleft128.md)\
[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
