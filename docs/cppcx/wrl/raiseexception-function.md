---
title: RaiseException-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: 08305c5d59d7e272aac87ad9aa183c8e82588632
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62231352"
---
# <a name="raiseexception-function"></a>RaiseException-Funktion

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>Parameter

*hr*<br/>
Der Ausnahmecode, der die Ausnahme ausgelöst wird; d. h. das HRESULT des einen fehlgeschlagenen Vorgang.

*dwExceptionFlags*<br/>
Ein Flag, der angibt, ein vernachlässigbare Ausnahme (der Flagwert ist 0 (null)), oder eine noncontinuable Ausnahme (Flag-Wert ungleich NULL ist). Standardmäßig ist die Ausnahme nicht fortsetzbare.

## <a name="remarks"></a>Hinweise

Löst eine Ausnahme aus, in dem aufrufenden Thread aus.

Weitere Informationen finden Sie in der Windows `RaiseException` Funktion.

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)