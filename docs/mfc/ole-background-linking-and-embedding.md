---
title: 'OLE-Hintergrund: Verlinken und einbetten | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ecbc8bb39d9cba3a5d13567811221fe0a703ab5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ole-background-linking-and-embedding"></a>OLE-Hintergrund: Verlinken und Einbetten
Mit dem Befehl Einfügen in eine Steuerelementcontainer-Anwendung kann eine eingebettete Komponente oder ein eingebettetes Element erstellt. Die Quelldaten für ein eingebettetes Element werden als Teil des OLE-Dokuments gespeichert, die es enthält. Auf diese Weise wird eine Dokumentdatei für ein Textverarbeitungsprogramm-Dokument kann Text enthalten und dürfen auch Bitmaps, Diagramme, Formeln oder andere Arten von Daten.  
  
 OLE bietet eine andere Möglichkeit, Daten aus einer anderen Anwendung einzubinden: Erstellen einer verknüpften Komponente oder verknüpftes Element oder ein Link. Die Schritte zum Erstellen eines verknüpften Elements ähneln denen zum Erstellen eines eingebetteten-Elements, außer dass Sie die Verknüpfung einfügen statt der Paste-Befehl verwenden. Im Gegensatz zu einer eingebetteten Komponente speichert eine verknüpfte Komponente einen Pfad zu der ursprünglichen Daten, die häufig in einer separaten Datei ist.  
  
 Wenn Sie in einem Wort Prozessor Dokuments arbeiten und ein verknüpftes Element auf einige Tabellenzellen zu erstellen, ist z. B. die Daten für das verknüpfte Element im ursprünglichen Arbeitsblatt Dokument gespeichert. Das Textverarbeitungsprogramm-Dokument enthält nur die Informationen, die angeben, in dem das Element, d. h. gefunden werden können sie einen Link zum ursprünglichen Arbeitsblatt Dokument enthält. Wenn Sie die Zellen doppelklicken, die Spreadsheet-Anwendung wird gestartet, und das Originaldokument Kalkulationstabelle aus, in dem es gespeichert wurde geladen.  
  
 Jeder OLE-Element hat, ob eingebettete oder verknüpfte, einen Typ zugeordnet basierend auf der Anwendung, die sie erstellt haben. Angenommen, ein Microsoft Paintbrush-Element ist ein Typ des Elements, und ein Microsoft Excel-Element ist ein anderer Typ. Einige Anwendungen können jedoch mehrere Elementtyp erstellen. Microsoft Excel können z. B. Arbeitsblatt Elemente Diagrammelemente und Makro wurde Elemente erstellen. Jedes dieser Elemente kann eindeutig identifiziert durch das System über eine Klassen-ID oder **CLSID**.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE-Hintergrund](../mfc/ole-background.md)   
 [OLE-Hintergrund: Container und Server](../mfc/ole-background-containers-and-servers.md)   
 [Container: Clientelemente](../mfc/containers-client-items.md)   
 [Server: Serverelemente](../mfc/servers-server-items.md)
