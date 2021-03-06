---
title: Abgeleitete Fensterklassen
ms.date: 11/04/2016
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
ms.openlocfilehash: e86ca139b8470dce614564f0c0134a611adeda2c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153373"
---
# <a name="derived-window-classes"></a>Abgeleitete Fensterklassen

Sie können Fenster direkt aus erstellen [CWnd](../mfc/reference/cwnd-class.md), oder Sie leiten neue Fensterklassen von `CWnd`. Im Allgemeinen erstellen Sie eigene, benutzerdefinierte Fenster auf diese Weise. Allerdings werden die meisten Fenster, die in einem Frameworkprogramm verwendet werden, stattdessen aus einer der von MFC bereitgestellten, von `CWnd` abgeleiteten Rahmenfensterklassen erstellt.

## <a name="frame-window-classes"></a>Klassen für Rahmenfenster

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
Wird für SDI-Rahmenfenster verwendet, um ein einzelnes Dokument und dessen Ansicht zu gestalten. Das Rahmenfenster ist sowohl das Hauptrahmenfenster für die Anwendung als auch das Rahmenfenster für das aktuelle Dokument.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
Wird als Hauptrahmenfenster für MDI-Anwendungen verwendet. Das Hauptrahmenfenster ist ein Container für alle MDI-Dokumentfenster und gibt seine Menüleiste für diese frei. Ein MDI-Rahmenfenster ist ein Fenster der obersten Ebene, das auf dem Desktop angezeigt wird.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
Wird für einzelne Dokumente verwendet, die in einem MDI-Hauptrahmenfenster geöffnet werden. Jedes Dokument und seine Ansicht werden durch ein untergeordnetes MDI-Rahmenfenster eingerahmt, das im MDI-Hauptrahmenfenster enthalten ist. Ein untergeordnetes MDI-Fenster sieht einem typischen Rahmenfenster sehr ähnlich. Es befindet sich aber nicht auf dem Desktop, sondern bleibt in einem MDI-Rahmenfenster. Dem untergeordneten MDI-Fenster fehlt allerdings eine eigene Menüleiste, sodass es die Menüleiste des MDI-Rahmenfensters mitverwenden muss, in dem es enthalten ist.

Weitere Informationen finden Sie unter [Frame Windows](../mfc/frame-windows.md).

## <a name="other-window-classes-derived-from-cwnd"></a>Andere Fensterklassen, die von "CWnd" abgeleitet werden

Zusätzlich zu den Rahmenfenstern werden mehrere andere Hauptkategorien von Fenstern von `CWnd` abgeleitet:

*Ansichten*<br/>
Sichten werden erstellt, mit der `CWnd`-abgeleitete Klasse [CView](../mfc/reference/cview-class.md) (oder einer ihrer abgeleiteten Klassen). Eine Ansicht wird an ein Dokument angefügt und dient als Vermittler zwischen dem Dokument und dem Benutzer. Eine Ansicht ist ein untergeordnetes Fenster (kein untergeordnetes MDI-Fenster), das normalerweise den Clientbereich eines SDI-Rahmenfensters oder eines untergeordneten MDI-Rahmenfensters ausfüllt (oder den Teil des Clientbereichs, der nicht von einer Symbolleiste und/oder einer Statusleiste abgedeckt ist).

*Dialogfelder*<br/>
Dialogfelder werden erstellt, mit der `CWnd`-abgeleitete Klasse [CDialog](../mfc/reference/cdialog-class.md).

*Formulare*<br/>
Formularansichten basierend auf Dialogfeld-Vorlagenressourcen, z. B. Dialogfelder, werden mithilfe von Klassen erstellt [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), oder [CDaoRecordView](../mfc/reference/cdaorecordview-class.md).

*Steuerelemente*<br/>
Steuerelemente wie Schaltflächen, Listenfelder und Kombinationsfelder werden mithilfe anderer Klassen erstellt, die von `CWnd` abgeleitet werden. Finden Sie unter [steuern Themen](../mfc/controls-mfc.md).

*Steuerleisten*<br/>
Untergeordnete Fenster, die Steuerelemente enthalten. Dazu zählen beispielsweise Symbolleisten und Statusleisten. Finden Sie unter [Steuerleisten](../mfc/control-bars.md).

## <a name="window-class-hierarchy"></a>Fensterklassenhierarchie

Finden Sie in der [MFC-Hierarchiediagramm](../mfc/hierarchy-chart.md) in die *MFC-Referenz*. Ansichten werden in erläutert [Dokument-/Ansichtarchitektur](../mfc/document-view-architecture.md). Dialogfelder werden in erläutert [Dialogfelder](../mfc/dialog-boxes.md).

## <a name="creating-your-own-special-purpose-window-classes"></a>Erstellen eigener Fensterklassen für spezielle Zwecke

Neben den Fensterklassen, die von der Klassenbibliothek bereitgestellt werden, benötigen Sie möglicherweise untergeordnete Fenster für besondere Zwecke. Um ein solches Fenster zu erstellen, erstellen Sie Ihre eigenen [CWnd](../mfc/reference/cwnd-class.md)-abgeleitete Klasse, und legen Sie ihn in ein untergeordnetes Fenster von einem Frame oder das anzeigen. Bedenken Sie, dass das Framework den Umfang des Clientbereichs von einem Dokumentrahmenfenster verwaltet. Die Großteil des Clientbereichs wird durch eine Ansicht verwaltet, aber andere Fenster, z. B. Steuerleisten oder eigene, benutzerdefinierte Fenster, können sich den Platz mit der Ansicht teilen. Möglicherweise müssen Sie die Interaktion mit den Mechanismen in den Klassen [CView](../mfc/reference/cview-class.md) und [CControlBar](../mfc/reference/ccontrolbar-class.md) zum Positionieren der untergeordneten Fenster im Clientbereich eines Fensters Frame.

[Erstellen von Windows](../mfc/creating-windows.md) Erläuterung zur Erstellung von Fensterobjekten und den Windows, die sie verwalten.

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)
