---
title: Empfangen von Benachrichtigungen
ms.date: 10/24/2018
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
ms.openlocfilehash: b35c1d3d6ff7d5d74493e843575f7448c4df8d8f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283799"
---
# <a name="receiving-notifications"></a>Empfangen von Benachrichtigungen

OLE DB stellt Schnittstellen bereit, für den Empfang von Benachrichtigungen, wenn Ereignisse auftreten. Diese werden beschrieben [OLE DB-Objekt Benachrichtigungen](/previous-versions/windows/desktop/ms725406(v=vs.85)) in die **OLE DB-Programmierreferenz**. Setup dieser Ereignisse wird den COM-Verbindungspunkt Standardmechanismus verwendet. Z. B. ein ATL-Objekt, das Ereignisse über abrufen möchte `IRowsetNotify` implementiert die `IRowsetNotify` -Schnittstelle durch Hinzufügen von `IRowsetNotify` auf die abgeleitete Klasse-Liste, und es über ein COM_INTERFACE_ENTRY-Makro verfügbar zu machen.

`IRowsetNotify` verfügt über drei Methoden, die zu verschiedenen Zeiten aufgerufen werden können. Wenn Sie nur eine dieser Methoden reagieren möchten, können Sie mithilfe der [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) -Klasse, die für die Methoden gibt E_NOTIMPL zurück Sie nicht interessiert sind.

Bei der Erstellung des Rowsets müssen Sie dem Anbieter anweisen, wirklich das zurückgegebene Rowset-Objekt, unterstützt `IConnectionPointContainer`, das ist erforderlich, um die Benachrichtigung eingerichtet.

Der folgende Code zeigt, öffnen Sie das Rowset von einem ATL-Objekt, und Verwenden der `AtlAdvise` Funktion, um den Benachrichtigungsempfänger einzurichten. `AtlAdvise` Gibt ein Cookie, das verwendet wird, wenn Sie aufrufen `AtlUnadvise`.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

Klicken Sie dann verwendet mit dem folgenden Code:

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>Siehe auch

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)