---
title: CompareStringOrdinal-Methode
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: a1ac0576bdd374daa5cbd445af480e7652b61e45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398705"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>Parameter

*lhs*<br/>
Das erste HSTRING, verglichen werden soll.

*rhs*<br/>
Das zweite HSTRING, verglichen werden soll.

## <a name="return-value"></a>Rückgabewert

|Wert|Bedingung|
|-----------|---------------|
|-1|*LHS* ist kleiner als *RS*.|
|0|*LHS* gleich *RS*.|
|1|*LHS* ist größer als *RS*.|

## <a name="remarks"></a>Hinweise

Vergleicht zwei angegebene HSTRING-Objekte und gibt eine ganze Zahl, die ihre relative Position in einer Sortierreihenfolge angibt.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::Details-Namespace](microsoft-wrl-wrappers-details-namespace.md)