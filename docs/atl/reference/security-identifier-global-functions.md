---
title: Globale Sicherheitsfunktionen für Bezeichner
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::Sids::AccountOps
- atlsecurity/ATL::Sids::Admins
- atlsecurity/ATL::Sids::AnonymousLogon
- atlsecurity/ATL::Sids::AuthenticatedUser
- atlsecurity/ATL::Sids::BackupOps
- atlsecurity/ATL::Sids::Batch
- atlsecurity/ATL::Sids::CreatorGroup
- atlsecurity/ATL::Sids::CreatorGroupServer
- atlsecurity/ATL::Sids::CreatorOwner
- atlsecurity/ATL::Sids::CreatorOwnerServer
- atlsecurity/ATL::Sids::Dialup
- atlsecurity/ATL::Sids::Guests
- atlsecurity/ATL::Sids::Interactive
- atlsecurity/ATL::Sids::Local
- atlsecurity/ATL::Sids::Network
- atlsecurity/ATL::Sids::NetworkService
- atlsecurity/ATL::Sids::Null
- atlsecurity/ATL::Sids::PowerUsers
- atlsecurity/ATL::Sids::PrintOps
- atlsecurity/ATL::Sids::Proxy
- atlsecurity/ATL::Sids::RasServers
- atlsecurity/ATL::Sids::Replicator
- atlsecurity/ATL::Sids::RestrictedCode
- atlsecurity/ATL::Sids::Self
- atlsecurity/ATL::Sids::ServerLogon
- atlsecurity/ATL::Sids::Service
- atlsecurity/ATL::Sids::System
- atlsecurity/ATL::Sids::SystemOps
- atlsecurity/ATL::Sids::TerminalServer
- atlsecurity/ATL::Sids::Users
- atlsecurity/ATL::Sids::World
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
ms.openlocfilehash: ab5d743c7c6abf7ee3a849a28916ebd32788ef40
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274944"
---
# <a name="security-identifier-global-functions"></a>Globale Sicherheitsfunktionen für Bezeichner

Diese Funktionen geben häufig bekannte SID Objekte zurück.

> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[Sids::AccountOps](#accountops)|Gibt die DOMAIN_ALIAS_RID_ACCOUNT_OPS-SID zurück.|
|[Sids::Admins](#admins)|Gibt die DOMAIN_ALIAS_RID_ADMINS-SID zurück.|
|[Sids::AnonymousLogon](#anonymouslogon)|Gibt die SECURITY_ANONYMOUS_LOGON_RID-SID zurück.|
|[Sids::AuthenticatedUser](#authenticateduser)|Gibt die SECURITY_AUTHENTICATED_USER_RID-SID zurück.|
|[Sids::BackupOps](#backupops)|Gibt die DOMAIN_ALIAS_RID_BACKUP_OPS-SID zurück.|
|[Sids::Batch](#batch)|Gibt die SECURITY_BATCH_RID-SID zurück.|
|[Sids::CreatorGroup](#creatorgroup)|Gibt die SECURITY_CREATOR_GROUP_RID-SID zurück.|
|[Sids::CreatorGroupServer](#creatorgroupserver)|Gibt die SECURITY_CREATOR_GROUP_SERVER_RID-SID zurück.|
|[Sids::CreatorOwner](#creatorowner)|Gibt die SECURITY_CREATOR_OWNER_RID-SID zurück.|
|[Sids::CreatorOwnerServer](#creatorownerserver)|Gibt die SECURITY_CREATOR_OWNER_SERVER_RID-SID zurück.|
|[Sids::Dialup](#dialup)|Gibt die SECURITY_DIALUP_RID-SID zurück.|
|[Sids::Guests](#guests)|Gibt die DOMAIN_ALIAS_RID_GUESTS-SID zurück.|
|[Sids::Interactive](#interactive)|Gibt die SECURITY_INTERACTIVE_RID-SID zurück.|
|[Sids::Local](#local)|Gibt die SECURITY_LOCAL_RID-SID zurück.|
|[Sids::Network](#network)|Gibt die SECURITY_NETWORK_RID-SID zurück.|
|[Sids::NetworkService](#networkservice)|Gibt die SECURITY_NETWORK_SERVICE_RID-SID zurück.|
|[Sids::Null](#null)|Gibt die SECURITY_NULL_RID-SID zurück.|
|[Sids::PreW2KAccess](#prew2kaccess)|Gibt die DOMAIN_ALIAS_RID_PREW2KCOMPACCESS-SID zurück.|
|[Sids::PowerUsers](#powerusers)|Gibt die DOMAIN_ALIAS_RID_POWER_USERS-SID zurück.|
|[Sids::PrintOps](#printops)|Gibt die DOMAIN_ALIAS_RID_PRINT_OPS-SID zurück.|
|[Sids::Proxy](#proxy)|Gibt die SECURITY_PROXY_RID-SID zurück.|
|[Sids::RasServers](#rasservers)|Gibt die DOMAIN_ALIAS_RID_RAS_SERVERS-SID zurück.|
|[Sids::Replicator](#replicator)|Gibt die DOMAIN_ALIAS_RID_REPLICATOR-SID zurück.|
|[Sids::RestrictedCode](#restrictedcode)|Gibt die SECURITY_RESTRICTED_CODE_RID-SID zurück.|
|[Sids::Self](#self)|Gibt die SECURITY_PRINCIPAL_SELF_RID-SID zurück.|
|[Sids::ServerLogon](#serverlogon)|Gibt die SECURITY_SERVER_LOGON_RID-SID zurück.|
|[Sids::Service](#service)|Gibt die SECURITY_SERVICE_RID-SID zurück.|
|[Sids::System](#system)|Gibt die SECURITY_LOCAL_SYSTEM_RID-SID zurück.|
|[Sids::SystemOps](#systemops)|Gibt die DOMAIN_ALIAS_RID_SYSTEM_OPS-SID zurück.|
|[Sids::TerminalServer](#terminalserver)|Gibt die SECURITY_TERMINAL_SERVER_RID-SID zurück.|
|[Sids::Users](#users)|Gibt die DOMAIN_ALIAS_RID_USERS-SID zurück.|
|[Sids::World](#world)|Gibt die SECURITY_WORLD_RID-SID zurück.|

### <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="accountops"></a>  Sids::AccountOps

Gibt die DOMAIN_ALIAS_RID_ACCOUNT_OPS-SID zurück.

```
CSid AccountOps() throw(...);
```

##  <a name="admins"></a>  SIDs::Admins

Gibt die DOMAIN_ALIAS_RID_ADMINS-SID zurück.

```
CSid Admins() throw(...);
```

##  <a name="anonymouslogon"></a>  SIDs::AnonymousLogon

Gibt die SECURITY_ANONYMOUS_LOGON_RID-SID zurück.

```
CSid AnonymousLogon() throw(...);
```

##  <a name="authenticateduser"></a>  SIDs::AuthenticatedUser

Gibt die SECURITY_AUTHENTICATED_USER_RID-SID zurück.

```
CSid AuthenticatedUser() throw(...);
```

##  <a name="backupops"></a>  SIDs::BackupOps

Gibt die DOMAIN_ALIAS_RID_BACKUP_OPS-SID zurück.

```
CSid BackupOps() throw(...);
```

##  <a name="batch"></a>  SIDs::Batch

Gibt die SECURITY_BATCH_RID-SID zurück.

```
CSid Batch() throw(...);
```

##  <a name="creatorgroup"></a>  SIDs::CreatorGroup

Gibt die SECURITY_CREATOR_GROUP_RID-SID zurück.

```
CSid CreatorGroup() throw(...);
```

##  <a name="creatorgroupserver"></a>  SIDs::CreatorGroupServer

Gibt die SECURITY_CREATOR_GROUP_SERVER_RID-SID zurück.

```
CSid CreatorGroupServer() throw(...);
```

##  <a name="creatorowner"></a>  SIDs::CreatorOwner

Gibt die SECURITY_CREATOR_OWNER_RID-SID zurück.

```
CSid CreatorOwner() throw(...);
```

##  <a name="creatorownerserver"></a>  SIDs::CreatorOwnerServer

Gibt die SECURITY_CREATOR_OWNER_SERVER_RID-SID zurück.

```
CSid CreatorOwnerServer() throw(...);
```

##  <a name="dialup"></a>  SIDs::Dialup

Gibt die SECURITY_DIALUP_RID-SID zurück.

```
CSid Dialup() throw(...);
```

##  <a name="guests"></a>  SIDs::Guests

Gibt die DOMAIN_ALIAS_RID_GUESTS-SID zurück.

```
CSid Guests() throw(...);
```

##  <a name="interactive"></a>  SIDs::Interactive

Gibt die SECURITY_INTERACTIVE_RID-SID zurück.

```
CSid Interactive() throw(...);
```

##  <a name="local"></a>  Sids::Local

Gibt die SECURITY_LOCAL_RID-SID zurück.

```
CSid Local() throw(...);
```

##  <a name="network"></a>  SIDs::Network

Gibt die SECURITY_NETWORK_RID-SID zurück.

```
CSid Network() throw(...);
```

##  <a name="networkservice"></a>  SIDs::NetworkService

Gibt die SECURITY_NETWORK_SERVICE_RID-SID zurück.

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>Hinweise

Verwenden Sie "NetworkService", um der Benutzer NT AUTHORITY\NetworkService ein Sicherheitsobjekt CPerfMon lesen kann. NetworkService hinzugefügt ATLServer Code, der DLL, die Anmeldung unter dem Netzwerkdienstkonto auf Windows XP Home Edition, Windows XP Professional, Windows Server 2003 und höher Betriebssystem ermöglichen, wird eine SecurityAttribute.

Wenn Indikatoren des benutzerdefinierten Protokolls mit ATLServer CPerfMon-Klasse in der Perfmon-MMC erstellt werden, möglicherweise die Indikatoren nicht angezeigt, wenn die Protokolldatei anzeigen, obwohl sie ordnungsgemäß in der Ansicht in Echtzeit angezeigt werden. Benutzerdefinierte Leistungsindikatoren CPerfMon nicht die erforderlichen Berechtigungen für den Dienst "Performance-Protokolle und Warnungen" (smlogsvc.exe) auf unter Windows XP Home Edition, Windows XP Professional, Windows Server 2003 (oder höher)-Betriebssystemen ausgeführt werden müssen. Dieser Dienst wird ausgeführt, unter dem Konto "NT AUTHORITY\NetworkService".

##  <a name="null"></a>  SIDs::NULL

Gibt die SECURITY_NULL_RID-SID zurück.

```
CSid Null() throw(...);
```

##  <a name="prew2kaccess"></a>  Sids::PreW2KAccess

Gibt die DOMAIN_ALIAS_RID_PREW2KCOMPACCESS-SID zurück.

```
CSid PreW2KAccess() throw(...);
```

##  <a name="powerusers"></a>  SIDs::PowerUsers

Gibt die DOMAIN_ALIAS_RID_POWER_USERS-SID zurück.

```
CSid PowerUsers() throw(...);
```

##  <a name="printops"></a>  Sids::PrintOps

Gibt die DOMAIN_ALIAS_RID_PRINT_OPS-SID zurück.

```
CSid PrintOps() throw(...);
```

##  <a name="proxy"></a>  SIDs::Proxy

Gibt die SECURITY_PROXY_RID-SID zurück.

```
CSid Proxy() throw(...);
```

##  <a name="rasservers"></a>  SIDs::RasServers

Gibt die DOMAIN_ALIAS_RID_RAS_SERVERS-SID zurück.

```
CSid RasServers() throw(...);
```

##  <a name="replicator"></a>  SIDs::Replicator

Gibt die DOMAIN_ALIAS_RID_REPLICATOR-SID zurück.

```
CSid Replicator() throw(...);
```

##  <a name="restrictedcode"></a>  SIDs::RestrictedCode

Gibt die SECURITY_RESTRICTED_CODE_RID-SID zurück.

```
CSid RestrictedCode() throw(...);
```

##  <a name="self"></a>  SIDs::Self

Gibt die SECURITY_PRINCIPAL_SELF_RID-SID zurück.

```
CSid Self() throw(...);
```

##  <a name="serverlogon"></a>  SIDs::ServerLogon

Gibt die SECURITY_SERVER_LOGON_RID-SID zurück.

```
CSid ServerLogon() throw(...);
```

##  <a name="service"></a>  SIDs::Service

Gibt die SECURITY_SERVICE_RID-SID zurück.

```
CSid Service() throw(...);
```

##  <a name="system"></a>  SIDs::System

Gibt die SECURITY_LOCAL_SYSTEM_RID-SID zurück.

```
CSid System() throw(...);
```

##  <a name="systemops"></a>  SIDs::SystemOps

Gibt die DOMAIN_ALIAS_RID_SYSTEM_OPS-SID zurück.

```
CSid SystemOps() throw(...);
```

##  <a name="terminalserver"></a>  SIDs::Terminalserver

Gibt die SECURITY_TERMINAL_SERVER_RID-SID zurück.

```
CSid TerminalServer() throw(...);
```

##  <a name="users"></a>  SIDs::Users

Gibt die DOMAIN_ALIAS_RID_USERS-SID zurück.

```
CSid Users() throw(...);
```

##  <a name="world"></a>  Sids::World

Gibt die SECURITY_WORLD_RID-SID zurück.

```
CSid World() throw(...);
```

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)
