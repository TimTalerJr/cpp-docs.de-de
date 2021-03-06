---
title: Cstockpropimpl-Klasse
ms.date: 05/06/2019
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
ms.openlocfilehash: 29b4337679f05d780d3d6cd5de6bf6f889a6ea30
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496327"
---
# <a name="cstockpropimpl-class"></a>Cstockpropimpl-Klasse

Diese Klasse stellt Methoden zum unterstützen von Aktien Eigenschafts Werten bereit.

> [!IMPORTANT]
> Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
template <
    class T, 
    class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE CStockPropImpl :
    public IDispatchImpl<InterfaceName, piid, plibid, wMajor, wMinor, tihclass>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse, die das Steuerelement implementiert `CStockPropImpl`und von abgeleitet wird.

*Schnittstellenname*<br/>
Eine duale Schnittstelle, die die Lagereigenschaften verfügbar macht.

*piid*<br/>
Ein Zeiger auf die IID von `InterfaceName`.

*plibid*<br/>
Ein Zeiger auf die LIBID der Typbibliothek, die die Definition von `InterfaceName`enthält.

*wMajor*<br/>
Die Hauptversion der Typbibliothek Der Standardwert ist 1.

*wMinor*<br/>
Die Nebenversion der Typbibliothek Der Standardwert ist 0.

