---
title: RuntimeClassBaseT-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
ms.openlocfilehash: 5d93b3e86e7ba105a42ccbedbbf44c51ada97bbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403164"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Parameter

*RuntimeClassTypeT*<br/>
Ein Feld von Flags, der angibt, eine oder mehrere [RuntimeClassType](runtimeclasstype-enumeration.md) Enumeratoren.

## <a name="remarks"></a>Hinweise

Stellt Hilfsmethoden für `QueryInterface` Vorgänge und die erste Schnittstellen-IDs.

## <a name="members"></a>Member

### <a name="protected-methods"></a>Geschützte Methoden

Name                                                         | Beschreibung
------------------------------------------------------------ | -----------------------------------------------------------------------------
[RuntimeClassBaseT::AsIID](#asiid)                           | Ruft einen Zeiger auf die angegebene Schnittstellen-ID.
[RuntimeClassBaseT::GetImplementedIIDS](#getimplementediids) | Ruft ein Array von Schnittstellen-IDs, die von einem angegebenen Typ implementiert werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`RuntimeClassBaseT`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="asiid"></a>RuntimeClassBaseT::AsIID

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Typ, die Schnittstellen-ID, die vom Parameter angegebene implementiert *Riid*.

*implements*<br/>
Eine Variable des Typs von Template-Parameter angegebenen *T*.

*riid*<br/>
Die Schnittstellen-ID abgerufen werden soll.

*ppvObject*<br/>
Wenn dieser Vorgang erfolgreich ist, wird ein Zeiger-auf-a-Zeiger auf die Schnittstelle vom-Parameter angegebenen *Riid*.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.

### <a name="remarks"></a>Hinweise

Ruft einen Zeiger auf die angegebene Schnittstellen-ID.

## <a name="getimplementediids"></a>RuntimeClassBaseT::GetImplementedIIDS

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des der *implementiert* Parameter.

*implements*<br/>
Zeiger auf den vom Parameter angegebenen Typ *T*.

*iidCount*<br/>
Die maximale Anzahl von Schnittstellen-IDs abrufen.

*iids*<br/>
Wenn dieser Vorgang erfolgreich abgeschlossen, ein Array von die Schnittstellen-IDs, die vom Typ implementiert wird *T*.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.

### <a name="remarks"></a>Hinweise

Ruft ein Array von Schnittstellen-IDs, die von einem angegebenen Typ implementiert werden.
