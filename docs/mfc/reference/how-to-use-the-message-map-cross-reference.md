---
title: 'Vorgehensweise: Verwenden des Meldungszuordnungs-Querverweises | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.messages
dev_langs: C++
helpviewer_keywords: windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ffa7b39962d78476e971750e92569eb14229606b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Gewusst wie: Verwenden des Meldungszuordnungs-Querverweises
In Einträge, die mit der Bezeichnung \<MemberFxn >, Schreiben Sie eine eigene Memberfunktion für eine abgeleitete [CWnd](../../mfc/reference/cwnd-class.md) Klasse. Geben Sie der Funktion einen beliebigen Namen, den Ihnen gefallen. Andere Funktionen wie `OnActivate`, werden die Memberfunktionen der Klasse `CWnd`. Wenn Sie aufgerufen wird, übergeben sie die Nachricht an die `DefWindowProc` Windows-Funktion. Um die Windows-benachrichtigungsmeldungen zu verarbeiten, überschreiben Sie die entsprechende `CWnd` Funktion in der abgeleiteten Klasse. Ihre Funktion sollte außer Kraft gesetzte-Funktion in Ihrer Basisklasse, mit der Basisklasse aufrufen, und Windows auf die Meldung reagieren.  
  
 Fügen Sie den Funktionsprototyp in allen Fällen, in der `CWnd`-Header der abgeleiteten Klasse, und Code Zuordnungseintrags Nachricht wie dargestellt.  
  
 Die folgenden Begriffe werden verwendet:  
  
|Begriff|Definition|  
|----------|----------------|  
|ID|Alle benutzerdefinierten Menü-Element-ID (**WM_COMMAND** Nachrichten) oder die control-ID (untergeordnete fenstermeldungen Benachrichtigung).|  
|"Nachricht" und "wNotifyCode schalten"|Der Windows-Meldung IDs gemäß Definition in WINDOWS. H.|  
|nMessageVariable|Name einer Variablen, die den Rückgabewert enthält die **RegisterWindowMessage registriert** Windows-Funktion.|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)
