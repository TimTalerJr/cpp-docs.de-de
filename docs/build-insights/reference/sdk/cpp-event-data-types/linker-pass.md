---
title: Linkerpass-Klasse
description: Die C++ linkerpass-Klassenreferenz für das Build Insights SDK.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 49a46b57d82391f4c253128c14b1b81d52945eae
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334721"
---
# <a name="linkerpass-class"></a>Linkerpass-Klasse

::: moniker range="<=vs-2015"

Das C++ Build Insights SDK ist kompatibel mit Visual Studio 2017 und höher. Um die Dokumentation für diese Versionen anzuzeigen, legen Sie das Steuerelement für die Visual Studio-Versions Auswahl für diesen Artikel auf Visual Studio 2017 oder Visual Studio 2019 fest.

::: moniker-end
::: moniker range=">=vs-2017"

Die `LinkerPass`-Klasse wird mit den Funktionen [matchevent](../functions/match-event.md), [matcheventinmitgliedfunction](../functions/match-event-in-member-function.md), [matcheventstack](../functions/match-event-stack.md)und [matcheventstackinmembership Function](../functions/match-event-stack-in-member-function.md) verwendet. Verwenden Sie es, um ein [PASS1](../event-table.md#pass1) -oder [PASS2](../event-table.md#pass2) -Ereignis abzugleichen.

## <a name="syntax"></a>Syntax

```cpp
class LinkerPass : public Activity
{
public:
    LinkerPass(const RawEvent& event);
};
```

## <a name="members"></a>Members

Zusammen mit den geerbten Membern der [Aktivitäts](activity.md) Basisklasse enthält die `LinkerPass`-Klasse die folgenden Member:

### <a name="constructors"></a>Konstruktoren

[Linkerpass](#linker-pass)

## <a name="linker-pass"></a>Linkerpass

```cpp
LinkerPass(const RawEvent& event);
```

### <a name="parameters"></a>Parameter

*Ereignis*\
Ein [PASS1](../event-table.md#pass1) -oder [PASS2](../event-table.md#pass2) -Ereignis.

::: moniker-end
