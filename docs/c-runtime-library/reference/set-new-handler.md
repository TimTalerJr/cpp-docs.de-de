---
title: _set_new_handler
ms.date: 11/04/2016
api_name:
- _set_new_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_new_handler
- set_new_handler
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
ms.openlocfilehash: a1f340887efd657dd9ff9bf219534d77fdd90aa3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948468"
---
# <a name="_set_new_handler"></a>_set_new_handler

Übergibt die Steuerung an den Fehlerbehandlungsmechanismus, wenn der **new**-Operator keine Speicherbelegung vornehmen kann.

## <a name="syntax"></a>Syntax

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>Parameter

*pNewHandler*<br/>
Zeiger zu der von der Anwendung bereitgestellten Speicherbehandlungsfunktion. Ist das Argument 0, wird der neue Ereignishandler entfernt.

## <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die vorherige Ausnahme Behandlungs Funktion zurück, die von **_set_new_handler**registriert wurde, sodass die vorherige Funktion später wieder hergestellt werden kann. Wenn keine vorherige Funktion festgelegt wurde, kann der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen. Dieser Wert kann **null**sein.

## <a name="remarks"></a>Hinweise

Die C++ **_set_new_handler** -Funktion gibt eine Ausnahme Behandlungs Funktion an, die die Steuerung erhält, wenn der **neue** Operator keinen Arbeitsspeicher zuordnen kann. Schlägt **New** fehl, ruft das Laufzeitsystem automatisch die Ausnahme Behandlungs Funktion auf, die als Argument an **_set_new_handler**übermittelt wurde. **_PNH**, definiert in New. h, ist ein Zeiger auf eine Funktion, die den Typ " **int** " zurückgibt und ein Argument vom Typ " **size_t**" annimmt. Verwenden Sie **size_t** , um den Speicherplatz anzugeben, der zugewiesen werden soll.

Es ist kein Standardhandler vorhanden.

bei **_set_new_handler** handelt es sich im Wesentlichen um ein Garbage Collection-Schema. Das Laufzeitsystem wiederholt die Zuordnung jedes Mal, wenn die Funktion einen Wert ungleich null zurückgibt, und schlägt fehl, wenn die Funktion 0 zurückgibt.

Ein Vorkommen der **_set_new_handler** -Funktion in einem Programm registriert die in der Argumentliste angegebene Ausnahme Behandlungs Funktion mit dem Laufzeitsystem:

```cpp
// set_new_handler1.cpp
#include <new.h>

int handle_program_memory_depletion( size_t )
{
   // Your code
}

int main( void )
{
   _set_new_handler( handle_program_memory_depletion );
   int *pi = new int[BIG_NUMBER];
}
```

Sie können die Funktions Adresse speichern, die zuletzt an die **_set_new_handler** -Funktion weitergegeben wurde, und Sie später wieder aktivieren:

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

Die C++-Funktion [_set_new_mode](set-new-mode.md) legt den neuen Handlermodus für [malloc](malloc.md) fest. Der neue handlermodus gibt an, ob **malloc** bei einem Fehler die neue Handlerroutine aufrufen soll, wie von **_set_new_handler**festgelegt. Standardmäßig ruft **malloc** die neue Handlerroutine nicht bei einem Fehler auf, um Arbeitsspeicher zuzuweisen. Sie können dieses Standardverhalten außer Kraft setzen, sodass, wenn **malloc** keinen Arbeitsspeicher zuordnen kann, die neue Handlerroutine von **malloc** auf die gleiche Weise aufgerufen wird wie der **neue** Operator, wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie

```cpp
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit Newmode.obj her.

Wenn ein benutzerdefinierter `operator new` bereitgestellt wird, werden die neuen Handlerfunktionen bei einem Fehler nicht automatisch aufgerufen.

Weitere Informationen finden Sie unter [new](../../cpp/new-operator-cpp.md) und [delete](../../cpp/delete-operator-cpp.md) in der *C++-Sprachreferenz*.

Es gibt einen einzelnen **_set_new_handler** -Handler für alle dynamisch verknüpften DLLs oder ausführbaren Dateien. auch wenn Sie **_set_new_handler** anrufen, wird der Handler möglicherweise durch einen anderen ersetzt, oder Sie ersetzen einen Handler, der von einer anderen DLL oder ausführbaren Datei festgelegt wurde.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Wenn – wie in diesem Beispiel – die Zuordnung fehlschlägt, wird die Steuerung an MyNewHandler übergeben. Das an MyNewHandler übergebene Argument ist die Anzahl der angeforderten Bytes. Der von MyNewHandler zurückgegebene Wert ist ein Flag, das angibt, ob die Zuordnung wiederholt werden soll: Ein Wert ungleich null gibt an, dass die Zuordnung wiederholt werden soll, und der Wert 0 gibt an, dass die Verteilung fehlgeschlagen ist.

```cpp
// crt_set_new_handler.cpp
// compile with: /c
#include <stdio.h>
#include <new.h>
#define BIG_NUMBER 0x1fffffff

int coalesced = 0;

int CoalesceHeap()
{
   coalesced = 1;  // Flag RecurseAlloc to stop
   // do some work to free memory
   return 0;
}
// Define a function to be called if new fails to allocate memory.
int MyNewHandler( size_t size )
{
   printf("Allocation failed. Coalescing heap.\n");

   // Call a function to recover some heap space.
   return CoalesceHeap();
}

int RecurseAlloc() {
   int *pi = new int[BIG_NUMBER];
   if (!coalesced)
      RecurseAlloc();
   return 0;
}

int main()
{
   // Set the failure handler for new to be MyNewHandler.
   _set_new_handler( MyNewHandler );
   RecurseAlloc();
}
```

```Output
Allocation failed. Coalescing heap.

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
