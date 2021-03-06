---
title: int_2-Klasse
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::int_2::y
- amp_short_vectors/Concurrency::graphics::int_2::set_x
- amp_short_vectors/Concurrency::graphics::int_2::set_y
- amp_short_vectors/Concurrency::graphics::int_2::get_yx
- amp_short_vectors/Concurrency::graphics::int_2::operator++
- amp_short_vectors/Concurrency::graphics::int_2::x
- amp_short_vectors/Concurrency::graphics::int_2::set_yx
- amp_short_vectors/Concurrency::graphics::int_2::operator/=
- amp_short_vectors/Concurrency::graphics::int_2::get_y
- amp_short_vectors/Concurrency::graphics::int_2::gr
- amp_short_vectors/Concurrency::graphics::int_2::operator*=
- amp_short_vectors/Concurrency::graphics::int_2::r
- amp_short_vectors/Concurrency::graphics::int_2::get_xy
- amp_short_vectors/Concurrency::graphics::int_2::operator=
- amp_short_vectors/Concurrency::graphics::int_2::g
- amp_short_vectors/Concurrency::graphics::int_2::rg
- amp_short_vectors/Concurrency::graphics::int_2::xy
- amp_short_vectors/Concurrency::graphics::int_2::operator-=
- amp_short_vectors/Concurrency::graphics::int_2::get_x
- amp_short_vectors/Concurrency::graphics::int_2::yx
- amp_short_vectors/Concurrency::graphics::int_2
- amp_short_vectors/Concurrency::graphics::int_2::operator-
- amp_short_vectors/Concurrency::graphics::int_2::set_xy
- amp_short_vectors/Concurrency::graphics::int_2::operator+=
- amp_short_vectors/Concurrency::graphics::int_2::operator--
ms.assetid: 258b02e9-f1ee-46c2-8edd-dc9f69184846
ms.openlocfilehash: 000bda3a6ecc5b1ebf9be4e07ce8d703b6cd9194
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126642"
---
# <a name="int_2-class"></a>int_2-Klasse

Stellt einen kurzen Vektor aus zwei ganzen Zahlen dar.

## <a name="syntax"></a>Syntax

```cpp
class int_2;
```

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[int_2-Konstruktor](#ctor)|Ist überladen. Standardkonstruktor, initialisiert alle Elemente mit 0.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|int_2::get_x||
|int_2::get_xy||
|int_2::get_y||
|int_2::get_yx||
|int_2::ref_g||
|int_2::ref_r||
|int_2::ref_x||
|int_2::ref_y||
|int_2::set_x||
|int_2::set_xy||
|int_2::set_y||
|int_2::set_yx||

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|int_2::operator-||
|int_2:: Operator--||
|int_2::operator%=||
|int_2::operator&=||
|int_2::operator*=||
|int_2::operator/=||
|int_2::operator^=||
|int_2::operator&#124;=||
|int_2:: Operator ~||
|int_2::operator++||
|int_2::operator+=||
|int_2:: Operator <\<=||
|int_2::operator=||
|int_2:: Operator-=||
|int_2::operator>>=||

### <a name="public-constants"></a>Öffentliche Konstanten

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Größen Konstante](#int_2__size)||

### <a name="public-data-members"></a>Öffentliche Datenelemente

|Name|BESCHREIBUNG|
|----------|-----------------|
|int_2::g||
|int_2::gr||
|int_2::r||
|int_2::rg||
|int_2::x||
|int_2::xy||
|int_2::y||
|int_2::yx||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`int_2`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amp_short_vectors. h

**Namespace:** Parallelität:: Grafiken

## <a name="ctor"></a>int_2

Standardkonstruktor, initialisiert alle Elemente mit 0.

```cpp
int_2() restrict(amp,
    cpu);

int_2(
    int _V0,
    int _V1) restrict(amp,
    cpu);

int_2(
    int _V) restrict(amp,
    cpu);

int_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const double_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parameter

*_V0*<br/>
Der Wert, mit dem Element 0 initialisiert werden soll.

*_V1*<br/>
Der Wert, mit dem Element 1 initialisiert werden soll.

*_V*<br/>
Der Wert für die Initialisierung.

*_Other*<br/>
Das-Objekt, das zum Initialisieren von verwendet wird.

## <a name="int_2__size"></a>Größe

```cpp
static const int size = 2;
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
