---
title: CMFCWindowsManagerDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: 5089decc7a118cd867aa14df51f5d7e269221108
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373660"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog-Klasse

Die `CMFCWindowsManagerDialog` Objekt kann ein Benutzer zum Verwalten von untergeordneten MDI-Fenster in einer MDI-Anwendung.

## <a name="syntax"></a>Syntax

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Erstellt ein `CMFCWindowsManagerDialog`-Objekt.|

## <a name="remarks"></a>Hinweise

Die `CMFCWindowsManagerDialog` enthält eine Liste von untergeordneten MDI-Fenster, die derzeit in der Anwendung geöffnet sind. Der Benutzer kann den Zustand des untergeordneten MDI-Fenster mithilfe dieses Dialogfelds manuell steuern.

`CMFCWindowsManagerDialog` eingebettet in der [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md). Die `CMFCWindowsManagerDialog` ist keine Klasse, die manuell erstellt werden soll. Rufen Sie stattdessen die Funktion [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), und er erstellt und zeigt eine `CMFCWindowsManagerDialog` Objekt.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCWindowsManagerDialog` Objekt durch Aufrufen von `CMDIFrameWndEx::ShowWindowsDialog`. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxWindowsManagerDialog.h

##  <a name="cmfcwindowsmanagerdialog"></a>  CMFCWindowsManagerDialog::CMFCWindowsManagerDialog

Erstellt eine [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) Objekt.

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>Parameter

*pMDIFrame*<br/>
[in] Ein Zeiger auf das übergeordnete Element oder Besitzer-Fenster.

*bHelpButton*<br/>
[in] Ein boolescher Parameter, der angibt, ob das Framework zeigt eine **Hilfe** Schaltfläche.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu Erscheinungsbild-Manager, finden Sie unter [Visualisierungs-Manager](../../mfc/visualization-manager.md).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md)
