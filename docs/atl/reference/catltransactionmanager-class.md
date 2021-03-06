---
title: Klasse von "-Klasse"
ms.date: 11/04/2016
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
ms.openlocfilehash: d72867eaa449a20e676d4eddc4c94c02090334e5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497717"
---
# <a name="catltransactionmanager-class"></a>Klasse von "-Klasse"

Die Klasse "Klasse-Manager" stellt einen Wrapper für die Funktionen des Kerneltransaktions-Managers (KTM) bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CAtlTransactionManager;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[~CAtlTransactionManager](#dtor)|Der Initialisierer von "-Dekonstruktor".|
|[CAtlTransactionManager](#catltransactionmanager)|Der-Konstruktor "-Konstruktor".|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Schließen](#close)|Schließt einen Transaktions handle.|
|[Einzusetzen](#commit)|Fordert an, dass für die Transaktion ein Commit ausgeführt wird.|
|[Erstellen](#create)|Erstellt das Transaktions handle.|
|[CreateFile](#createfile)|Erstellt oder öffnet eine Datei, einen Dateistream oder ein Verzeichnis als transaktiven Vorgang.|
|[DeleteFile](#deletefile)|Löscht eine vorhandene Datei als transaktiven Vorgang.|
|[FindFirstFile](#findfirstfile)|Durchsucht ein Verzeichnis nach einer Datei oder einem Unterverzeichnis als transaktiver Vorgang.|
|[GetFileAttributes](#getfileattributes)|Ruft Dateisystem Attribute für eine angegebene Datei oder ein angegebenes Verzeichnis als transaktiven Vorgang ab.|
|[Getfileattributesex](#getfileattributesex)|Ruft Dateisystem Attribute für eine angegebene Datei oder ein angegebenes Verzeichnis als transaktiven Vorgang ab.|
|[GetHandle](#gethandle)|Gibt das Transaktions Handle zurück.|
|[IsFallback](#isfallback)|Bestimmt, ob die Fall Back Aufrufe aktiviert sind.|
|[MoveFile](#movefile)|Verschiebt eine vorhandene Datei oder ein Verzeichnis, einschließlich der untergeordneten Elemente, als transaktiven Vorgang.|
|[RegCreateKeyEx](#regcreatekeyex)|Erstellt den angegebenen Registrierungsschlüssel und ordnet ihn einer Transaktion zu. Wenn der Schlüssel bereits vorhanden ist, wird er von der Funktion geöffnet.|
|[RegDeleteKey](#regdeletekey)|Löscht einen Unterschlüssel und seine Werte aus der angegebenen plattformspezifischen Sicht der Registrierung als transaktiven Vorgang.|
|[RegOpenKeyEx](#regopenkeyex)|Öffnet den angegebenen Registrierungsschlüssel und ordnet ihn einer Transaktion zu.|
|[Rollback](#rollback)|Fordert an, dass ein Rollback der Transaktion ausgeführt wird.|
|[Setfileattribute](#setfileattributes)|Legt die Attribute für eine Datei oder ein Verzeichnis als transaktiven Vorgang fest.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|TRUE, wenn der Fall Back unterstützt wird. Andernfalls false.|
|[m_hTransaction](#m_htransaction)|Das Transaktions handle.|

## <a name="remarks"></a>Hinweise

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** atltransaktionmanager. h

##  <a name="dtor"></a>~-"~-Transaktionmanager"

Der Initialisierer von "-Dekonstruktor".

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Hinweise

Bei normaler Verarbeitung wird die Transaktion automatisch committet und geschlossen. Wenn der Dekonstruktor während einer Ausnahme entladen wird, wird ein Rollback für die Transaktion ausgeführt und geschlossen.

##  <a name="catltransactionmanager"></a>CAtlTransactionManager

Der-Konstruktor "-Konstruktor".

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>Parameter

*bFallback*<br/>
TRUE gibt den Supportfall Back an. Wenn die transaktive Funktion fehlschlägt, ruft die Klasse automatisch die nicht transaktive Funktion auf. FALSE gibt an, dass keine Fallback-Aufrufe aufgerufen werden.

*bAutoCreateTransaction*<br/>
TRUE gibt an, dass der Transaktions Handler automatisch im Konstruktor erstellt wird. FALSE gibt an, dass dies nicht der Fall ist.

### <a name="remarks"></a>Hinweise

##  <a name="close"></a>Ihrer

Schließt das Transaktions handle.

```
inline BOOL Close();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `CloseHandle` -Funktion auf. Die-Methode wird automatisch im Dekonstruktor aufgerufen.

##  <a name="commit"></a>Einzusetzen

Fordert an, dass für die Transaktion ein Commit ausgeführt wird.

```
inline BOOL Commit();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `CommitTransaction` -Funktion auf. Die-Methode wird automatisch im Dekonstruktor aufgerufen.

##  <a name="create"></a>Stelle

Erstellt das Transaktions handle.

```
inline BOOL Create();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `CreateTransaction` -Funktion auf. Überprüfen Sie dies

##  <a name="createfile"></a>CreateFile

Erstellt oder öffnet eine Datei, einen Dateistream oder ein Verzeichnis als transaktiven Vorgang.

```
inline HANDLE CreateFile(
    LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name des zu erstellenden oder zu öffnenden Objekts.

*dwDesiredAccess*<br/>
Der Zugriff auf das-Objekt, das als lesen, schreiben, beides oder keines von beiden (null) zusammengefasst werden kann. Die am häufigsten verwendeten Werte sind GENERIC_READ, GENERIC_WRITE oder beides: GENERIC_READ &#124; GENERIC_WRITE.

*dwShareMode*<br/>
Der Freigabe Modus eines Objekts, das Lesen, schreiben, beides, löschen, alle oder keine: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.

*lpSecurityAttributes*<br/>
Ein Zeiger auf eine SECURITY_ATTRIBUTES-Struktur, die einen optionalen Sicherheits Deskriptor enthält und auch bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Der-Parameter kann NULL sein.

*dwCreationDisposition*<br/>
Eine Aktion, die für Dateien ausgeführt werden soll, die vorhanden sind und nicht vorhanden sind. Dieser Parameter muss einer der folgenden Werte sein, die nicht kombiniert werden können: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING oder TRUNCATE_EXISTING.

*dwFlagsAndAttributes*<br/>
Die Dateiattribute und-Flags. Dieser Parameter kann eine beliebige Kombination der verfügbaren Dateiattribute (FILE_ATTRIBUTE_ *) enthalten. Alle anderen Dateiattribute überschreiben FILE_ATTRIBUTE_NORMAL. Dieser Parameter kann auch Kombinationen von Flags (FILE_FLAG_\*) enthalten, um das Puffer Verhalten, Zugriffs Modi und andere Flags für bestimmte Zwecke zu steuern. Diese kombinieren sich mit\* allen FILE_ATTRIBUTE_-Werten.

*hTemplateFile*<br/>
Ein gültiges Handle für eine Vorlagen Datei mit dem GENERIC_READ-Zugriffsrecht. Die Vorlagen Datei liefert Dateiattribute und erweiterte Attribute für die Datei, die erstellt wird. Dieser Parameter kann NULL sein.

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle zurück, das für den Zugriff auf das-Objekt verwendet werden kann.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `CreateFileTransacted` -Funktion auf.

##  <a name="deletefile"></a>DeleteFile

Löscht eine vorhandene Datei als transaktiven Vorgang.

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name der zu löschenden Datei.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `DeleteFileTransacted` -Funktion auf.

##  <a name="findfirstfile"></a>FindFirstFile

Durchsucht ein Verzeichnis nach einer Datei oder einem Unterverzeichnis als transaktiver Vorgang.

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Das Verzeichnis oder der Pfad und der Dateiname, nach dem gesucht werden soll. Dieser Parameter kann Platzhalter Zeichen enthalten, z. b. ein Sternchen (*) oder ein Fragezeichen ().

*pNextInfo*<br/>
Ein Zeiger auf die WIN32_FIND_DATA-Struktur, die Informationen zu einer gefundenen Datei oder einem Unterverzeichnis empfängt.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ein Such handle, das in einem `FindNextFile` nachfolg `FindClose`enden Rückruf von oder verwendet wird. Wenn die Funktion fehlerhaft ist oder Dateien aus der Such Zeichenfolge im *lpFileName* -Parameter nicht finden kann, ist der Rückgabewert INVALID_HANDLE_VALUE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `FindFirstFileTransacted` -Funktion auf.

##  <a name="getfileattributes"></a>GetFileAttributes

Ruft Dateisystem Attribute für eine angegebene Datei oder ein angegebenes Verzeichnis als transaktiven Vorgang ab.

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name der Datei oder des Verzeichnisses.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `GetFileAttributesTransacted` -Funktion auf.

##  <a name="getfileattributesex"></a>Getfileattributesex

Ruft Dateisystem Attribute für eine angegebene Datei oder ein angegebenes Verzeichnis als transaktiven Vorgang ab.

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name der Datei oder des Verzeichnisses.

*fInfoLevelId*<br/>
Die Ebene der abzurufenden Attributinformationen.

*lpFileInformation*<br/>
Ein Zeiger auf einen Puffer, der die Attributinformationen empfängt. Der Typ der Attributinformationen, die in diesem Puffer gespeichert werden, wird durch den Wert von *finfolevelid*bestimmt. Wenn der *finfolevelid* -Parameter getfileexinfostandard ist, verweist dieser Parameter auf eine WIN32_FILE_ATTRIBUTE_DATA-Struktur.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `GetFileAttributesTransacted` -Funktion auf.

##  <a name="gethandle"></a>GetHandle

Gibt das Transaktions Handle zurück.

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Transaktions Handle für eine-Klasse zurück. Gibt NULL zurück, `CAtlTransactionManager` wenn das nicht an ein Handle angefügt ist.

### <a name="remarks"></a>Hinweise

##  <a name="isfallback"></a>Isfallback

Bestimmt, ob die Fall Back Aufrufe aktiviert sind.

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Klasse Fall Back Aufrufe unterstützt. Andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="m_bfallback"></a>m_bFallback

TRUE, wenn der Fall Back unterstützt wird. Andernfalls false.

```
BOOL m_bFallback;
```

### <a name="remarks"></a>Hinweise

##  <a name="m_htransaction"></a>m_hTransaction

Das Transaktions handle.

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Hinweise

##  <a name="movefile"></a>MoveFile

Verschiebt eine vorhandene Datei oder ein Verzeichnis, einschließlich der untergeordneten Elemente, als transaktiven Vorgang.

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>Parameter

*lpOldFileName*<br/>
Der aktuelle Name der vorhandenen Datei oder des vorhandenen Verzeichnisses auf dem lokalen Computer.

*lpNewFileName*<br/>
Der neue Name für die Datei oder das Verzeichnis. Dieser Name darf nicht bereits vorhanden sein. Eine neue Datei kann sich auf einem anderen Dateisystem oder Laufwerk befinden. Ein neues Verzeichnis muss sich auf demselben Laufwerk befinden.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `MoveFileTransacted` -Funktion auf.

##  <a name="regcreatekeyex"></a>Regkreatekeyex

Erstellt den angegebenen Registrierungsschlüssel und ordnet ihn einer Transaktion zu. Wenn der Schlüssel bereits vorhanden ist, wird er von der Funktion geöffnet.

```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Ein Handle für einen geöffneten Registrierungsschlüssel.

*lpSubKey*<br/>
Der Name eines unter Schlüssels, der von dieser Funktion geöffnet oder erstellt wird.

*dwReserved*<br/>
Dieser Parameter ist reserviert und muss NULL sein.

*lpClass*<br/>
Die benutzerdefinierte Klasse dieses Schlüssels. Dieser Parameter kann ignoriert werden. Dieser Parameter kann NULL sein.

*dwOptions*<br/>
Dieser Parameter kann einen der folgenden Werte aufweisen: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE oder REG_OPTION_VOLATILE.

*samDesired*<br/>
Eine Maske, die die Zugriffsrechte für den Schlüssel angibt.

*lpSecurityAttributes*<br/>
Zeiger auf eine SECURITY_ATTRIBUTES-Struktur, die bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Wenn *lpsecurityattribute* NULL ist, kann das Handle nicht geerbt werden.

*phkResult*<br/>
Ein Zeiger auf eine Variable, die ein Handle für den geöffneten oder erstellten Schlüssel empfängt. Wenn es sich bei dem Schlüssel nicht um einen der vordefinierten Registrierungsschlüssel handelt `RegCloseKey` , müssen Sie die Funktion nach Abschluss der Verwendung des Handles aufzurufen.

*lpdwDisposition*<br/>
Ein Zeiger auf eine Variable, die einen der folgenden Dispositions Werte empfängt: REG_CREATED_NEW_KEY oder REG_OPENED_EXISTING_KEY.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WinError. h definiert ist.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `RegCreateKeyTransacted` -Funktion auf.

##  <a name="regdeletekey"></a>Regdeletekey

Löscht einen Unterschlüssel und seine Werte aus der angegebenen plattformspezifischen Sicht der Registrierung als transaktiven Vorgang.

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*hKey*|Ein Handle für einen geöffneten Registrierungsschlüssel.|
|*lpSubKey*|Der Name des zu löschenden Schlüssels.|

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WinError. h definiert ist.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `RegDeleteKeyTransacted` -Funktion auf.

##  <a name="regopenkeyex"></a>Fehler bei RegOpenKeyEx

Öffnet den angegebenen Registrierungsschlüssel und ordnet ihn einer Transaktion zu.

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Ein Handle für einen geöffneten Registrierungsschlüssel.

*lpSubKey*<br/>
Der Name des Registrierungs unter Schlüssels, der geöffnet werden soll.

*ulOptions*<br/>
Dieser Parameter ist reserviert und muss NULL sein.

*samDesired*<br/>
Eine Maske, die die Zugriffsrechte für den Schlüssel angibt.

*phkResult*<br/>
Ein Zeiger auf eine Variable, die ein Handle für den geöffneten oder erstellten Schlüssel empfängt. Wenn es sich bei dem Schlüssel nicht um einen der vordefinierten Registrierungsschlüssel handelt `RegCloseKey` , müssen Sie die Funktion nach Abschluss der Verwendung des Handles aufzurufen.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WinError. h definiert ist.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `RegOpenKeyTransacted` -Funktion auf.

##  <a name="rollback"></a>Rollback

Fordert an, dass ein Rollback der Transaktion ausgeführt wird.

```
inline BOOL Rollback();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `RollbackTransaction` -Funktion auf.

##  <a name="setfileattributes"></a>Setfileattribute

Legt die Attribute für eine Datei oder ein Verzeichnis als transaktiven Vorgang fest.

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name der Datei oder des Verzeichnisses.

*dwAttributes*<br/>
Die Dateiattribute, die für die Datei festgelegt werden sollen. Weitere Informationen finden Sie unter [setfileattributestranshandelten](/windows/win32/api/winbase/nf-winbase-setfileattributestransactedw).

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `SetFileAttributesTransacted` -Funktion auf.

## <a name="see-also"></a>Siehe auch

[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)
