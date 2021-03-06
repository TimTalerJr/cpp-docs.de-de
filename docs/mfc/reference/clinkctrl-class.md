---
title: ClinkCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
ms.openlocfilehash: 37d9e624c40f0d6aa7f3d3fa1ed3d97ffa478ee7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505702"
---
# <a name="clinkctrl-class"></a>ClinkCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-SysLink-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|Erstellt ein `CLinkCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CLinkCtrl::Create](#create)|Erstellt ein Link Steuerelement und fügt es an `CLinkCtrl` ein-Objekt an.|
|[CLinkCtrl::CreateEx](#createex)|Erstellt ein Link Steuerelement mit erweiterten Stilen und fügt es an `CLinkCtrl` ein-Objekt an.|
|[CLinkCtrl::GetIdealHeight](#getidealheight)|Ruft die ideale Höhe des Link Steuer Elements ab.|
|[CLinkCtrl::GetIdealSize](#getidealsize)|Berechnet die bevorzugte Höhe des linktexts für das aktuelle Link Steuerelement, abhängig von der angegebenen Breite des Links.|
|[CLinkCtrl::GetItem](#getitem)|Ruft die Zustände und Attribute eines Link Steuerelement Elements ab.|
|[CLinkCtrl::GetItemID](#getitemid)|Ruft die ID eines Link Steuerelement Elements ab.|
|[CLinkCtrl::GetItemState](#getitemstate)|Ruft den Zustand des Link Steuer Elements ab.|
|[CLinkCtrl::GetItemUrl](#getitemurl)|Ruft die URL ab, die durch das Link-Steuerelement dargestellt wird.|
|[CLinkCtrl::HitTest](#hittest)|Bestimmt, ob der Benutzer auf den angegebenen Link geklickt hat.|
|[CLinkCtrl::SetItem](#setitem)|Legt die Zustände und Attribute eines Link Steuer Elements fest.|
|[CLinkCtrl::SetItemID](#setitemid)|Legt die ID eines Link Steuer Elements fest.|
|[CLinkCtrl::SetItemState](#setitemstate)|Legt den Zustand des Link Steuer Elements fest.|
|[CLinkCtrl::SetItemUrl](#setitemurl)|Legt die vom Link Steuerelement dargestellte URL fest.|

## <a name="remarks"></a>Hinweise

Ein "Link-Steuerelement" ist eine bequeme Möglichkeit zum Einbetten von Hypertext-Links in einem Fenster. Das tatsächliche Steuerelement ist ein Fenster, das markierten Text rendert und geeignete Anwendungen öffnet, wenn der Benutzer auf einen eingebetteten Link klickt. Mehrere Links werden innerhalb eines Steuer Elements unterstützt, und es kann auf einen NULL basierten Index zugegriffen werden.

Dieses Steuerelement (und damit `CLinkCtrl` auch die-Klasse) ist nur für Programme verfügbar, die unter Windows XP und höher ausgeführt werden.

Weitere Informationen finden Sie unter [Syslink-Steuer](/windows/win32/Controls/syslink-overview) Element im Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="clinkctrl"></a>ClinkCtrl:: ClinkCtrl

Erstellt ein `CLinkCtrl`-Objekt.

```
CLinkCtrl();
```

##  <a name="create"></a>ClinkCtrl:: Create

Erstellt ein Link Steuerelement und fügt es an `CLinkCtrl` ein-Objekt an.

```
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*lpszLinkMarkup*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den markierten Text enthält, der angezeigt werden soll. Weitere Informationen finden Sie im Abschnitt "Markup-und Link Zugriff" im Thema [Übersicht über Syslink](/windows/win32/Controls/syslink-overview)-Steuerelemente.

*dwStyle*<br/>
Gibt den Stil des Link Steuer Elements an. Wenden Sie eine beliebige Kombination von Steuerelement Stilen an. Weitere Informationen finden Sie unter [allgemeine Steuerelement Stile](/windows/win32/Controls/common-control-styles) in der `Windows SDK` .

*Rect*<br/>
Gibt die Größe und Position des Link Steuer Elements an. Dabei kann es sich entweder um ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder um eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur handeln.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster des Link Steuer Elements an. Er darf nicht NULL sein.

*nID*<br/>
Gibt die ID des Link Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Initialisierung erfolgreich war. andernfalls false.

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CLinkCtrl` -Objekt in zwei Schritten. Zuerst wird der-Konstruktor aufgerufen und dann `Create`aufgerufen, wodurch das Link Steuerelement erstellt und an das `CLinkCtrl` -Objekt angefügt wird. Wenn Sie erweiterte Windows-Stile mit dem Steuerelement verwenden möchten, können Sie " [ClinkCtrl::](#createex) up- `Create`Ex" anstelle von aufrufen.

Die zweite Form der `Create` Methode ist veraltet. Verwenden Sie das erste Formular, das den *lpszlinkmarkup* -Parameter angibt.

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden zwei Variablen mit dem `m_Link1` Namen `m_Link2`und definiert, die für den Zugriff auf zwei Link Steuerelemente verwendet werden.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird ein Link Steuerelement basierend auf der Position eines anderen Link Steuer Elements erstellt. Das Ressourcen Lade Modul erstellt das erste Link Steuerelement, wenn die Anwendung gestartet wird. Wenn Ihre Anwendung in die OnInitDialog-Methode eintritt, erstellen Sie das zweite Link Steuerelement relativ zur Position des ersten Link Steuer Elements. Anschließend ändern Sie die Größe des zweiten Link Steuer Elements, sodass es dem angezeigten Text entspricht.

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

##  <a name="createex"></a>ClinkCtrl:: kreateex

Erstellt ein Link Steuerelement mit erweiterten Stilen und fügt es an `CLinkCtrl` ein-Objekt an.

```
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```

### <a name="parameters"></a>Parameter

*lpszLinkMarkup*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den markierten Text enthält, der angezeigt werden soll. Weitere Informationen finden Sie im Abschnitt "Markup-und Link Zugriff" im Thema [Übersicht über Syslink](/windows/win32/Controls/syslink-overview)-Steuerelemente.

*dwExStyle*<br/>
Gibt den erweiterten Stil des Link Steuer Elements an. Eine Liste erweiterter Windows-Stile finden Sie unter dem *dwExStyle* -Parameter für " [kreatewindowex](/windows/win32/api/winuser/nf-winuser-createwindowexw) " in der Windows SDK.

*dwStyle*<br/>
Gibt den Stil des Link Steuer Elements an. Wenden Sie eine beliebige Kombination von Steuerelement Stilen an. Weitere Informationen finden Sie unter [allgemeine Steuerelement Stile](/windows/win32/Controls/common-control-styles) in der Windows SDK.

*Rect*<br/>
Gibt die Größe und Position des Link Steuer Elements an. Dabei kann es sich entweder um ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder um eine [Rect](/windows/win32/api/windef/ns-windef-rect) -Struktur handeln.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster des Link Steuer Elements an. Er darf nicht NULL sein.

*nID*<br/>
Gibt die ID des Link Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Initialisierung erfolgreich war. andernfalls false.

### <a name="remarks"></a>Hinweise

Verwenden `CreateEx` Sie anstelle von [Create](#create) , um erweiterte Windows-Stil Konstanten anzuwenden.

Die zweite Form der `CreateEx` Methode ist veraltet. Verwenden Sie das erste Formular, das den *lpszlinkmarkup* -Parameter angibt.

##  <a name="getidealheight"></a>ClinkCtrl:: getidealheight

Ruft die ideale Höhe des Link Steuer Elements ab.

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>Rückgabewert

Die ideale Höhe des Steuer Elements in Pixel.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [LM_GETIDEALHEIGHT](/windows/win32/Controls/lm-getidealheight), wie im Windows SDK beschrieben.

##  <a name="getidealsize"></a>ClinkCtrl:: getidealsize

Berechnet die bevorzugte Höhe des linktexts für das aktuelle Link Steuerelement, abhängig von der angegebenen Breite des Links.

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*cxMaxWidth*|in Die maximale Breite des Links in Pixel.|
|vorgenommen \* *Psize*|Ein Zeiger auf eine Windows- [Größen](/windows/win32/api/windef/ns-windef-size) Struktur. Wenn diese Methode zurückgegeben wird , enthält der CY `SIZE` -Member der-Struktur die ideale linktexthöhe für die von *cxmaxwidth*angegebene Link Text Breite. Der *CX* -Member der-Struktur enthält die Text Breite des Links, die tatsächlich benötigt wird.|

### <a name="return-value"></a>Rückgabewert

Die bevorzugte Höhe des linktexts in Pixel. Der Rückgabewert ist identisch mit dem Wert des *CY* -Members der `SIZE` -Struktur.

### <a name="remarks"></a>Hinweise

Ein Beispiel für die `GetIdealSize` -Methode finden Sie im Beispiel unter [ClinkCtrl:: Create](#create).

Diese Methode sendet die [LM_GETIDEALSIZE](/windows/win32/Controls/lm-getidealsize) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getitem"></a>ClinkCtrl:: GetItem

Ruft die Zustände und Attribute eines Link Steuerelement Elements ab.

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Ein Zeiger auf eine [LItem](/windows/win32/api/commctrl/ns-commctrl-litem) -Struktur, um Element Informationen zu empfangen.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [LM_GETITEM](/windows/win32/Controls/lm-getitem), wie im Windows SDK beschrieben.

##  <a name="getitemid"></a>ClinkCtrl:: getItemID

Ruft die ID eines Link Steuerelement Elements ab.

```
BOOL GetItemID(
    int iLink,
    CString& strID) const;

BOOL GetItemID(
    int iLink,
    LPWSTR szID,
    UINT cchID) const;
```

### <a name="parameters"></a>Parameter

*iLink*<br/>
Der Index eines Link Steuer Elements.

*strID*<br/>
Ein [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das die ID des angegebenen Elements enthält.

*szID*<br/>
Eine NULL-terminierte Zeichenfolge, die die ID des angegebenen Elements enthält.

*cchID*<br/>
Die Größe des *szid* -Puffers in Zeichen.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

> [!NOTE]
>  Diese Funktion gibt auch false zurück, wenn der Puffer von *szid oder Strid* kleiner als MAX_LINKID_TEXT ist.

### <a name="remarks"></a>Hinweise

Ruft die ID eines bestimmten Link Steuerelement Elements ab. Weitere Informationen finden Sie in der Win32-Nachricht [LM_GETITEM](/windows/win32/Controls/lm-getitem) im Windows SDK.

##  <a name="getitemstate"></a>ClinkCtrl:: GetItemState

Ruft den Zustand des Link Steuer Elements ab.

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>Parameter

*iLink*<br/>
Der Index eines Link Steuer Elements.

*pnState*<br/>
Der Wert des angegebenen Zustands Elements.

*stateMask*<br/>
Eine Kombination von Flags, die das zu entbende Zustands Element beschreiben. Eine Liste der Werte finden Sie in der Beschreibung des `state` Members in der [LItem](/windows/win32/api/commctrl/ns-commctrl-litem) -Struktur. Zulässige Elemente sind mit denen in `state`identisch.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Ruft den Wert des angegebenen Zustands Elements eines bestimmten Link Steuerelement Elements ab. Weitere Informationen finden Sie in der Win32-Nachricht [LM_GETITEM](/windows/win32/Controls/lm-getitem) im Windows SDK.

##  <a name="getitemurl"></a>ClinkCtrl:: getitemurl

Ruft die URL ab, die durch das Link-Steuerelement dargestellt wird.

```
BOOL GetItemUrl(
    int iLink,
    CString& strUrl) const;

BOOL GetItemUrl(
    int iLink,
    LPWSTR szUrl,
    UINT cchUrl) const;
```

### <a name="parameters"></a>Parameter

*iLink*<br/>
Der Index eines Link Steuer Elements.

*strUrl*<br/>
Ein [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das die durch das angegebene Element dargestellte URL enthält.

*szUrl*<br/>
Eine auf NULL endenden Zeichenfolge, die die durch das angegebene Element dargestellte URL enthält.

*cchUrl*<br/>
Die Größe des *szURL* -Puffers in Zeichen.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

> [!NOTE]
>  Diese Funktion gibt auch false zurück, wenn der Puffer von *szURL oder "strinurl* " kleiner als MAX_LINKID_TEXT ist.

### <a name="remarks"></a>Hinweise

Ruft die URL ab, die durch das angegebene Link Steuerelement dargestellt wird. Weitere Informationen finden Sie in der Win32-Nachricht [LM_GETITEM](/windows/win32/Controls/lm-getitem) im Windows SDK.

##  <a name="hittest"></a>ClinkCtrl:: HitTest

Bestimmt, ob der Benutzer auf den angegebenen Link geklickt hat.

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>Parameter

*phti*<br/>
Zeiger auf eine `LHITTESTINFO` -Struktur, die Informationen über den Link enthält, auf den der Benutzer geklickt hat.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [LM_HITTEST](/windows/win32/Controls/lm-hittest), wie im Windows SDK beschrieben.

##  <a name="setitem"></a>ClinkCtrl:: System Item

Legt die Zustände und Attribute eines Link Steuer Elements fest.

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>Parameter

*pItem*<br/>
Ein Zeiger auf eine [LItem](/windows/win32/api/commctrl/ns-commctrl-litem) -Struktur, die die festzulegenden Informationen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [LM_SETITEM](/windows/win32/Controls/lm-setitem), wie im Windows SDK beschrieben.

##  <a name="setitemid"></a>ClinkCtrl:: s-temid

Ruft die ID eines Link Steuerelement Elements ab.

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>Parameter

*iLink*<br/>
Der Index eines Link Steuer Elements.

*szID*<br/>
Eine NULL-terminierte Zeichenfolge, die die ID des angegebenen Elements enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Legt die ID eines bestimmten Link Steuerelement Elements fest. Weitere Informationen finden Sie in der Win32-Nachricht [LM_SETITEM](/windows/win32/Controls/lm-setitem) im Windows SDK.

##  <a name="setitemstate"></a>ClinkCtrl:: abtitemstate

Ruft den Zustand des Link Steuer Elements ab.

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>Parameter

*iLink*<br/>
Der Index eines Link Steuer Elements.

*pnState*<br/>
Der Wert des angegebenen Zustands Elements, das festgelegt wird.

*stateMask*<br/>
Eine Kombination von Flags, die das festgelegte Zustands Element beschreiben. Eine Liste der Werte finden Sie in der Beschreibung des `state` Members in der [LItem](/windows/win32/api/commctrl/ns-commctrl-litem) -Struktur. Zulässige Elemente sind mit denen in `state`identisch.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Legt den Wert des angegebenen Zustands Elements eines bestimmten Link Steuerelement-Elements fest. Weitere Informationen finden Sie in der Win32-Nachricht [LM_SETITEM](/windows/win32/Controls/lm-setitem) im Windows SDK.

##  <a name="setitemurl"></a>ClinkCtrl:: abtitemurl

Legt die vom Link Steuerelement dargestellte URL fest.

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>Parameter

*iLink*<br/>
Der Index eines Link Steuer Elements.

*szUrl*<br/>
Eine auf NULL endenden Zeichenfolge, die die durch das angegebene Element dargestellte URL enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Legt die URL fest, die durch das angegebene Link Steuerelement dargestellt wird. Weitere Informationen finden Sie in der Win32-Nachricht [LM_SETITEM](/windows/win32/Controls/lm-setitem) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)