*tihclass*<br/>
Die Klasse, mit der die Typinformationen für *T*verwaltet werden. Der Standardwert ist `CComTypeInfoHolder`sein.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|[get_Appearance](#get_appearance)|Mit dieser Methode können Sie den vom Steuerelement verwendeten Zeichenstil abrufen, z. b. Flat oder 3D.|
|[get_AutoSize](#get_autosize)|Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob das Steuerelement keine andere Größe aufweisen kann.|
|[get_BackColor](#get_backcolor)|Mit dieser Methode können Sie die Hintergrundfarbe des Steuer Elements abrufen.|
|[get_BackStyle](#get_backstyle)|Mit dieser Methode können Sie den Hintergrund Stil des Steuer Elements abrufen, entweder transparent oder nicht transparent.|
|[get_BorderColor](#get_bordercolor)|Mit dieser Methode können Sie die Rahmenfarbe des Steuer Elements abrufen.|
|[get_BorderStyle](#get_borderstyle)|Ruft diese Methode auf, um die Rahmenart des Steuer Elements abzurufen.|
|[get_BorderVisible](#get_bordervisible)|Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob der Rahmen des Steuer Elements sichtbar ist.|
|[get_BorderWidth](#get_borderwidth)|Mit dieser Methode können Sie die Breite (in Pixel) des Rahmens des Steuer Elements abrufen.|
|[get_Caption](#get_caption)|Mit dieser Methode wird der in der Beschriftung eines Objekts angegebene Text abzurufen.|
|[get_DrawMode](#get_drawmode)|Mit dieser Methode können Sie den Zeichnungsmodus des Steuer Elements abrufen, z. b. Xor Pen oder Invert Farben.|
|[get_DrawStyle](#get_drawstyle)|Mit dieser Methode können Sie die Zeichnungs Art des Steuer Elements abrufen, z. b. mit Solid, gestrichelt oder gepunkteten.|
|[get_DrawWidth](#get_drawwidth)|Mit dieser Methode können Sie die Zeichnungs Breite (in Pixel) abrufen, die von den Zeichnungs Methoden des Steuer Elements verwendet wird.|
|[get_Enabled](#get_enabled)|Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob das Steuerelement aktiviert ist.|
|[get_FillColor](#get_fillcolor)|Ruft diese Methode auf, um die Füllfarbe des Steuer Elements abzurufen.|
|[get_FillStyle](#get_fillstyle)|Mit dieser Methode können Sie den Füllstil des Steuer Elements abrufen, z. b. durchgezogen, transparent oder Kreuz.|
|[get_Font](#get_font)|Mit dieser Methode können Sie einen Zeiger auf die Schriftart Eigenschaften des Steuer Elements abrufen.|
|[get_ForeColor](#get_forecolor)|Mit dieser Methode können Sie die Vordergrundfarbe des Steuer Elements abrufen.|
|[get_HWND](#get_hwnd)|Mit dieser Methode wird das Fenster Handle aufgerufen, das dem Steuerelement zugeordnet ist.|
|[get_MouseIcon](#get_mouseicon)|Mit dieser Methode können Sie die Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatei) abrufen, die angezeigt werden soll, wenn sich der Mauszeiger über dem Steuerelement befindet.|
|[get_MousePointer](#get_mousepointer)|Mit dieser Methode können Sie den Typ des Mauszeigers abrufen, der angezeigt wird, wenn sich der Mauszeiger über dem Steuerelement befindet, z. b. Pfeil, Kreuz oder Sanduhr.|
|[get_Picture](#get_picture)|Mit dieser Methode können Sie einen Zeiger auf die Bildeigenschaften einer Grafik (Symbol, Bitmap oder Metadatei) abrufen, die angezeigt werden soll.|
|[get_ReadyState](#get_readystate)|Mit dieser Methode können Sie den Zustand des Steuer Elements abrufen, z. b. Laden oder laden.|
|[get_TabStop](#get_tabstop)|Mit dieser Methode wird das Flag aufgerufen, das angibt, ob es sich bei dem Steuerelement um einen Tabstopp handelt.|
|[get_Text](#get_text)|Mit dieser Methode können Sie den Text abrufen, der mit dem-Steuerelement angezeigt wird.|
|[getvalid](#get_valid)|Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob das Steuerelement gültig ist.|
|[get_Window](#get_window)|Mit dieser Methode wird das Fenster Handle aufgerufen, das dem Steuerelement zugeordnet ist. Identisch mit [cstockpropimpl:: get_HWND](#get_hwnd).|
|[put_Appearance](#put_appearance)|Mit dieser Methode können Sie die vom Steuerelement verwendete Zeichnungs Art festlegen, z. b. Flat oder 3D.|
|[put_AutoSize](#put_autosize)|Mit dieser Methode wird der Wert des Flags festgelegt, das angibt, ob das Steuerelement keine andere Größe aufweisen kann.|
|[put_BackColor](#put_backcolor)|Mit dieser Methode wird die Hintergrundfarbe des Steuer Elements festgelegt.|
|[put_BackStyle](#put_backstyle)|Ruft diese Methode auf, um den Hintergrund Stil des Steuer Elements festzulegen.|
|[put_BorderColor](#put_bordercolor)|Mit dieser Methode wird die Rahmenfarbe des Steuer Elements festgelegt.|
|[put_BorderStyle](#put_borderstyle)|Ruft diese Methode auf, um die Rahmenart des Steuer Elements festzulegen.|
|[put_BorderVisible](#put_bordervisible)|Ruft diese Methode auf, um den Wert des Flags festzulegen, das angibt, ob der Rahmen des Steuer Elements sichtbar ist.|
|[put_BorderWidth](#put_borderwidth)|Ruft diese Methode auf, um die Breite des Rahmens des Steuer Elements festzulegen.|
|[put_Caption](#put_caption)|Mit dieser Methode können Sie den Text festlegen, der mit dem Steuerelement angezeigt werden soll.|
|[put_DrawMode](#put_drawmode)|Mit dieser Methode können Sie den Zeichnungsmodus des Steuer Elements festlegen, z. b. Xor Pen oder Invert Farben.|
|[put_DrawStyle](#put_drawstyle)|Mit dieser Methode können Sie die Zeichnungsart des Steuer Elements festlegen, z. b. mit Solid, gestrichelt oder gepunkteten.|
|[put_DrawWidth](#put_drawwidth)|Ruft diese Methode auf, um die Breite (in Pixel) festzulegen, die von den Zeichnungs Methoden des Steuer Elements verwendet wird.|
|[put_Enabled](#put_enabled)|Mit dieser Methode können Sie das Flag festlegen, das angibt, ob das Steuerelement aktiviert ist.|
|[put_FillColor](#put_fillcolor)|Mit dieser Methode wird die Füllfarbe des Steuer Elements festgelegt.|
|[put_FillStyle](#put_fillstyle)|Mit dieser Methode können Sie den Füllstil des Steuer Elements festlegen, z. b. Solid, transparent oder Cross-.|
|[put_Font](#put_font)|Ruft diese Methode auf, um die Schriftart Eigenschaften des Steuer Elements festzulegen.|
|[put_ForeColor](#put_forecolor)|Ruft diese Methode auf, um die Vordergrundfarbe des Steuer Elements festzulegen.|
|[put_HWND](#put_hwnd)|Diese Methode gibt E_FAIL zurück.|
|[put_MouseIcon](#put_mouseicon)|Mit dieser Methode können Sie die Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatendatei) festlegen, die angezeigt werden soll, wenn sich der Mauszeiger über dem Steuerelement befindet.|
|[put_MousePointer](#put_mousepointer)|Mit dieser Methode können Sie den Typ des Mauszeigers festlegen, der angezeigt wird, wenn sich der Mauszeiger über dem Steuerelement befindet, z. b. Pfeil, Kreuz oder Sanduhr.|
|[put_Picture](#put_picture)|Mit dieser Methode können Sie die Bildeigenschaften einer Grafik (Symbol, Bitmap oder Metadatei) festlegen, die angezeigt werden soll.|
|[put_ReadyState](#put_readystate)|Mit dieser Methode können Sie den Zustand des Steuer Elements festlegen, z. b. Laden oder laden.|
|[put_TabStop](#put_tabstop)|Mit dieser Methode können Sie den Wert des Flags festlegen, das angibt, ob es sich bei dem Steuerelement um einen Tabstopp handelt.|
|[put_Text](#put_text)|Mit dieser Methode können Sie den Text festlegen, der mit dem-Steuerelement angezeigt wird.|
|[putvalid](#put_valid)|Ruft diese Methode auf, um das Flag festzulegen, das angibt, ob das Steuerelement gültig ist.|
|[put_Window](#put_window)|Diese Methode ruft [cstockpropimpl::p ut_hwnd](#put_hwnd)auf, wodurch E_FAIL zurückgegeben wird.|
|[putref_Font](#putref_font)|Mit dieser Methode können Sie die Schriftart Eigenschaften des Steuer Elements mit einem Verweis Zähler festlegen.|
|[putref_MouseIcon](#putref_mouseicon)|Mit dieser Methode können Sie die Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatendatei) festlegen, die angezeigt werden soll, wenn sich der Mauszeiger über dem Steuerelement befindet, mit einem Verweis Zähler.|
|[putref_Picture](#putref_picture)|Mit dieser Methode können Sie die Bildeigenschaften einer Grafik (Symbol, Bitmap oder Metadatei), die angezeigt werden soll, mit einem Verweis Zähler festlegen.|

## <a name="remarks"></a>Hinweise

`CStockPropImpl`stellt **Put** -und **Get** -Methoden für jede Aktien Eigenschaft bereit. Diese Methoden stellen den Code bereit, der erforderlich ist, um das Datenelement, das den einzelnen Eigenschaften zugeordnet ist, festzulegen oder zu erhalten und mit dem Container zu benachrichtigen, wenn sich eine Eigenschaft ändert

Visual Studio bietet Unterstützung für Bestands Eigenschaften durch die Assistenten. Weitere Informationen zum Hinzufügen von Aktien Eigenschaften zu einem Steuerelement finden Sie im [ATL-Tutorial](../../atl/active-template-library-atl-tutorial.md).

Aus Gründen der abwärts `CStockPropImpl` Kompatibilität macht `get_Window` auch `put_Window` die `get_HWND` -Methode und die `put_HWND`-Methode verfügbar, die einfach und bzw. Die Standard Implementierung von `put_HWND` gibt E_FAIL zurück, da HWND eine schreibgeschützte Eigenschaft sein sollte.

Die folgenden Eigenschaften verfügen auch über eine **PutRef** -Implementierung:

- Schriftart

- MouseIcon

- Picture

Die gleichen drei vordefinierten Eigenschaften erfordern, dass Ihr zugehöriger Datenmember vom `CComPtr` Typ oder einer anderen Klasse ist, die mithilfe des Zuweisungs Operators die korrekte Zählung der Schnittstellen Verweise bereitstellt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`T`

[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="get_appearance"></a>Cstockpropimpl:: get_Appearance

Mit dieser Methode können Sie den vom Steuerelement verwendeten Zeichenstil abrufen, z. b. Flat oder 3D.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>Parameter

*pnAppearance*<br/>
Eine Variable, die die Zeichnungs Art des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_autosize"></a>Cstockpropimpl:: get_AutoSize

Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob das Steuerelement keine andere Größe aufweisen kann.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>Parameter

*pbAutoSize*<br/>
Variable, die den FlagStatus empfängt. TRUE gibt an, dass das Steuerelement keine andere Größe aufweisen kann.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_backcolor"></a>Cstockpropimpl:: get_BackColor

Mit dieser Methode können Sie die Hintergrundfarbe des Steuer Elements abrufen.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>Parameter

*pclrBackColor*<br/>
Eine Variable, die die Hintergrundfarbe des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_backstyle"></a>Cstockpropimpl:: get_BackStyle

Mit dieser Methode können Sie den Hintergrund Stil des Steuer Elements abrufen, entweder transparent oder nicht transparent.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>Parameter

*pnBackStyle*<br/>
Eine Variable, die den Hintergrund Stil des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_bordercolor"></a>Cstockpropimpl:: get_BorderColor

Mit dieser Methode können Sie die Rahmenfarbe des Steuer Elements abrufen.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>Parameter

*pclrBorderColor*<br/>
Eine Variable, die die Rahmenfarbe des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_borderstyle"></a>Cstockpropimpl:: get_BorderStyle

Ruft diese Methode auf, um die Rahmenart des Steuer Elements abzurufen.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>Parameter

*pnBorderStyle*<br/>
Eine Variable, die die Rahmenart des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_bordervisible"></a>Cstockpropimpl:: get_BorderVisible

Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob der Rahmen des Steuer Elements sichtbar ist.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>Parameter

*pbBorderVisible*<br/>
Variable, die den FlagStatus empfängt. TRUE gibt an, dass der Rahmen des Steuer Elements sichtbar ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_borderwidth"></a>Cstockpropimpl:: get_BorderWidth

Mit dieser Methode können Sie die Breite des Rahmens des Steuer Elements abrufen.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>Parameter

*pnBorderWidth*<br/>
Eine Variable, die die Rahmenbreite des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_caption"></a>Cstockpropimpl:: get_Caption

Mit dieser Methode wird der in der Beschriftung eines Objekts angegebene Text abzurufen.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>Parameter

*pbstrCaption*<br/>
Der Text, der mit dem Steuerelement angezeigt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_drawmode"></a>Cstockpropimpl:: get_DrawMode

Mit dieser Methode können Sie den Zeichnungsmodus des Steuer Elements abrufen, z. b. Xor Pen oder Invert Farben.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>Parameter

*pnDrawMode*<br/>
Eine Variable, die den Zeichnungsmodus des-Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_drawstyle"></a>Cstockpropimpl:: get_DrawStyle

Mit dieser Methode können Sie die Zeichnungs Art des Steuer Elements abrufen, z. b. mit Solid, gestrichelt oder gepunkteten.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>Parameter

*pnDrawStyle*<br/>
Eine Variable, die die Zeichnungsart des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_drawwidth"></a>Cstockpropimpl:: get_DrawWidth

Mit dieser Methode können Sie die Zeichnungs Breite (in Pixel) abrufen, die von den Zeichnungs Methoden des Steuer Elements verwendet wird.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>Parameter

*pnDrawWidth*<br/>
Eine Variable, die den Breitenwert des Steuer Elements in Pixel empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_enabled"></a>Cstockpropimpl:: get_Enabled

Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob das Steuerelement aktiviert ist.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>Parameter

*pbenabled*<br/>
Variable, die den FlagStatus empfängt. TRUE gibt an, dass das Steuerelement aktiviert ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_fillcolor"></a>Cstockpropimpl:: get_FillColor

Ruft diese Methode auf, um die Füllfarbe des Steuer Elements abzurufen.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>Parameter

*pclrFillColor*<br/>
Eine Variable, die die Füllfarbe des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_fillstyle"></a>Cstockpropimpl:: get_FillStyle

Mit dieser Methode können Sie den Füllstil des Steuer Elements abrufen, z. b. Solid, transparent oder crosshatched.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>Parameter

*pnFillStyle*<br/>
Eine Variable, die den Füllstil des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_font"></a>Cstockpropimpl:: get_Font

Mit dieser Methode können Sie einen Zeiger auf die Schriftart Eigenschaften des Steuer Elements abrufen.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parameter

*ppFont*<br/>
Eine Variable, die einen Zeiger auf die Schriftart Eigenschaften des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_forecolor"></a>Cstockpropimpl:: get_ForeColor

Mit dieser Methode können Sie die Vordergrundfarbe des Steuer Elements abrufen.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>Parameter

*pclrForeColor*<br/>
Variable, die die Vordergrundfarbe der Steuerelemente empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_hwnd"></a>Cstockpropimpl:: get_HWND

Mit dieser Methode wird das Fenster Handle aufgerufen, das dem Steuerelement zugeordnet ist.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parameter

*phWnd*<br/>
Das Fenster Handle, das dem Steuerelement zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_mouseicon"></a>Cstockpropimpl:: get_MouseIcon

Mit dieser Methode können Sie die Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatei) abrufen, die angezeigt werden soll, wenn sich der Mauszeiger über dem Steuerelement befindet.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parameter

*pppicture*<br/>
Eine Variable, die einen Zeiger auf die Bildeigenschaften der Grafik empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_mousepointer"></a>Cstockpropimpl:: get_MousePointer

Mit dieser Methode können Sie den Typ des Mauszeigers abrufen, der angezeigt wird, wenn sich der Mauszeiger über dem Steuerelement befindet, z. b. Pfeil, Kreuz oder Sanduhr.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>Parameter

*pnMousePointer*<br/>
Variable, die den Typ des Mauszeigers empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_picture"></a>Cstockpropimpl:: get_Picture

Mit dieser Methode können Sie einen Zeiger auf die Bildeigenschaften einer Grafik (Symbol, Bitmap oder Metadatei) abrufen, die angezeigt werden soll.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parameter

*pppicture*<br/>
Eine Variable, die einen Zeiger auf die Eigenschaften des Bilds empfängt. Weitere Informationen finden Sie unter [IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_readystate"></a>Cstockpropimpl:: get_ReadyState

Mit dieser Methode können Sie den Zustand des Steuer Elements abrufen, z. b. Laden oder laden.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>Parameter

*pnReadyState*<br/>
Eine Variable, die den Zustand "bereit" des Steuer Elements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_tabstop"></a>Cstockpropimpl:: get_TabStop

Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob es sich bei dem Steuerelement um einen Tabstopp handelt.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>Parameter

*pbTabStop*<br/>
Variable, die den FlagStatus empfängt. TRUE gibt an, dass das Steuerelement ein Tabstopp ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_text"></a>Cstockpropimpl:: get_Text

Mit dieser Methode können Sie den Text abrufen, der mit dem-Steuerelement angezeigt wird.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>Parameter

*pbstrText*<br/>
Der Text, der mit dem-Steuerelement angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_valid"></a>Cstockpropimpl:: GetValID

Mit dieser Methode können Sie den Status des Flags abrufen, das angibt, ob das Steuerelement gültig ist.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>Parameter

*pbValid*<br/>
Variable, die den FlagStatus empfängt. TRUE gibt an, dass das Steuerelement gültig ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="get_window"></a>Cstockpropimpl:: get_Window

Mit dieser Methode wird das Fenster Handle aufgerufen, das dem Steuerelement zugeordnet ist. Identisch mit [cstockpropimpl:: get_HWND](#get_hwnd).

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parameter

*phWnd*<br/>
Das Fenster Handle, das dem Steuerelement zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_appearance"></a>Cstockpropimpl::p ut_appearance

Mit dieser Methode können Sie die vom Steuerelement verwendete Zeichnungs Art festlegen, z. b. Flat oder 3D.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>Parameter

*nappearance*<br/>
Der neue Zeichnungs Stil, der vom-Steuerelement verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_autosize"></a>Cstockpropimpl::p ut_autosize

Mit dieser Methode wird der Wert des Flags festgelegt, das angibt, ob das Steuerelement keine andere Größe aufweisen kann.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>Parameter

*bAutoSize*<br/>
TRUE, wenn das Steuerelement keine andere Größe aufweisen kann.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_backcolor"></a>Cstockpropimpl::p ut_backcolor

Mit dieser Methode wird die Hintergrundfarbe des Steuer Elements festgelegt.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>Parameter

*clrBackColor*<br/>
Die neue Hintergrundfarbe des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_backstyle"></a>Cstockpropimpl::p ut_backstyle

Ruft diese Methode auf, um den Hintergrund Stil des Steuer Elements festzulegen.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>Parameter

*nBackStyle*<br/>
Der neue Steuerelement Hintergrund Stil.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_bordercolor"></a>Cstockpropimpl::p ut_bordercolor

Mit dieser Methode wird die Rahmenfarbe des Steuer Elements festgelegt.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>Parameter

*clrBorderColor*<br/>
Die neue Rahmenfarbe. Der OLE_COLOR-Datentyp wird intern als 32-Bit-Ganzzahl (Long) dargestellt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_borderstyle"></a>Cstockpropimpl::p ut_borderstyle

Ruft diese Methode auf, um die Rahmenart des Steuer Elements festzulegen.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>Parameter

*nBorderStyle*<br/>
Die neue Rahmenart.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_bordervisible"></a>Cstockpropimpl::p ut_bordervisible

Ruft diese Methode auf, um den Wert des Flags festzulegen, das angibt, ob der Rahmen des Steuer Elements sichtbar ist.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>Parameter

*bBorderVisible*<br/>
TRUE, wenn der Rahmen sichtbar sein soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_borderwidth"></a>Cstockpropimpl::p ut_borderwidth

Ruft diese Methode auf, um die Breite des Rahmens des Steuer Elements festzulegen.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>Parameter

*nBorderWidth*<br/>
Die neue Breite des Rahmens des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_caption"></a>Cstockpropimpl::p ut_caption

Mit dieser Methode können Sie den Text festlegen, der mit dem Steuerelement angezeigt werden soll.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>Parameter

*bstrCaption*<br/>
Der Text, der mit dem Steuerelement angezeigt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_drawmode"></a>Cstockpropimpl::p ut_drawmode

Mit dieser Methode können Sie den Zeichnungsmodus des Steuer Elements festlegen, z. b. Xor Pen oder Invert Farben.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>Parameter

*nDrawMode*<br/>
Der neue Zeichnungsmodus für das Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_drawstyle"></a>Cstockpropimpl::p ut_drawstyle

Mit dieser Methode können Sie die Zeichnungsart des Steuer Elements festlegen, z. b. mit Solid, gestrichelt oder gepunkteten.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>Parameter

*nDrawStyle*<br/>
Die neue Zeichnungsart für das Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_drawwidth"></a>Cstockpropimpl::p ut_drawwidth

Ruft diese Methode auf, um die Breite (in Pixel) festzulegen, die von den Zeichnungs Methoden des Steuer Elements verwendet wird.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>Parameter

*nDrawWidth*<br/>
Die neue Breite, die von den Zeichnungs Methoden des Steuer Elements verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_enabled"></a>Cstockpropimpl::p ut_enabled

Mit dieser Methode können Sie den Wert des Flags festlegen, das angibt, ob das Steuerelement aktiviert ist.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>Parameter

*benabled*<br/>
TRUE, wenn das Steuerelement aktiviert ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_fillcolor"></a>Cstockpropimpl::p ut_fillcolor

Mit dieser Methode wird die Füllfarbe des Steuer Elements festgelegt.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>Parameter

*clrFillColor*<br/>
Die neue Füllfarbe für das-Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_fillstyle"></a>Cstockpropimpl::p ut_fillstyle

Mit dieser Methode können Sie den Füllstil des Steuer Elements festlegen, z. b. Solid, transparent oder Cross-.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>Parameter

*nFillStyle*<br/>
Der neue Füllstil für das Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_font"></a>Cstockpropimpl::p ut_font

Ruft diese Methode auf, um die Schriftart Eigenschaften des Steuer Elements festzulegen.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parameter

*pFont*<br/>
Ein Zeiger auf die Schriftart Eigenschaften des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_forecolor"></a>Cstockpropimpl::p ut_forecolor

Ruft diese Methode auf, um die Vordergrundfarbe des Steuer Elements festzulegen.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>Parameter

*clrForeColor*<br/>
Die neue Vordergrundfarbe des-Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_hwnd"></a>Cstockpropimpl::p ut_hwnd

Diese Methode gibt E_FAIL zurück.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt E_FAIL zurück.

### <a name="remarks"></a>Hinweise

Das Fenster Handle ist ein Schreib geschützter-Wert.

##  <a name="put_mouseicon"></a>Cstockpropimpl::p ut_mouseicon

Mit dieser Methode können Sie die Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatendatei) festlegen, die angezeigt werden soll, wenn sich der Mauszeiger über dem Steuerelement befindet.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parameter

*ppicture*<br/>
Ein Zeiger auf die Bildeigenschaften der Grafik.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_mousepointer"></a>Cstockpropimpl::p ut_mousepointer

Mit dieser Methode können Sie den Typ des Mauszeigers festlegen, der angezeigt wird, wenn sich der Mauszeiger über dem Steuerelement befindet, z. b. Pfeil, Kreuz oder Sanduhr.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>Parameter

*nMousePointer*<br/>
Der Typ des Mauszeigers.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_picture"></a>Cstockpropimpl::p ut_picture

Mit dieser Methode können Sie die Bildeigenschaften einer Grafik (Symbol, Bitmap oder Metadatei) festlegen, die angezeigt werden soll.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parameter

*ppicture*<br/>
Ein Zeiger auf die Eigenschaften des Bilds. Weitere Informationen finden Sie unter [IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_readystate"></a>Cstockpropimpl::p ut_readystate

Mit dieser Methode können Sie den Zustand des Steuer Elements festlegen, z. b. Laden oder laden.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>Parameter

*nReadyState*<br/>
Der bereite Zustand des-Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_tabstop"></a>Cstockpropimpl::p ut_tabstop

Mit dieser Methode können Sie das Flag festlegen, das angibt, ob es sich bei dem Steuerelement um einen Tabstopp handelt.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>Parameter

*bTabStop*<br/>
TRUE, wenn das Steuerelement ein Tabstopp ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_text"></a>Cstockpropimpl::p ut_text

Mit dieser Methode können Sie den Text festlegen, der mit dem-Steuerelement angezeigt wird.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>Parameter

*bstrText*<br/>
Der Text, der mit dem-Steuerelement angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_valid"></a>Cstockpropimpl::p utvalid

Ruft diese Methode auf, um das Flag festzulegen, das angibt, ob das Steuerelement gültig ist.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>Parameter

*bValid*<br/>
TRUE, wenn das Steuerelement gültig ist.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="put_window"></a>Cstockpropimpl::p ut_window

Diese Methode ruft [cstockpropimpl::p ut_hwnd](#put_hwnd)auf, wodurch E_FAIL zurückgegeben wird.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
Das Fensterhandle.

### <a name="return-value"></a>Rückgabewert

Gibt E_FAIL zurück.

### <a name="remarks"></a>Hinweise

Das Fenster Handle ist ein Schreib geschützter-Wert.

##  <a name="putref_font"></a>Cstockpropimpl::p utref_font

Mit dieser Methode können Sie die Schriftart Eigenschaften des Steuer Elements mit einem Verweis Zähler festlegen.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parameter

*pFont*<br/>
Ein Zeiger auf die Schriftart Eigenschaften des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Identisch mit [cstockpropimpl::p ut_font](#put_font), jedoch mit einem Verweis Zähler.

##  <a name="putref_mouseicon"></a>Cstockpropimpl::p utref_mouseicon

Mit dieser Methode können Sie die Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatendatei) festlegen, die angezeigt werden soll, wenn sich der Mauszeiger über dem Steuerelement befindet, mit einem Verweis Zähler.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parameter

*ppicture*<br/>
Ein Zeiger auf die Bildeigenschaften der Grafik.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Identisch mit [cstockpropimpl::p ut_mouseicon](#put_mouseicon), jedoch mit einem Verweis Zähler.

##  <a name="putref_picture"></a>Cstockpropimpl::p utref_picture

Mit dieser Methode können Sie die Bildeigenschaften einer Grafik (Symbol, Bitmap oder Metadatei), die angezeigt werden soll, mit einem Verweis Zähler festlegen.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parameter

*ppicture*<br/>
Ein Zeiger auf die Eigenschaften des Bilds. Weitere Informationen finden Sie unter [IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp) .

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Identisch mit [cstockpropimpl::p ut_picture](#put_picture), jedoch mit einem Verweis Zähler.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[IDispatchImpl-Klasse](../../atl/reference/idispatchimpl-class.md)
