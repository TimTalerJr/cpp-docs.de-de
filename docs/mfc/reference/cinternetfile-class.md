---
title: CInternetFile-Klasse
ms.date: 11/04/2016
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
ms.openlocfilehash: 68a0a0f35d1a1f4519401080f9f207bf76c87079
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424332"
---
# <a name="cinternetfile-class"></a>CInternetFile-Klasse

Ermöglicht den Zugriff auf Dateien auf Remote Systemen, die Internet Protokolle verwenden.

## <a name="syntax"></a>Syntax

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetFile:: CInternetFile](#cinternetfile)|Erstellt ein `CInternetFile`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CInternetFile:: Abort](#abort)|Schließt die Datei, wobei alle Warnungen und Fehler ignoriert werden.|
|[CInternetFile:: Close](#close)|Schließt einen `CInternetFile` und gibt seine Ressourcen frei.|
|[CInternetFile:: Flush](#flush)|Leert den Inhalt des Schreib Puffers und stellt sicher, dass die Daten im Arbeitsspeicher auf den Zielcomputer geschrieben werden.|
|[CInternetFile:: GetLength](#getlength)|Gibt die Größe der Datei zurück.|
|[CInternetFile:: Read](#read)|Liest die Anzahl der angegebenen Bytes.|
|[CInternetFile:: infoString](#readstring)|Liest einen Datenstrom von Zeichen.|
|[CInternetFile:: Seek](#seek)|Positioniert den Zeiger in einer geöffneten Datei.|
|[CInternetFile:: settreadbuffersize](#setreadbuffersize)|Legt die Größe des Puffers fest, in dem die Daten gelesen werden.|
|[CInternetFile:: setschreitebuffersize](#setwritebuffersize)|Legt die Größe des Puffers fest, in den Daten geschrieben werden.|
|[CInternetFile:: Write](#write)|Schreibt die Anzahl der angegebenen Bytes.|
|[CInternetFile:: Write String](#writestring)|Schreibt eine NULL-terminierte Zeichenfolge in eine Datei.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetFile:: Operator HINTERNET](#operator_hinternet)|Ein Umwandlungs Operator für ein Internet handle.|

### <a name="protected-data-members"></a>Geschützte Datenelemente

|Name|Beschreibung|
|----------|-----------------|
|[CInternetFile:: m_hFile](#m_hfile)|Ein Handle für eine Datei.|

## <a name="remarks"></a>Hinweise

Stellt eine Basisklasse für die Klassen " [CHttpFile](../../mfc/reference/chttpfile-class.md) " und " [CGopherFile](../../mfc/reference/cgopherfile-class.md) " bereit. Sie erstellen niemals direkt ein `CInternetFile` Objekt. Erstellen Sie stattdessen ein Objekt einer der abgeleiteten Klassen, indem Sie [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) oder [CHttpConnection:: openrequest](../../mfc/reference/chttpconnection-class.md#openrequest)aufrufen. Sie können auch ein `CInternetFile` Objekt erstellen, indem Sie [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)aufrufen.

Die `CInternetFile` Member-Funktionen `Open`, `LockRange`, `UnlockRange`und `Duplicate` sind nicht für `CInternetFile`implementiert. Wenn Sie diese Funktionen für ein `CInternetFile` Objekt aufzurufen, wird eine [cnotsupportedexception-Ausnahme](../../mfc/reference/cnotsupportedexception-class.md)angezeigt.

Weitere Informationen zur Funktionsweise von `CInternetFile` mit den anderen MFC-Internet Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>Voraussetzungen

**Header:** AFXINET. h

##  <a name="abort"></a>CInternetFile:: Abort

Schließt die Datei, die diesem-Objekt zugeordnet ist, und macht die Datei zum Lesen oder schreiben nicht verfügbar.

```
virtual void Abort();
```

### <a name="remarks"></a>Hinweise

Wenn Sie die Datei nicht geschlossen haben, bevor Sie das Objekt zerstören, wird Sie vom Dekonstruktor für Sie geschlossen.

Bei der Behandlung von Ausnahmen unterscheidet sich `Abort` in zwei wichtigen Punkten von [Close](#close) . Zuerst löst die `Abort`-Funktion bei Fehlern keine Ausnahme aus, da Sie Fehler ignoriert. Zweitens wird `Abort` nicht bestätigt **, wenn die** Datei nicht geöffnet oder zuvor geschlossen wurde.

##  <a name="cinternetfile"></a>CInternetFile:: CInternetFile

Diese Member-Funktion wird aufgerufen, wenn ein `CInternetFile` Objekt erstellt wird.

```
CInternetFile(
    HINTERNET hFile,
    LPCTSTR pstrFileName,
    CInternetConnection* pConnection,
    BOOL bReadMode);

CInternetFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrFileName,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext,
    BOOL bReadMode);
```

### <a name="parameters"></a>Parameter

*hFile*<br/>
Ein Handle für eine Internet Datei.

*pstrinfilename*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Dateinamen enthält.

*pConnection*<br/>
Ein Zeiger auf ein [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) -Objekt.

*Bread-Modus*<br/>
Gibt an, ob die Datei schreibgeschützt ist.

*hsession*<br/>
Ein Handle für eine Internet Sitzung.

*pstrinserver*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Servers enthält.

*dwcontext*<br/>
Der Kontext Bezeichner für das `CInternetFile` Objekt. Weitere Informationen zum Kontext Bezeichner finden Sie unter [WinInet-Grundlagen](../../mfc/wininet-basics.md) .

### <a name="remarks"></a>Hinweise

Sie erstellen niemals direkt ein `CInternetFile` Objekt. Erstellen Sie stattdessen ein Objekt einer der abgeleiteten Klassen, indem Sie [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) oder [CHttpConnection:: openrequest](../../mfc/reference/chttpconnection-class.md#openrequest)aufrufen. Sie können auch ein `CInternetFile` Objekt erstellen, indem Sie [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)aufrufen.

##  <a name="close"></a>CInternetFile:: Close

Schließt einen `CInternetFile` und gibt seine Ressourcen frei.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Wenn die Datei zum Schreiben geöffnet wurde, gibt es einen impliziten Löschvorgang [, um sicherzustellen,](#flush) dass alle gepufferten Daten auf den Host geschrieben werden. Wenn Sie mit der Verwendung einer Datei fertig sind, sollten Sie `Close` anrufen.

##  <a name="flush"></a>CInternetFile:: Flush

Mit dieser Member-Funktion können Sie den Inhalt des Schreib Puffers leeren.

```
virtual void Flush();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie `Flush`, um sicherzustellen, dass alle Daten im Arbeitsspeicher tatsächlich auf den Zielcomputer geschrieben wurden, und um sicherzustellen, dass die Transaktion mit dem Host Computer abgeschlossen wurde. `Flush` ist nur für `CInternetFile` Objekte wirksam, die zum Schreiben geöffnet sind.

##  <a name="getlength"></a>CInternetFile:: GetLength

Gibt die Größe der Datei zurück.

```
virtual ULONGLONG GetLength() const;
```

##  <a name="m_hfile"></a>CInternetFile:: m_hFile

Ein Handle für die Datei, die diesem-Objekt zugeordnet ist.

```
HINTERNET m_hFile;
```

##  <a name="operator_hinternet"></a>CInternetFile:: Operator HINTERNET

Verwenden Sie diesen Operator, um das Windows-Handle für die aktuelle Internet Sitzung zu erhalten.

```
operator HINTERNET() const;
```

##  <a name="read"></a>CInternetFile:: Read

Mit dieser Member-Funktion können Sie in den angegebenen Speicher, beginnend bei *lpvbuf*, mit der angegebenen Anzahl von Bytes, *nCount*, lesen.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parameter

*lpbuf*<br/>
Ein Zeiger auf eine Speicheradresse, auf der Dateidaten gelesen werden.

*nCount*<br/>
Die Anzahl der zu schreibenden Bytes.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der in den Puffer übertrageben Bytes. Der Rückgabewert kann kleiner als *nCount* sein, wenn das Ende der Datei erreicht wurde.

### <a name="remarks"></a>Hinweise

Die Funktion gibt die Anzahl der tatsächlich gelesenen Bytes zurück – eine Zahl, die kleiner als *nCount* sein kann, wenn die Datei endet. Wenn beim Lesen der Datei ein Fehler auftritt, löst die Funktion ein [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt aus, das den Fehler beschreibt. Beachten Sie, dass der Lesevorgang nach dem Ende der Datei nicht als Fehler angesehen und keine Ausnahme ausgelöst wird.

Um sicherzustellen, dass alle Daten abgerufen werden, muss eine Anwendung die `CInternetFile::Read`-Methode weiterhin aufzurufen, bis die Methode NULL zurückgibt.

##  <a name="readstring"></a>CInternetFile:: infoString

Mit dieser Member-Funktion können Sie einen Datenstrom lesen, bis ein Zeilen vorzeitiges Zeichen gefunden wird.

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>Parameter

*Pstr*<br/>
Ein Zeiger auf eine Zeichenfolge, die die gelesene Zeile empfängt.

*nMax*<br/>
Die maximale Anzahl der zu lesenden Zeichen.

*RString*<br/>
Ein Verweis auf das [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das die Lese Zeile empfängt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Puffer mit reinen Daten, die aus dem [CInternetFile](../../mfc/reference/cinternetfile-class.md) -Objekt abgerufen wurden. Ungeachtet des Datentyps des an diese Methode weiter gegebenen Puffers führt er keine Manipulationen an den Daten aus (z. b. bei der Konvertierung in Unicode). Daher müssen Sie die zurückgegebenen Daten der erwarteten Struktur zuordnen, so als ob der **void** - <strong>\*</strong> Typ zurückgegeben wurde.

NULL, wenn das Dateiende erreicht wurde, ohne dass Daten gelesen wurden. oder, wenn es sich um einen booleschen Wert handelt, false, wenn das Dateiende erreicht wurde, ohne Daten zu lesen.

### <a name="remarks"></a>Hinweise

Die-Funktion platziert die resultierende Zeile in den Speicher, auf den vom *Pstr* -Parameter verwiesen wird. Das Lesen von Zeichen wird beendet, wenn die maximale Anzahl von Zeichen erreicht wird, die durch *nmax*angegeben wird. Der Puffer empfängt immer ein abschließendes NULL-Zeichen.

Wenn Sie `ReadString` [aufrufen, ohne](#setreadbuffersize)zuerst "" "" "" "" "" "" "4096,"

##  <a name="seek"></a>CInternetFile:: Seek

Mit dieser Member-Funktion können Sie den Zeiger in einer zuvor geöffneten Datei neu positionieren.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>Parameter

*loffset*<br/>
Offset in Bytes zum Verschieben des Lese-/schreibzeigers in der Datei.

*nfrom*<br/>
Relativer Verweis für den Offset. Dies muss einer der folgenden Werte sein:

- `CFile::begin` verschieben Sie den Dateizeiger " *lOff* Bytes" vom Anfang der Datei.

- `CFile::current` den *Dateizeiger aus* der aktuellen Position in der Datei an die aktuelle Position verschieben.

- `CFile::end` verschieben Sie den Dateizeiger mit der Datei " *lOff* Bytes" vom Dateiende. bei der Suche in der vorhandenen Datei muss " *lOff* " negativ sein. positive Werte werden nach dem Ende der Datei gesucht.

### <a name="return-value"></a>Rückgabewert

Der neue Byte Offset vom Anfang der Datei, wenn die angeforderte Position gültig ist. Andernfalls ist der Wert nicht definiert, und es wird ein [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt ausgelöst.

### <a name="remarks"></a>Hinweise

Die `Seek`-Funktion ermöglicht den zufälligen Zugriff auf den Inhalt einer Datei, indem der Zeiger auf einen angegebenen Betrag (absolut oder relativ) verschoben wird. Während der Suche werden tatsächlich keine Daten gelesen.

Zu diesem Zeitpunkt wird ein Aufruf dieser Member-Funktion nur für Daten unterstützt, die `CHttpFile` Objekten zugeordnet sind. Sie wird für FTP-oder Gopher-Anforderungen nicht unterstützt. Wenn Sie `Seek` für einen dieser nicht unterstützten Dienste aufzurufen, werden Sie an den Win32-Fehlercode ERROR_INTERNET_INVALID_OPERATION zurückgegeben.

Wenn eine Datei geöffnet wird, befindet sich der Dateizeiger am Offset 0, dem Anfang der Datei.

> [!NOTE]
>  [Die Verwendung von `Seek`](#flush)kann einen impliziten-Aufrufvorgang verursachen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für die Basisklassen Implementierung ( [CFile:: Seek](../../mfc/reference/cfile-class.md#seek)).

##  <a name="setreadbuffersize"></a>CInternetFile:: settreadbuffersize

Mit dieser Member-Funktion können Sie die Größe des temporären Lese Puffers festlegen, der von einem `CInternetFile`-abgeleiteten Objekt verwendet wird.

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>Parameter

*nread size*<br/>
Die gewünschte Puffergröße in Bytes.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Die zugrunde liegenden WinInet-APIs führen keine Pufferung aus. Wählen Sie daher eine Puffergröße aus, die Ihrer Anwendung ermöglicht, Daten effizient zu lesen, unabhängig von der zu lesenden Datenmenge. Wenn jeder [Lese](#read) Vorgang in der Regel eine große Anzahl von Daten enthält (z. b. vier oder mehr Kilobytes), sollten Sie keinen Puffer benötigen. Wenn Sie jedoch `Read` zum Abrufen kleiner Datenblöcke oder zum Verwenden von "read [String](#readstring) " verwenden, um einzelne Zeilen gleichzeitig zu lesen, verbessert ein Lese Puffer die Anwendungsleistung.

Standardmäßig stellt ein `CInternetFile` Objekt keine Pufferung zum Lesen bereit. Wenn Sie diese Member-Funktion aufrufen, müssen Sie sicherstellen, dass die Datei für den Lesezugriff geöffnet wurde.

Sie können die Puffergröße jederzeit vergrößern, das Verkleinern des Puffers hat jedoch keine Auswirkungen. Wenn Sie "read [String](#readstring) " aufrufen, ohne zuerst `SetReadBufferSize`aufzurufen, erhalten Sie einen Puffer mit einer Größe von 4096 Bytes.

##  <a name="setwritebuffersize"></a>CInternetFile:: setschreitebuffersize

Mit dieser Member-Funktion können Sie die Größe des temporären Schreib Puffers festlegen, der von einem `CInternetFile`-abgeleiteten Objekt verwendet wird.

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>Parameter

*nschreibgröße*<br/>
Die Größe des Puffers in Byte.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Die zugrunde liegenden WinInet-APIs führen keine Pufferung aus. Wählen Sie daher eine Puffergröße aus, die Ihrer Anwendung ermöglicht, Daten unabhängig von der zu schreibenden Datenmenge effizient zu schreiben. Wenn jeder Aufruf zum [Schreiben](#write) in der Regel eine große Datenmenge (z. b. vier oder mehr Kilobyte) umfasst, sollten Sie keinen Puffer benötigen. Wenn Sie jedoch [schreiben schreiben](#write) , um kleine Datenblöcke zu schreiben, verbessert ein Schreibpuffer die Leistung Ihrer Anwendung.

Standardmäßig stellt ein `CInternetFile` Objekt keine Pufferung zum Schreiben bereit. Wenn Sie diese Member-Funktion aufrufen, müssen Sie sicherstellen, dass die Datei für den Schreibzugriff geöffnet wurde. Sie können die Größe des Schreib Puffers jederzeit ändern, aber dies bewirkt einen impliziten Aufruf von [Flush](#flush).

##  <a name="write"></a>CInternetFile:: Write

Mit dieser Member-Funktion können Sie in den angegebenen Speicher, *lpvbuf*, die angegebene Anzahl von Bytes, *nCount*, schreiben.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parameter

*lpbuf*<br/>
Ein Zeiger auf das erste zu schreibende Byte.

*nCount*<br/>
Gibt die Anzahl der zu schreibenden Bytes an.

### <a name="remarks"></a>Hinweise

Wenn beim Schreiben der Daten ein Fehler auftritt, löst die Funktion ein [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt aus, das den Fehler beschreibt.

##  <a name="writestring"></a>CInternetFile:: Write String

Diese Funktion schreibt eine NULL-terminierte Zeichenfolge in die zugeordnete Datei.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>Parameter

*Pstr*<br/>
Ein Zeiger auf eine Zeichenfolge, die den zu schreibenden Inhalt enthält.

### <a name="remarks"></a>Hinweise

Wenn beim Schreiben der Daten ein Fehler auftritt, löst die Funktion ein [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt aus, das den Fehler beschreibt.

## <a name="see-also"></a>Siehe auch

[CStdioFile-Klasse](../../mfc/reference/cstdiofile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)
