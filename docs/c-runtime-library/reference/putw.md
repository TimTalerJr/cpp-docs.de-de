---
title: _putw
ms.date: 11/04/2016
api_name:
- _putw
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _putw
helpviewer_keywords:
- integers, writing to streams
- putw function
- streams, writing integers to
- _putw function
ms.assetid: 83d63644-249d-4a39-87e5-3b7aa313968d
ms.openlocfilehash: be2ee5c1b3706b1f2a0847415ab4a82a6a4bbe4f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443723"
---
# <a name="_putw"></a>_putw

Schreibt eine ganze Zahl in einen Stream.

## <a name="syntax"></a>Syntax

```C
int _putw(
   int binint,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*binint*<br/>
Binäre Ganzzahl wird ausgegeben.

*stream*<br/>
Zeiger zur **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Gibt den geschriebenen Wert zurück. Der Rückgabewert von **EOF** weist möglicherweise auf einen Fehler hin. Da **EOF** auch ein legitimer ganzzahliger Wert ist, verwenden Sie **ferror** , um einen Fehler zu überprüfen. Wenn *Stream* ein NULL-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt diese Funktion **errno** auf **EINVAL** fest und gibt **EOF**zurück.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Bemerkungen

Die **_putw** -Funktion schreibt einen binären Wert vom Typ **int** an die aktuelle Position des *Streams.* **_putw** wirkt sich weder auf die Ausrichtung von Elementen im Stream noch auf eine besondere Ausrichtung aus. **_putw** ist hauptsächlich auf die Kompatibilität mit früheren Bibliotheken zurück. Möglicherweise treten bei der **_putw** Portabilitäts Probleme auf, da die Größe eines **int** -und die Reihenfolge der Bytes innerhalb eines **int** -Systems systemübergreifend abweichen.

## <a name="requirements"></a>Requirements (Anforderungen)

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_putw**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_putw.c
/* This program uses _putw to write a
* word to a stream, then performs an error check.
*/

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   unsigned u;
   if( fopen_s( &stream, "data.out", "wb" ) )
      exit( 1 );
   for( u = 0; u < 10; u++ )
   {
      _putw( u + 0x2132, stream );   /* Write word to stream. */
      if( ferror( stream ) )         /* Make error check. */
      {
         printf( "_putw failed" );
         clearerr_s( stream );
         exit( 1 );
      }
   }
   printf( "Wrote ten words\n" );
   fclose( stream );
}
```

### <a name="output"></a>Output

```Output
Wrote ten words
```

## <a name="see-also"></a>Weitere Informationen

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_getw](getw.md)<br/>
