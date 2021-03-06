---
title: VerifyInterfaceHelper-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
ms.openlocfilehash: cdd0272953b2399cd71efe207eb1c56e5de154e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398094"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper-Struktur

Unterstützt die Windows Runtime C++ Template Library-Infrastruktur, und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>Parameter

*I*<br/>
Eine Schnittstelle, um zu überprüfen.

*isWinRTInterface*

## <a name="remarks"></a>Hinweise

Überprüft, ob die die Template-Parameter angegebene Schnittstelle bestimmte Anforderungen erfüllt.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

Name                                            | Beschreibung
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[VerifyInterfaceHelper::Verify-Methode](#verify) | Überprüft, ob die Schnittstelle, die durch den aktuellen Vorlagenparameter angegeben bestimmte Anforderungen erfüllt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`VerifyInterfaceHelper`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="verify"></a>VerifyInterfaceHelper::Verify

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static void Verify();
```

### <a name="remarks"></a>Hinweise

Überprüft, ob die Schnittstelle, die durch den aktuellen Vorlagenparameter angegeben bestimmte Anforderungen erfüllt.
