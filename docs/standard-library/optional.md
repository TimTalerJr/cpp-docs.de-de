---
title: '&lt;optional&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: bce31811c98d351f3c561b3136d41f7ed23d13e0
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687256"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

Definiert die Containerklassen Vorlage `optional` und mehrere unterstützende Vorlagen.

## <a name="requirements"></a>Anforderungen

**Header:** \<optional >

**Namespace:** std

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|Testet, ob ein Objekt gleich einem anderen Objekt ist.|
|[Operator!=](../standard-library/optional-operators.md#op_neq)|Testet, ob ein Objekt ungleich einem anderen Objekt ist.|
|[operator<](../standard-library/optional-operators.md#op_lt)|Testet, ob das Objekt auf der linken Seite kleiner ist als das Objekt auf der rechten Seite.|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|Testet, ob das-Objekt Links kleiner als oder gleich dem-Objekt auf der rechten Seite ist.|
|[operator>](../standard-library/optional-operators.md#op_gt)|Testet, ob das-Objekt auf der linken Seite größer als das-Objekt auf der rechten Seite ist.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|Testet, ob das-Objekt auf der linken Seite größer als oder gleich dem-Objekt auf der rechten Seite ist.|

> [!NOTE]
> Neben relationalen vergleichen unterstützen \<optional >-Operatoren auch Vergleiche mit **nullopt** und `T`.

### <a name="functions"></a>Funktionen

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Macht ein-Objekt optional.|
|[swap](../standard-library/optional-functions.md#swap)|Vertauscht die enthaltenen Werte von zwei `optional`-Objekten.|

### <a name="classes-and-structs"></a>Klassen und Strukturen

|||
|-|-|
|hash|Gibt einen Hash des enthaltenen-Objekts zurück.|
|[optionale Klasse](../standard-library/optional-class.md)|Beschreibt ein Objekt, das einen Wert enthalten kann.|
|[nullopt_t-Struktur](../standard-library/nullopt-t-structure.md)|Beschreibt ein Objekt, das keinen Wert enthält.|
|[bad_optional_access-Klasse](../standard-library/bad-optional-access-class.md)|Beschreibt ein Objekt, das als Ausnahme ausgelöst wurde, um einen Versuch, auf einen Wert zuzugreifen, zu melden.|

### <a name="objects"></a>erzwingen

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|Eine Instanz von `nullopt_t` für Vergleiche.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
