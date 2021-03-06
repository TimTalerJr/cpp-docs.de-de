---
title: Auswählen des Formats von .netmodule-Eingabedateien
ms.date: 11/04/2016
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
ms.openlocfilehash: d48bfe84210143db333d1e6b081acf1aa66980cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294576"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>Auswählen des Formats von .netmodule-Eingabedateien

Eine MSIL-OBJ-Datei (kompiliert mit ["/ CLR"](clr-common-language-runtime-compilation.md)) kann auch als eine NETMODULE-Datei verwendet werden.  OBJ-Dateien enthalten die Metadaten und systemeigene Symbole.  NETMODULE-Dateien enthalten nur Metadaten.

Sie können eine MSIL-OBJ-Datei an einem beliebigen anderen Visual Studio-Compiler übergeben, über die/addmodule-Compileroption (aber beachten Sie, dass die OBJ-Datei der resultierenden Assembly Teil, und mit der Assembly geliefert werden muss.)  Beispielsweise haben in Visual c# und Visual Basic/addmodule-Compileroption.

> [!NOTE]
>  In den meisten Fällen müssen Sie an den Linker die OBJ-Datei aus der Kompilierung übergeben, die das Modul .net erstellt.  Eine DLL- oder NETMODULE-Datei MSIL-Modul-Datei an dem Linker übergeben kann dazu führen, dass LNK1107.

OBJ-Dateien, zusammen mit ihren zugeordneten h-Dateien, die, die Sie über verweisen #include in Quelle, können Sie C++-Anwendungen nutzen den nativen Typen in das Modul, während in einer NETMODULE-Datei nur die verwalteten Typen, die von einer C++-Anwendung genutzt werden können.  Wenn Sie versuchen, eine OBJ-Datei übergeben #using, Informationen zu systemeigenen Typen nicht zur Verfügung; #include Sie stattdessen die OBJ-Datei die .h-Datei.

Andere Visual Studio-Compiler können nur mit verwaltete Typen aus einem Modul nutzen.

Verwenden Sie Folgendes, um zu bestimmen, ob Sie eine NETMODULE-Datei oder eine OBJ-Datei als Moduleingabe für den MSVC-Linker verwenden möchten:

- Wenn Sie mit einem Visual Studio-Compiler als Visual C++ erstellen, erstellen Sie einer NETMODULE-Datei, und verwenden Sie die NETMODULE-Datei als Eingabe für den Linker.

- Wenn Sie den MSVC-Compiler mithilfe erzeugen Module und wenn die Module verwendet werden soll, um etwas anderes als eine Bibliothek, zu erstellen, verwenden die OBJ-Dateien, die vom Compiler als Moduleingabe für den Linker erstellt; Verwenden Sie nicht die NETMODULE-Datei als Eingabe.

- Wenn Ihre Module zur Erstellung einer systemeigenen (keine verwaltete)-Bibliothek verwendet werden, verwenden Sie die OBJ-Dateien als Moduleingabe für den Linker aus, und generieren Sie eine LIB-Datei für Bibliothek.

- Wenn Ihre Module zum Erstellen einer verwalteten Bibliothek verwendet werden, und wenn alle Moduleingabe für den Linker überprüfbar sind (erstellt mit/clr: safe), verwenden Sie die OBJ-Dateien als Moduleingabe für den Linker, und generieren Sie einer DLL-Datei (Assembly) oder die Bibliotheksdatei NETMODULE-Datei (Modul).

- Wenn Ihre Module zum Erstellen einer verwalteten Bibliothek verwendet werden, und eine oder mehrere Module Eingabe für den Linker mit nur "/ CLR" erstellt wird, verwenden Sie die OBJ-Dateien als Moduleingabe für den Linker aus, und generiert eine DLL-Datei (Assembly).  Wenn verwalteter Typen aus der Bibliothek und ggf. auch C++-Anwendungen nutzen den nativen Typen in der Bibliothek verfügbar gemacht werden sollen, besteht Ihre Bibliothek die OBJ-Dateien für die Bibliotheken Komponentenmodule aus (Sie sollten auch die h-Dateien für jedes Modul senden Damit sie mit verwiesen werden können #include aus dem Quellcode).

## <a name="see-also"></a>Siehe auch

[.NETMODULE-Dateien als Eingabe für den Linker](netmodule-files-as-linker-input.md)
