---
title: CMFCAcceleratorKey-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
ms.openlocfilehash: 6a99ad00a43ac7912320ee469d542b6bf9cca3de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403957"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey-Klasse

Eine Hilfsklasse, die virtuelle tastenzuordnung und Formatierung implementiert.

## <a name="syntax"></a>Syntax

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Erstellt ein `CMFCAcceleratorKey`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCAcceleratorKey::Format](#format)|Übersetzt die ACCELERATION-Struktur, die die visuelle Darstellung.|
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Legt die Tastenkombination für den `CMFCAcceleratorKey` Objekt.|

## <a name="remarks"></a>Hinweise

Zugriffstasten werden auch Tastenkombinationen. Wenn Sie möchten, um Tastenkombinationen anzuzeigen, die ein Benutzer eingibt, die [CMFCAcceleratorKeyAssignCtrl-Klasse](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) Zuordnungen Tastenkombinationen, z. B. die ALT-Taste + UMSCHALT + S, um eine benutzerdefinierte Text-Format, z. B. "Alt + Umschalt + S". Jede `CMFCAcceleratorKey` Objekt wird als TXT-Datei eine einzelnen Tastenkombination zugeordnet.

Weitere Informationen zur Verwendung von Tastenkombinationen und Zugriffstastentabellen finden Sie unter [CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCAcceleratorKey` -Objekt und wie Sie mit der `Format` Methode.

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>Anforderungen

**Header:** afxacceleratorkey.h

##  <a name="cmfcacceleratorkey"></a>  CMFCAcceleratorKey::CMFCAcceleratorKey

Erstellt eine [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) Objekt.

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parameter

*lpAccel*<br/>
[in] Ein Zeiger auf eine Tastenkombination.

### <a name="remarks"></a>Hinweise

Wenn Sie eine Tastenkombination nicht angeben, bei der Erstellung einer `CMFCAccleratorKey`, verwenden die [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) Methode, um eine Tastenkombination mit zuordnen Ihrer `CMFCAcceleratorKey` Objekt.

##  <a name="format"></a>  CMFCAcceleratorKey::Format

Übersetzt die ACCELERATION-Struktur, auf den Wert für die zugeordnete Zeichenfolge.

```
void Format(CString& str) const;
```

### <a name="parameters"></a>Parameter

*str*<br/>
[out] Ein Verweis auf eine `CString` Objekt, in denen die Methode die übersetzten Tastenkombination schreibt.

### <a name="remarks"></a>Hinweise

Diese Methode ruft das Zeichenfolgenformat der zugeordneten Tastenkombination ab. Sie können festlegen, der das Format der Zeichenfolge ein [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) Objekt mit dem Konstruktor oder die Methode [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).

##  <a name="setaccelerator"></a>  CMFCAcceleratorKey::SetAccelerator

Legt die Tastenkombination für den [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) Objekt.

```
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>Parameter

*lpAccel*<br/>
[in] Ein Zeiger auf eine Tastenkombination.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie die Tastenkombination festlegen einer `CMFCAcceleratorKey` , wenn Sie eine Tastenkombination nicht angegeben haben, bei der Erstellung der `CMFCAcceleratorKey`.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager-Klasse](../../mfc/reference/ckeyboardmanager-class.md)
