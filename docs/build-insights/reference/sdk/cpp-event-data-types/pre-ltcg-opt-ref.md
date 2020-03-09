---
title: Preltcgoptref-Klasse
description: Der C++ Build Insights SDK-preltcgoptref-Klassen Verweis.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- PreLTCGOptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4690feddcf615a82226ce5ad2f3ee242749db04a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334607"
---
# <a name="preltcgoptref-class"></a>Preltcgoptref-Klasse

::: moniker range="<=vs-2015"

Das C++ Build Insights SDK ist kompatibel mit Visual Studio 2017 und höher. Um die Dokumentation für diese Versionen anzuzeigen, legen Sie das Steuerelement für die Visual Studio-Versions Auswahl für diesen Artikel auf Visual Studio 2017 oder Visual Studio 2019 fest.

::: moniker-end
::: moniker range=">=vs-2017"

Die `PreLTCGOptRef`-Klasse wird mit den Funktionen [matchevent](../functions/match-event.md), [matcheventinmitgliedfunction](../functions/match-event-in-member-function.md), [matcheventstack](../functions/match-event-stack.md)und [matcheventstackinmembership Function](../functions/match-event-stack-in-member-function.md) verwendet. Verwenden Sie es, um ein [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) Ereignis abzugleichen.

## <a name="syntax"></a>Syntax

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>Members

Zusammen mit den geerbten Membern der [Aktivitäts](activity.md) Basisklasse enthält die `PreLTCGOptRef`-Klasse die folgenden Member:

### <a name="constructors"></a>Konstruktoren

[Preltcgoptref](#pre-ltcg-opt-ref)

## <a name="pre-ltcg-opt-ref"></a>Preltcgoptref

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>Parameter

*Ereignis*\
Ein [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) Ereignis.

::: moniker-end