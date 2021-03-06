---
title: CAnimationVariableChangeHandler-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 92189ce5ea76811496d4462aa4254bbd03ebb219
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338141"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler-Klasse

Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn sich der Wert einer Animationsvariablen ändert.

## <a name="syntax"></a>Syntax

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Erstellt ein `CAnimationVariableChangeHandler`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|Erstellt eine Instanz des `CAnimationVariableChangeHandler` Objekt.|
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|Wird aufgerufen, wenn ein Wert einer Animationsvariablen geändert wurde. (Überschreibt `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.)|
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.|

## <a name="remarks"></a>Hinweise

Dieser Ereignishandler erstellt und übergeben `IUIAnimationVariable::SetVariableChangeHandler` Methode, die beim Aufrufen `CAnimationVariable::EnableValueChangedEvent` oder `CAnimationBaseObject::EnableValueChangedEvent` (wodurch dieses Ereignis für alle Animationsvariablen in ein Animationsobjekt gekapselt).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="onvaluechanged"></a>  CAnimationVariableChangeHandler::OnValueChanged

Wird aufgerufen, wenn ein Wert einer Animationsvariablen geändert wurde.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>Parameter

*storyboard*<br/>
Das Storyboard, das die Variable animiert wird.

*variable*<br/>
Die Animationsvariable, die aktualisiert wurde.

*newValue*<br/>
Der neue Wert.

*previousValue*<br/>
Der vorherige Wert.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="setanimationcontroller"></a>  CAnimationVariableChangeHandler::SetAnimationController

Speichert einen Zeiger auf den Animationscontroller zum Weiterleiten von Ereignissen.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parameter

*pAnimationController*<br/>
Ein Zeiger auf den Animationscontroller, der Ereignisse empfängt.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
