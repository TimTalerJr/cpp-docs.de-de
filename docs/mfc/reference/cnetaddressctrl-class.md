---
title: CNetAddressCtrl-Klasse
ms.date: 11/19/2018
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
ms.openlocfilehash: 5e485c22bcc4bf35f61226d84345102052689f89
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69504536"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl-Klasse

Die Klasse `CNetAddressCtrl` stellt das Netzwerkadressen-Steuerelement dar, das verwendet werden kann, um IPv4-, IPv6- und benannte DNS-Adressen einzugeben und ihr Format zu überprüfen.

## <a name="syntax"></a>Syntax

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Erstellt ein `CNetAddressCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CNetAddressCtrl::Create](#create)|Erstellt ein Netzwerk Adress Steuerelement mit angegebenen Stilen und fügt es an das `CNetAddressCtrl` aktuelle-Objekt an.|
|[CNetAddressCtrl::CreateEx](#createex)|Erstellt ein Netzwerk Adress Steuerelement mit den angegebenen erweiterten Stilen und fügt es an `CNetAddressCtrl` das aktuelle-Objekt an.|
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Zeigt eine Fehler Sprechblasen Info an, wenn der Benutzer eine nicht unterstützte Netzwerkadresse in der aktuellen Netzwerk Adress Steuerung eingibt.|
|[CNetAddressCtrl::GetAddress](#getaddress)|Ruft eine validierte und analysierte Darstellung der Netzwerkadresse ab, die dem aktuellen Netzwerk Adress Steuerelement zugeordnet ist.|
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Ruft den Typ der Netzwerkadresse ab, die vom aktuellen Netzwerk Adress Steuerelement unterstützt werden kann.|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Legt den Typ der Netzwerkadresse fest, die vom aktuellen Netzwerk Adress Steuerelement unterstützt werden kann.|

## <a name="remarks"></a>Hinweise

Das Netzwerk Adress Steuerelement überprüft, ob das Format der Adresse, die der Benutzer eingibt, korrekt ist. Das-Steuerelement stellt keine Verbindung mit der Netzwerkadresse her. Die [CNetAddressCtrl:: abtallowtype](#setallowtype) -Methode gibt einen oder mehrere Typen von Adressen an, die die [CNetAddressCtrl:: GetAddress](#getaddress) -Methode analysieren und überprüfen kann. Eine Adresse kann in Form einer IPv4-, IPv6-oder benannten Adresse für ein Server-, Netzwerk-, Host-oder Broadcast Nachrichten Ziel vorliegen. Wenn das Format der Adresse falsch ist, können Sie die [CNetAddressCtrl::D isplayerrortip](#displayerrortip) -Methode verwenden, um ein Infotipp-Meldungs Feld anzuzeigen, das grafisch auf das Textfeld des Netzwerk Adress Steuer Elements zeigt und eine vordefinierte Fehlermeldung anzeigt.

Die `CNetAddressCtrl` -Klasse wird von der [CEdit](../../mfc/reference/cedit-class.md) -Klasse abgeleitet. Folglich bietet das Netzwerk Adress Steuerelement Zugriff auf alle Windows-Bearbeitungs Steuerelement-Meldungen.

In der folgenden Abbildung wird ein Dialogfeld angezeigt, das ein Netzwerk Adress Steuerelement enthält. Das Textfeld (1) für das Netzwerk Adress Steuerelement enthält eine ungültige Netzwerkadresse. Die Infotipp-Nachricht (2) wird angezeigt, wenn die Netzwerkadresse ungültig ist.

![Dialog Feld mit einem Netzwerk Adress Steuerelement und infotip.](../../mfc/reference/media/cnetaddctrl.png "Dialog Feld mit einem Netzwerk Adress Steuerelement und infotip.")

## <a name="example"></a>Beispiel

Das folgende Codebeispiel ist ein Teil eines Dialog Felds, in dem eine Netzwerkadresse überprüft wird. Mit den Ereignis Handlern für drei Options Felder wird angegeben, dass die Netzwerkadresse einen von drei Adresstypen aufweisen kann. Der Benutzer gibt eine Adresse in das Textfeld des Netzwerk Steuer Elements ein und drückt dann eine Schaltfläche, um die Adresse zu überprüfen. Wenn die Adresse gültig ist, wird eine Erfolgsmeldung angezeigt. Andernfalls wird die vordefinierte Infotipp-Fehlermeldung angezeigt.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>Beispiel

Mit dem folgenden Codebeispiel aus der Dialog Header Datei werden die Variablen [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) und [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) definiert, die für die [CNetAddressCtrl:: GetAddress](#getaddress) -Methode erforderlich sind.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

Diese Klasse wird in Windows Vista und höher unterstützt.

Weitere Anforderungen für diese Klasse werden unter [Buildanforderungen für allgemeine Windows Vista](../../mfc/build-requirements-for-windows-vista-common-controls.md)-Steuerelemente beschrieben.

##  <a name="cnetaddressctrl"></a>CNetAddressCtrl:: CNetAddressCtrl

Erstellt ein `CNetAddressCtrl`-Objekt.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie die Methode [CNetAddressCtrl:: Create](#create) oder [CNetAddressCtrl::](#createex) -Methode, um ein Netzwerk Steuerelement zu erstellen, und `CNetAddressCtrl` fügen Sie es an das-Objekt an.

##  <a name="create"></a>CNetAddressCtrl:: Create

Erstellt ein Netzwerk Adress Steuerelement mit angegebenen Stilen und fügt es an das `CNetAddressCtrl` aktuelle-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwStyle*|in Eine bitweise Kombination von Stilen, die auf das-Steuerelement angewendet werden sollen. Weitere Informationen finden Sie unter [Bearbeiten von Stilen](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*Rect*|in Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Position und Größe des Steuer Elements enthält.|
|*pParentWnd*|in Ein nicht-NULL-Zeiger auf ein [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuer Elements ist.|
|*nID*|in Die ID des Steuer Elements.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

##  <a name="createex"></a>CNetAddressCtrl:: kreateex

Erstellt ein Netzwerk Adress Steuerelement mit den angegebenen erweiterten Stilen und fügt es an `CNetAddressCtrl` das aktuelle-Objekt an.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwExStyle*|in Eine bitweise Kombination (oder) erweiterter Stile, die auf das-Steuerelement angewendet werden sollen. Weitere Informationen finden Sie unter dem *dwExStyle* -Parameter der Funktion " [deatewindowex](/windows/win32/api/winuser/nf-winuser-createwindowexw) ".|
|*dwStyle*|in Eine bitweise Kombination (or) der Stile, die auf das-Steuerelement angewendet werden sollen. Weitere Informationen finden Sie unter [Bearbeiten von Stilen](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*Rect*|in Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Position und Größe des Steuer Elements enthält.|
|*pParentWnd*|in Ein nicht-NULL-Zeiger auf ein [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuer Elements ist.|
|*nID*|in Die ID des Steuer Elements.|

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

##  <a name="displayerrortip"></a>CNetAddressCtrl::D isplayerrortip

Zeigt eine Fehlermeldung in der Sprechblasen Info an, die dem aktuellen Netzwerk Adress Steuerelement zugeordnet ist.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Rückgabewert

Der- `S_OK` Wert, wenn diese Methode erfolgreich ist, andernfalls ein Fehlercode.

### <a name="remarks"></a>Hinweise

Verwenden Sie die Methode [CNetAddressCtrl:: abtallowtype](#setallowtype) , um die Typen von Adressen anzugeben, die das aktuelle Netzwerk Adress Steuerelement unterstützen kann. Verwenden Sie die [CNetAddressCtrl:: GetAddress](#getaddress) -Methode, um die vom Benutzer eingegebene Netzwerkadresse zu überprüfen und zu analysieren. Verwenden Sie die [CNetAddressCtrl::D isplayerrortip](#displayerrortip) -Methode, um einen InfoTipp für eine Fehlermeldung anzuzeigen, wenn die [CNetAddressCtrl:: GetAddress](#getaddress) -Methode nicht erfolgreich ist.

Diese Meldung Ruft das [NetAddr_DisplayErrorTip](/windows/win32/api/shellapi/nf-shellapi-netaddr_displayerrortip) -Makro auf, das in der Windows SDK beschrieben wird. Dieses Makro sendet die `NCM_DISPLAYERRORTIP` Nachricht.

##  <a name="getaddress"></a>CNetAddressCtrl:: GetAddress

Ruft eine validierte und analysierte Darstellung der Netzwerkadresse ab, die dem aktuellen Netzwerk Adress Steuerelement zugeordnet ist.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>Parameter

*pAddress*<br/>
[in, out] Zeiger auf eine [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) -Struktur.  Legen Sie den *paddrinfo* -Member dieser Struktur auf die Adresse einer [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) -Struktur fest, bevor Sie die GetAddress-Methode aufrufen.

### <a name="return-value"></a>Rückgabewert

Der Wert S_OK, wenn diese Methode erfolgreich ist. andernfalls ein com-Fehlercode. Weitere Informationen zu den möglichen Fehlercodes finden Sie im Abschnitt "Rückgabewert" des [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) -Makros.

### <a name="remarks"></a>Hinweise

Wenn diese Methode erfolgreich ist, enthält die [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) -Struktur zusätzliche Informationen über die Netzwerkadresse.

Verwenden Sie die Methode [CNetAddressCtrl:: abtallowtype](#setallowtype) , um die Typen von Adressen anzugeben, die das aktuelle Netzwerk Adress Steuerelement unterstützen kann. Verwenden Sie die [CNetAddressCtrl:: GetAddress](#getaddress) -Methode, um die vom Benutzer eingegebene Netzwerkadresse zu überprüfen und zu analysieren. Verwenden Sie die [CNetAddressCtrl::D isplayerrortip](#displayerrortip) -Methode, um einen InfoTipp für eine Fehlermeldung anzuzeigen, wenn die [CNetAddressCtrl:: GetAddress](#getaddress) -Methode nicht erfolgreich ist.

Diese Methode ruft das [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) -Makro auf, das im Windows SDK beschrieben wird. Dieses Makro sendet die NCM_GETADDRESS-Nachricht.

##  <a name="getallowtype"></a>CNetAddressCtrl:: getallowtype

Ruft den Typ der Netzwerkadresse ab, die vom aktuellen Netzwerk Adress Steuerelement unterstützt werden kann.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Rückgabewert

Eine bitweise Kombination (or) von Flags, die die Typen von Adressen angibt, die das Netzwerk Adress Steuerelement unterstützen kann. Weitere Informationen finden Sie unter [NET_STRING](/windows/win32/shell/net-string).

### <a name="remarks"></a>Hinweise

Diese Meldung Ruft das [NetAddr_GetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_getallowtype) -Makro auf, das in der Windows SDK beschrieben wird. Dieses Makro sendet die NCM_GETALLOWTYPE-Nachricht.

##  <a name="setallowtype"></a>CNetAddressCtrl:: cnetlowtype

Legt den Typ der Netzwerkadresse fest, die vom aktuellen Netzwerk Adress Steuerelement unterstützt werden kann.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwAddrMask*|in Eine bitweise Kombination (or) von Flags, die die Typen von Adressen angibt, die das Netzwerk Adress Steuerelement unterstützen kann. Weitere Informationen finden Sie unter [NET_STRING](/windows/win32/shell/net-string).|

### <a name="return-value"></a>Rückgabewert

S_OK, wenn diese Methode erfolgreich ist. andernfalls ein com-Fehlercode.

### <a name="remarks"></a>Hinweise

Verwenden Sie die Methode [CNetAddressCtrl:: abtallowtype](#setallowtype) , um die Typen von Adressen anzugeben, die das aktuelle Netzwerk Adress Steuerelement unterstützen kann. Verwenden Sie die [CNetAddressCtrl:: GetAddress](#getaddress) -Methode, um die vom Benutzer eingegebene Netzwerkadresse zu überprüfen und zu analysieren. Verwenden Sie die [CNetAddressCtrl::D isplayerrortip](#displayerrortip) -Methode, um einen InfoTipp für eine Fehlermeldung anzuzeigen, wenn die [CNetAddressCtrl:: GetAddress](#getaddress) -Methode nicht erfolgreich ist.

Diese Meldung Ruft das [NetAddr_SetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_setallowtype) -Makro auf, das in der Windows SDK beschrieben wird. Dieses Makro sendet die NCM_SETALLOWTYPE-Nachricht.

## <a name="see-also"></a>Siehe auch

[CNetAddressCtrl-Klasse](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)
