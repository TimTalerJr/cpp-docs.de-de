---
title: CAutoPtrList-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 2558c522f7903e8d59363cd77d1a86027f6a7511
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260278"
---
# <a name="cautoptrlist-class"></a>CAutoPtrList-Klasse

Diese Klasse stellt nützliche Methoden aus, wenn Sie eine Liste von intelligenten Zeigern zu erstellen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Parameter

*E*<br/>
Der Zeigertyp.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Der Konstruktor.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt einen Konstruktor bereit und leitet Sie Methoden aus [CAtlList](../../atl/reference/catllist-class.md) und [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) zur Unterstützung der Erstellung eines Listenobjekts intelligente Zeiger speichern. Die Klasse [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) bietet eine ähnliche Funktion für ein Arrayobjekt.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="cautoptrlist"></a>  CAutoPtrList::CAutoPtrList

Der Konstruktor.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parameter

*nBlockSize*<br/>
Die Blockgröße hat den Standardwert 10.

### <a name="remarks"></a>Hinweise

Die Blockgröße ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.

## <a name="see-also"></a>Siehe auch

[CAtlList-Klasse](../../atl/reference/catllist-class.md)<br/>
[CAutoPtrElementTraits-Klasse](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
