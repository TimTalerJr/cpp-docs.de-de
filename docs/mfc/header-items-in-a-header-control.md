---
title: Headerelemente in einem Headersteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], header items in
- header items in header controls [MFC]
- CHeaderCtrl class [MFC], header items in
- controls [MFC], header
ms.assetid: ac79ef1f-a671-4ab2-93e9-b1aa016a48bf
ms.openlocfilehash: 31b6bcb134b62fc11df78a846b3c256a2ef69c14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239996"
---
# <a name="header-items-in-a-header-control"></a>Headerelemente in einem Headersteuerelement

Sie haben viel Kontrolle über das Aussehen und Verhalten des Header-Elemente, die einem Kopfzeilen-Steuerelement zu bilden ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)). Jedes Headerelement möglich, eine Zeichenfolge, eine Bitmap, ein Image aus einer Bildliste für die zugeordnete oder eine anwendungsdefinierte 32-Bit-Wert zugeordnet. Die Zeichenfolge, Bitmap oder Bild wird im Headerelement angezeigt.

Sie können die Darstellung und Inhalt der neuen Elemente anpassen, wenn sie erstellt werden, indem Sie einen Aufruf [InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem) oder durch Ändern eines vorhandenen Elements, mit einem Aufruf von [CHeaderCtrl:: GetItem](../mfc/reference/cheaderctrl-class.md#getitem) und [ CHeaderCtrl::SetItem](../mfc/reference/cheaderctrl-class.md#setitem).

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Anpassen von Headerelementen](../mfc/customizing-the-header-item-s-appearance.md)

- [Anordnen von Elementen im Headersteuerelement](../mfc/ordering-items-in-the-header-control.md)

- [Bereitstellen von Drag & Drop-Unterstützung für die Headerelemente](../mfc/providing-drag-and-drop-support-for-header-items.md)

- [Verwenden von Bildlisten in Headersteuerelementen](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)
