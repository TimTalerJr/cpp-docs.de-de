---
title: ActivateInstance-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: 43aa34153f0e71dd665090243ff2288bff704404
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303969"
---
# <a name="activateinstance-function"></a>ActivateInstance-Funktion

Registriert, und ruft eine Instanz eines angegebenen Typs, der definiert, die in einer angegebenen Klasse-ID ab

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Typ, zu aktivieren.

*activatableClassId*<br/>
Der Name des Klassen-ID, die Parameter definiert *T*.

*instance*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Verweis auf eine Instanz von *T*.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, das die Ursache des Fehlers angibt.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Windows::Foundation

## <a name="see-also"></a>Siehe auch

[Windows::Foundation-Namespace](windows-foundation-namespace.md)