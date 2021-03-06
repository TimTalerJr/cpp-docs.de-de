---
title: Befehlsobjekt-Schnittstellen
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: 755c44cf8d0cb5bf5066197bfd0ead3e0f25e1f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216368"
---
# <a name="command-object-interfaces"></a>Befehlsobjekt-Schnittstellen

Das Befehlsobjekt verwendet die `IAccessor` Schnittstelle parameterbindungen angeben. Der Consumer ruft `IAccessor::CreateAccessor`, übergibt ein Array von `DBBINDING` Strukturen. `DBBINDING` enthält Informationen über die spaltenbindungen (z. B. Typ und Länge). Der Anbieter empfängt die Strukturen und bestimmt, wie die Daten übertragen werden sollen, und gibt an, ob Konvertierungen erforderlich sind.

Die `ICommandText` Schnittstelle bietet eine Möglichkeit, einen Text-Befehl anzugeben. Die `ICommandProperties` Schnittstelle verarbeitet alle Befehlseigenschaften.

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
