---
title: isblank, iswblank, _isblank_l, _iswblank_l
ms.date: 11/04/2016
api_name:
- isblank
- _isblank_l
- iswblank
- _iswblank_l
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _iswblank_l
- isblank
- _istblank_l
- _istblank
- _isblank_l
- iswblank
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
ms.openlocfilehash: 022eba0335facc597f0608d63cfb58e0146e0f23
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954518"
---
# <a name="isblank-iswblank-_isblank_l-_iswblank_l"></a>isblank, iswblank, _isblank_l, _iswblank_l

Bestimmt, ob eine ganze Zahl ein Leerzeichen darstellt.

## <a name="syntax"></a>Syntax

```C
int isblank(
   int c
);
int iswblank(
   wint_t c
);
int _isblank_l(
   int c,
   _locale_t locale
);
int _iswblank_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu testende ganze Zahl.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt einen Wert ungleich 0 (null) zurück, wenn *c* eine bestimmte Darstellung eines leer Zeichens oder eines horizontalen Tabstopp Zeichens ist oder einer der Gebiets Schema spezifischen Zeichen ist, die zum Trennen von Wörtern in einer Textzeile verwendet werden. **isblank** gibt einen Wert ungleich 0 (null) zurück, wenn *c* ein Leerzeichen (0x20) oder ein horizontales Tabstopp Zeichen (0x09) ist. Das Ergebnis der Test Bedingung für die **isblank** -Funktionen hängt von der **LC_CTYPE** -Kategorieeinstellung des Gebiets Schemas ab. Weitere Informationen finden Sie unter [setlocale, _wsetlocale](setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das **_l** -Suffix verwenden das aktuelle Gebiets Schema für jedes vom Gebiets Schema abhängige Verhalten. die Versionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch stattdessen das übergebene Gebiets Schema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

**iswblank** gibt einen Wert ungleich 0 (null) zurück, wenn *c* ein breit Zeichen ist, das einem Standard-oder einem horizontalen Tabstopp Zeichen entspricht.

Das Verhalten von " **isblank** " und " **_isblank_l** " ist nicht definiert, wenn *c* nicht EOF ist oder im Bereich von 0 bis 0xFF (einschließlich) liegt. Wenn eine Debug-CRT-Bibliothek verwendet wird und *c* keiner dieser Werte ist, wird von den Funktionen eine-Assertion erhoben.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istblank**|**isblank**|[_ismbcblank](ismbcgraph-functions.md)|**iswblank**|
|**_istblank_l**|**_isblank_l**|[_ismbcblank_l](ismbcgraph-functions.md)|**_iswblank_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**isblank**|\<ctype.h>|
|**iswblank**|\<ctype.h> oder \<wchar.h>|
|**_isblank_l**|\<ctype.h>|
|**_iswblank_l**|\<ctype.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Zeichenklassifizierung](../../c-runtime-library/character-classification.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)<br/>
