---
title: Uidefault (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uidefault
helpviewer_keywords:
- uidefault attribute
ms.assetid: 200de0e0-2e34-40a2-bae4-8d485a62264d
ms.openlocfilehash: b4090011aade4ebab2f5c07a8e56e91253cc7c49
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513898"
---
# <a name="uidefault"></a>uidefault

Gibt an, dass der Typinformationsmember der Standard Member für die Anzeige in der Benutzeroberfläche ist.

## <a name="syntax"></a>Syntax

```cpp
[uidefault]
```

## <a name="remarks"></a>Hinweise

Das **Uidefault** C++ -Attribut verfügt über die gleiche Funktionalität wie das [Uidefault](/windows/win32/Midl/uidefault) -Attribut "Mittel".

## <a name="example"></a>Beispiel

Der folgende Code zeigt ein Beispiel für **Uidefault**:

```cpp
// cpp_attr_ref_uidefault.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom{
   HRESULT Custom([in] long l, [out, retval] long *pLong);
   [uidefault]HRESULT id0([in] long l);
   [uidefault]HRESULT id1([in] long l);

   [uidefault, propget] HRESULT get_y(int *y);
   [uidefault, propput] HRESULT put_y(int y);
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)