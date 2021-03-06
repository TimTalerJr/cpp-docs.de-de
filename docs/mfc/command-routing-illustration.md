---
title: Befehlsroutingerläuterung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
ms.openlocfilehash: 56d131151f2284f12a3b46a9acd3cfbd3c8b0f47
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164877"
---
# <a name="command-routing-illustration"></a>Befehlsroutingerläuterung

Um zu veranschaulichen, betrachten Sie eine Nachricht über ein Menüelement in einer MDI-Anwendung-Menü "Bearbeiten" Alle löschen aus. Nehmen wir an, dass die Handler-Funktion für diesen Befehl erfolgt eine Memberfunktion der Anwendung Dokumentklasse sein. Hier ist, wie dieses Befehls den Handler erreicht, nachdem der Benutzer das Menüelement auswählt:

1. Das Hauptrahmenfenster empfängt die Nachricht zuerst an.

1. Der MDI-Hauptrahmenfenster gibt dem momentan aktiven untergeordnete MDI-Fenster eine Möglichkeit, den Befehl behandeln.

1. Das standardmäßige routing von einem untergeordneten MDI-Rahmenfenster kann der Ansicht an der Befehlszeile vor dem Überprüfen ihre eigene meldungszuordnung.

1. Die Ansicht ihre eigene meldungszuordnung zuerst überprüft und als Nächstes den Befehl leitet kein Handler auf, suchen, an dessen zugeordnete Dokument.

1. Das Dokument überprüft seine meldungszuordnung und sucht nach einem Handler. Dieses Dokument-Memberfunktion aufgerufen wird, und das routing wird beendet.

Wenn das Dokument keinen Handler hatte, würden sie als Nächstes den Befehl an seine Dokumentvorlage weiterleiten. Klicken Sie dann würde der Befehl, um die Ansicht, und klicken Sie dann das Rahmenfenster zurück. Das Rahmenfenster würde seine meldungszuordnung, aktivieren Sie zum Schluss. Wenn auch die Überprüfung fehlgeschlagen ist, würde der Befehl zurück an die Haupt-MDI-Rahmenfenster und dann auf das Anwendungsobjekt weitergeleitet werden, das endgültige Ziel nicht behandelten Befehle.

## <a name="see-also"></a>Siehe auch

[So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)
