---
title: Helpstringcontext (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringcontext
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
ms.openlocfilehash: ae48c6216b1f1d987b33eff50acf9d82dc551400
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501490"
---
# <a name="helpstringcontext"></a>helpstringcontext

Gibt die ID eines Hilfe Themas in einer. hlp-oder CHM-Datei an.

## <a name="syntax"></a>Syntax

```cpp
[ helpstringcontext(contextID) ]
```

### <a name="parameters"></a>Parameter

*contextID*<br/>
Ein 32-Bit-Hilfe Kontext Bezeichner in der **Hilfe** Datei.

## <a name="remarks"></a>Hinweise

Das **helpstringcontext** C++ -Attribut verfügt über die gleiche Funktionalität wie das [helpstringcontext](/windows/win32/Midl/helpstringcontext) -ODL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object, helpstring("help string"), helpstringcontext(1), uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Schnittstelle**, Schnittstellen Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[module](module-cpp.md)