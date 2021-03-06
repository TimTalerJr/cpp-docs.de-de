---
title: Executableimageoutput-Klasse
description: Der C++ Build Insights SDK executableimageoutput-Klassen Verweis.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5a2e417a7dd976f257b4dd5a3aabfdf440c604fc
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334877"
---
# <a name="executableimageoutput-class"></a>Executableimageoutput-Klasse

::: moniker range="<=vs-2015"

Das C++ Build Insights SDK ist kompatibel mit Visual Studio 2017 und höher. Um die Dokumentation für diese Versionen anzuzeigen, legen Sie das Steuerelement für die Visual Studio-Versions Auswahl für diesen Artikel auf Visual Studio 2017 oder Visual Studio 2019 fest.

::: moniker-end
::: moniker range=">=vs-2017"

Die `ExecutableImageOutput`-Klasse wird mit den Funktionen [matchevent](../functions/match-event.md), [matcheventinmitgliedfunction](../functions/match-event-in-member-function.md), [matcheventstack](../functions/match-event-stack.md)und [matcheventstackinmembership Function](../functions/match-event-stack-in-member-function.md) verwendet. Verwenden Sie es, um ein [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) Ereignis abzugleichen.

## <a name="syntax"></a>Syntax

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>Members

Zusammen mit den geerbten Membern aus der [FileOutput](file-output.md) -Basisklasse enthält die `ExecutableImageOutput`-Klasse die folgenden Member:

### <a name="constructors"></a>Konstruktoren

[Executableimageoutput](#executable-image-output)

## <a name="executable-image-output"></a>Executableimageoutput

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parameter

*Ereignis*\
Ein [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) Ereignis.

::: moniker-end
