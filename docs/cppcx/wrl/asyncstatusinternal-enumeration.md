---
title: AsyncStatusInternal-Enumeration
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
ms.openlocfilehash: f12bf4aafc87e44a6e2fb15ba79de4a9744bea58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398783"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal-Enumeration

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
enum AsyncStatusInternal;
```

## <a name="remarks"></a>Hinweise

Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die `Windows::Foundation::AsyncStatus` Enumeration.

## <a name="members"></a>Member

`_Created`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Created`.

`_Started`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Started`.

`_Completed`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Completed`.

`_Cancelled`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Cancelled`.

`_Error`<br/>
Entspricht `::Windows::Foundation::AsyncStatus::Error`.

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)