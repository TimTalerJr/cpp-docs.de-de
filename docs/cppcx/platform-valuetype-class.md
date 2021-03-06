---
title: Platform::ValueType-Klasse
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: 889cf3a53468491517d37978ca09472756ad9b7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182950"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType-Klasse

Die Basisklasse für Instanzen von Werttypen.

## <a name="syntax"></a>Syntax

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|[ValueType::ToString](#tostring)|Gibt eine Zeichenfolgendarstellung des Objekts zurück. Geerbt von [Platform:: Object](../cppcx/platform-object-class.md).|

### <a name="remarks"></a>Hinweise

Die ValueType-Klasse wird zum Erstellen von Werttypen verwendet. „ValueType“ ist von „Object“ abgeleitet, die über Basismember verfügt. Der Compiler trennt jedoch diese Basismember von den Werttypen, die aus der ValueType-Klasse abgeleitet sind. Der Compiler fügt die Basismember wieder an, wenn ein Werttyp mittels Boxing konvertiert wird.

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Plattform

**Metadaten:** platform.winmd

## <a name="tostring"></a> ValueType:: ToString-Methode

Gibt eine Zeichenfolgendarstellung des Objekts zurück.

### <a name="syntax"></a>Syntax

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>Rückgabewert

Ein Platform:: String-Wert, der den Wert darstellt.

## <a name="see-also"></a>Siehe auch

[Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
