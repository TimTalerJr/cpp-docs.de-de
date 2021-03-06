---
title: Importieren mithilfe von DEF-Dateien
ms.date: 11/04/2016
helpviewer_keywords:
- importing DLLs [C++], DEF files
- def files [C++], importing with
- .def files [C++], importing with
- dllimport attribute [C++], DEF files
- DLLs [C++], DEF files
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
ms.openlocfilehash: 13a6a375d6200f73dd9845d057d1954c2b65485c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273416"
---
# <a name="importing-using-def-files"></a>Importieren mithilfe von DEF-Dateien

Wenn Sie auch verwenden **von "__declspec(dllimport)" "** zusammen mit einer DEF-Datei, Sie sollten die DEF-Datei, um die Daten anstelle von KONSTANTEN verwenden, um die Wahrscheinlichkeit zu verringern, dass falsche Codierung Probleme entstehen ändern:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   DATA
```

In der folgende Tabelle wird erläutert, weshalb.

|Stichwort|Gibt in der Importbibliothek her|Exporte|
|-------------|---------------------------------|-------------|
|`CONSTANT`|`_imp_ulDataInDll`, `_ulDataInDll`|`_ulDataInDll`|
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|

Mithilfe von **von "__declspec(dllimport)" "** und Konstante enthält sowohl die `imp` Version und den nicht ergänzten Namen in der LIB-DLL-Importbibliothek, die erstellt wird, um die explizite Verknüpfung zu ermöglichen. Mithilfe von **von "__declspec(dllimport)" "** und Listen der Daten lediglich die `imp` Version des Namens.

Wenn Sie die Konstante verwenden, eine der folgenden Codekonstrukte kann verwendet werden für den Zugriff auf `ulDataInDll`:

```
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/
if (ulDataInDll == 0L)   /*sample code fragment*/
```

\- oder -

```
ULONG *ulDataInDll;      /*prototype*/
if (*ulDataInDll == 0L)  /*sample code fragment*/
```

Aber wenn Sie Daten in der DEF-Datei verwenden, nur mit der folgenden Definition kompiliertem Code kann greifen auf die Variable `ulDataInDll`:

```
__declspec(dllimport) ULONG ulDataInDll;

if (ulDataInDll == 0L)   /*sample code fragment*/
```

Konstante riskanter ist, da Sie vergessen, die zusätzliche Ebene der Dereferenzierung, Sie möglicherweise die Importadresstabelle Zeiger auf die Variable zugreifen könnten, nicht auf die Variable selbst. Diese Art von Problem kann häufig als eine zugriffsverletzung Ergebnissen führen, da die Importadresstabelle derzeit durch den Compiler und Linker schreibgeschützt ist.

Der aktuelle MSVC-Linker gibt eine Warnung, solche Konstante in der DEF-Datei für diesen Fall berücksichtigen. Der einzige wirkliche Grund für die Konstante ist, wenn Sie eine Objektdatei, wo die Header-Datei nicht aufgeführt neu kompilieren können **von "__declspec(dllimport)" "** für den Prototyp.

## <a name="see-also"></a>Siehe auch

[Importieren in eine Anwendung](importing-into-an-application.md)
