---
title: ___lc_collate_cp_func
ms.date: 11/04/2016
api_name:
- ___lc_collate_cp_func
api_location:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ___lc_collate_cp_func
helpviewer_keywords:
- ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
ms.openlocfilehash: d6a857760bf3b76481cc608ef8f015bca207f35f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940157"
---
# <a name="___lc_collate_cp_func"></a>___lc_collate_cp_func

Interne CRT-Funktion. Ruft die aktuelle Sortierungscodeseite des Threads ab.

## <a name="syntax"></a>Syntax

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Rückgabewert

Die aktuelle Sortierungscodeseite des Threads.

## <a name="remarks"></a>Anmerkungen

`___lc_collate_cp_func` ist eine interne CRT-Funktion, die von anderen CRT-Funktionen verwendet wird, um die aktuelle Sortierungscodeseite aus dem lokalen Threadspeicher für CRT-Daten abzurufen. Diese Information kann auch durch Verwendung der [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)-Funktion gewonnen werden.

Interne CRT-Funktionen sind implementierungsspezifisch und mit jedem neuen Release Änderungen unterworfen. Ihre Verwendung in einem Code wird nicht empfohlen.

## <a name="requirements"></a>Requirements (Anforderungen)

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`___lc_collate_cp_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Siehe auch

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
