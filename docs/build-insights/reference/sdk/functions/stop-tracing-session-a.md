---
title: Stoptracingsessiona
description: Die C++ Funktionsreferenz für das Build Insights SDK stoptracingsessiona.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 12f0c7a9665c47f36fb5e88d799673918017bb98
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334193"
---
# <a name="stoptracingsessiona"></a>Stoptracingsessiona

::: moniker range="<=vs-2015"

Das C++ Build Insights SDK ist kompatibel mit Visual Studio 2017 und höher. Um die Dokumentation für diese Versionen anzuzeigen, legen Sie das Steuerelement für die Visual Studio-Versions Auswahl für diesen Artikel auf Visual Studio 2017 oder Visual Studio 2019 fest.

::: moniker-end
::: moniker range=">=vs-2017"

Die `StopTracingSessionA`-Funktion beendet eine laufende Ablauf Verfolgungs Sitzung und erstellt eine Rohdaten-Ablauf Verfolgungs Datei. Zum Starten einer Analyse Sitzung können unformatierte Ablauf Verfolgungs Dateien an die Funktionen " [analysieren](analyze.md)", " [analzea](analyze-a.md)" und " [analyzew](analyze-w.md) " übermittelt werden. Unformatierte Ablauf Verfolgungs Dateien können auch an die Funktionen [relog](relog.md), [reloga](relog-a.md)und [relogw](relog-w.md) weitergegeben werden, um die Sitzung erneut zu protokollieren. Ausführbare Dateien, die `StopTracingSessionA` aufrufen, müssen über Administratorrechte verfügen.

## <a name="syntax"></a>Syntax

```cpp
enum RESULT_CODE StopTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Parameter

*Sessionname* -\
Der Name der Ablauf Verfolgungs Sitzung, die angehalten werden soll. Verwenden Sie den gleichen Sitzungs Namen wie der, der an [starttracingsession](start-tracing-session.md), [starttracingsessiona](start-tracing-session-a.md)oder [starttracingsessionw](start-tracing-session-w.md)übergeben wird.

*outputlogfile* -\
Der Pfad zur endgültigen Ausgabeprotokoll Datei, in der die Rohdaten Ablauf Verfolgung gespeichert werden soll.

*Statistik*\
Zeiger auf ein [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) Objekt. `StopTracingSessionA` schreibt Statistiken der Ablauf Verfolgungs Sammlung in dieses Objekt, bevor Sie zurückgegeben wird

### <a name="return-value"></a>Rückgabewert

Ein Ergebniscode aus der [RESULT_CODE](../other-types/result-code-enum.md) -Aufzählung.

::: moniker-end
