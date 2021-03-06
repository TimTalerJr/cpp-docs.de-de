---
title: Cmfcdropdownframe-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
ms.openlocfilehash: 534dc90443371c8440e0cb317540f2cf80f6eacc
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425832"
---
# <a name="cmfcdropdownframe-class"></a>Cmfcdropdownframe-Klasse

Stellt Funktionen für das Dropdown-Rahmen Fenster für Dropdown-Symbolleisten und Dropdown-Symbolleisten-Schaltflächen bereit.

## <a name="syntax"></a>Syntax

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|`CMFCDropDownFrame::CMFCDropDownFrame`|Standardkonstruktor|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|[Cmfcdropdownframe:: Create](#create)|Erstellt ein `CMFCDropDownFrame`-Objekt.|
|`CMFCDropDownFrame::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[Cmfcdropdownframe:: getparametermenubar](#getparentmenubar)|Ruft die übergeordnete Menüleiste des Dropdown Rahmens ab.|
|[Cmfcdropdownframe:: getparameterpopupmenu](#getparentpopupmenu)|Ruft das übergeordnete Popup Menü des Dropdown Rahmens ab.|
|`CMFCDropDownFrame::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[Cmfcdropdownframe:: Neuberechnung](#recalclayout)|Positioniert den Dropdown Rahmen neu.|
|[Cmfcdropdownframe:: "Dropdown"](#setautodestroy)|Legt fest, ob das untergeordnete Dropdown-Symbolleisten Fenster automatisch zerstört wird.|

### <a name="remarks"></a>Hinweise

Diese Klasse ist nicht für die direkte Verwendung im Code vorgesehen.

Das Framework verwendet diese Klasse, um das Frame Verhalten für die Klassen `CMFCDropDownToolbar` und `CMFCDropDownToolbarButton` bereitzustellen. Weitere Informationen zu diesen Klassen finden Sie unter [cmfcdropdowntoolbar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md) und [cmfcdropdowntoolbarbutton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Zeiger auf ein `CMFCDropDownFrame` Objekt aus einer `CFrameWnd` Klasse abgerufen wird und wie das untergeordnete Dropdown-Symbolleisten Fenster automatisch zerstört wird.

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[Cmfcdropdownframe](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>Voraussetzungen

**Header:** afxdropdowntoolbar.h

##  <a name="create"></a>Cmfcdropdownframe:: Create

Erstellt ein `CMFCDropDownFrame`-Objekt.

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pwndparent*|in Das übergeordnete Fenster des Dropdown Rahmens.|
|*x*|in Die horizontale Bildschirm Koordinate für die Position des nach-unten-Rahmens.|
|*y*|in Die vertikale Bildschirm Koordinate für die Position des nach-unten-Rahmens.|
|*pwndorigintoolbar*|in Die Symbolleiste mit den Dropdown-Schaltflächen, die von dieser Methode zum Auffüllen des neuen Dropdown Frame-Objekts verwendet werden.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Dropdown Rahmen erfolgreich erstellt wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die Base [CMiniFrameWnd:: foateex](../../mfc/reference/cminiframewnd-class.md#createex) -Methode auf, um das Dropdown-Rahmen Fenster mit dem WS_POPUP-Stil zu erstellen. Das Dropdown-Rahmen Fenster wird an den angegebenen Bildschirm Koordinaten angezeigt. Bei dieser Methode tritt ein Fehler auf, wenn die [CMiniFrameWnd::](../../mfc/reference/cminiframewnd-class.md#createex) up-Methode false zurückgibt.

Die `CMFCDropDownFrame`-Klasse erstellt eine Kopie des angegebenen `CMFCDropDownToolBar`-Parameters. Diese Methode kopiert die Schaltflächen Bilder und Schaltflächen Zustände aus dem `pWndOriginToolbar`-Parameter in das `m_pWndOriginToolbar` Datenmember.

##  <a name="getparentmenubar"></a>Cmfcdropdownframe:: getparametermenubar

Ruft die übergeordnete Menüleiste des Dropdown Rahmens ab.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die übergeordnete Menüleiste des Dropdown Rahmens oder NULL, wenn der Frame kein übergeordnetes Element aufweist.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die übergeordnete Menüleiste von der übergeordneten Schaltfläche ab. Diese Methode gibt NULL zurück, wenn der Dropdown-Frame keine übergeordnete Schaltfläche aufweist oder die übergeordnete Schaltfläche keine übergeordnete Menüleiste hat.

##  <a name="getparentpopupmenu"></a>Cmfcdropdownframe:: getparameterpopupmenu

Ruft das übergeordnete Popup Menü des Dropdown Rahmens ab.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das übergeordnete Dropdown Menü des Dropdown Rahmens oder NULL, wenn der Frame kein übergeordnetes Element aufweist.

### <a name="remarks"></a>Hinweise

Diese Methode ruft das übergeordnete Menü von der übergeordneten Schaltfläche ab. Diese Methode gibt NULL zurück, wenn der Dropdown-Frame keine übergeordnete Schaltfläche aufweist oder die übergeordnete Schaltfläche kein übergeordnetes Menü hat.

##  <a name="recalclayout"></a>Cmfcdropdownframe:: Neuberechnung

Positioniert den Dropdown Rahmen neu.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*bbenachrichtigen*|[in] Nicht verwendet.|

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn der Dropdown Rahmen erstellt wird oder die Größe des übergeordneten Fensters geändert wird. Diese Methode berechnet die Position und die Größe des Dropdown Rahmens, indem die Position und Größe des übergeordneten Fensters verwendet wird.

##  <a name="setautodestroy"></a>Cmfcdropdownframe:: "Dropdown"

Legt fest, ob das untergeordnete Dropdown-Symbolleisten Fenster automatisch zerstört wird.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*Bauto zerstören*<br/>
in TRUE, wenn das zugehörige Dropdown-Symbolleisten Fenster automatisch zerstört werden soll. andernfalls false.

### <a name="remarks"></a>Hinweise

Wenn *baudedestroy* auf true festgelegt ist, zerstört der `CMFCDropDownFrame` debugtor das zugehörige Dropdown-Symbolleisten Fenster. Der Standardwert lautet TRUE.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCDropDownToolbarButton-Klasse](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
