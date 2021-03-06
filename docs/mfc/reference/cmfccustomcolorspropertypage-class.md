---
title: CMFCCustomColorsPropertyPage-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: b28711991835dd14929e5387709046c3867c715e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403697"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage-Klasse

Stellt eine Eigenschaft dar, die Farben in einem Farbendialogfeld auswählen können.

## <a name="syntax"></a>Syntax

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|Standardkonstruktor|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|`CMFCCustomColorsPropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCCustomColorsPropertyPage::Setup](#setup)|Legt die Farbe Komponenten der Eigenschaftenseite fest.|

### <a name="remarks"></a>Hinweise

Die `CMFCColorDialog` Klasse verwendet diese Klasse, um die Eigenschaftenseite für die benutzerdefinierte Farbe anzuzeigen. Weitere Informationen zu `CMFCColorDialog`, finden Sie unter [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCCustomColorsPropertyPage` Objekt, und legen Sie die Komponenten der Farbe der Eigenschaftenseite.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxcustomcolorspropertypage.h

##  <a name="setup"></a>  CMFCCustomColorsPropertyPage::Setup

Legt die Farbe Komponenten der Eigenschaftenseite fest.

```
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*R*|[in] Der roten Anteil der RGB-Wert.|
|*G*|[in] Der grünen Anteil der RGB-Wert.|
|*B*|[in] Die blaue Komponente des RGB-Werts.|

### <a name="remarks"></a>Hinweise

Diese Methode aktualisiert die aktuellen RGB- und die zugehörigen HLS (Hue, Helligkeit und Sättigung) Farbwerte der Eigenschaftenseite. Die [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) -Methode ruft diese Methode auf, wenn das Framework das Dialogfeld Farbe initialisiert oder der Benutzer die linke Maustaste gedrückt drückt. Weitere Informationen zu `CMFCColorDialog`, finden Sie unter [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCStandardColorsPropertyPage-Klasse](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
