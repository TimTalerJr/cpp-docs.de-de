---
title: CD2DGradientBrush-Klasse
ms.date: 03/27/2019
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
ms.openlocfilehash: 2e04d714e3479224cfc4e207b70483786be33db8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173378"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush-Klasse

Die Basisklasse der CD2DLinearGradientBrush und die CD2DRadialGradientBrush-Klassen.

## <a name="syntax"></a>Syntax

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|Erstellt ein CD2DGradientBrush-Objekt.|
|[CD2DGradientBrush::~CD2DGradientBrush](#_dtorcd2dgradientbrush)|Der Destruktor. Wird aufgerufen, wenn ein Farbverlaufspinsel D2D-Objekt zerstört wird.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGradientBrush::Destroy](#destroy)|Zerstört ein CD2DGradientBrush-Objekt. (Überschreibt [CD2DBrush:: Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|Array von Strukturen D2D1_GRADIENT_STOP.|
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|Der Speicherplatz in der die, den Farbe der Interpolation zwischen dem Farbverlaufsstopp ausgeführt wird.|
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|Das Verhalten der Farbverlauf außerhalb der normalisierten Bereich [0,1].|
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|Ein Zeiger auf ein Array von D2D1_GRADIENT_STOP-Strukturen.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dgradientbrush"></a>  CD2DGradientBrush:: ~ CD2DGradientBrush

Der Destruktor. Wird aufgerufen, wenn ein Farbverlaufspinsel D2D-Objekt zerstört wird.

```
virtual ~CD2DGradientBrush();
```

##  <a name="cd2dgradientbrush"></a>  CD2DGradientBrush::CD2DGradientBrush

Erstellt ein CD2DGradientBrush-Objekt.

```
CD2DGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*gradientStops*<br/>
Ein Zeiger auf ein Array von D2D1_GRADIENT_STOP-Strukturen.

*gradientStopsCount*<br/>
Ein Wert größer als oder gleich 1, der die Anzahl der Farbverlaufsstopps in GradientStops-Array angibt.

*colorInterpolationGamma*<br/>
Der Speicherplatz in der die, den Farbe der Interpolation zwischen dem Farbverlaufsstopp ausgeführt wird.

*extendMode*<br/>
Das Verhalten der Farbverlauf außerhalb der normalisierten Bereich [0,1].

*pBrushProperties*<br/>
Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="destroy"></a>  CD2DGradientBrush:: Destroy

Zerstört ein CD2DGradientBrush-Objekt.

```
virtual void Destroy();
```

##  <a name="m_argradientstops"></a>  CD2DGradientBrush::m_arGradientStops

Array von Strukturen D2D1_GRADIENT_STOP.

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

##  <a name="m_colorinterpolationgamma"></a>  CD2DGradientBrush::m_colorInterpolationGamma

Der Speicherplatz in der die, den Farbe der Interpolation zwischen dem Farbverlaufsstopp ausgeführt wird.

```
D2D1_GAMMA m_colorInterpolationGamma;
```

##  <a name="m_extendmode"></a>  CD2DGradientBrush::m_extendMode

Das Verhalten der Farbverlauf außerhalb der normalisierten Bereich [0,1].

```
D2D1_EXTEND_MODE m_extendMode;
```

##  <a name="m_pgradientstops"></a>  CD2DGradientBrush::m_pGradientStops

Ein Zeiger auf ein Array von D2D1_GRADIENT_STOP-Strukturen.

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
