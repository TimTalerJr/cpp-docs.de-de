---
title: 'Ressourcencompiler: Fehler RC2144'
ms.date: 11/04/2016
f1_keywords:
- RC2144
helpviewer_keywords:
- RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
ms.openlocfilehash: deabd639e04d5b78b398cda9245e9726e2124740
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173469"
---
# <a name="resource-compiler-error-rc2144"></a>Ressourcencompiler: Fehler RC2144

Primäre Sprach-ID ist keine Zahl

Primäre Sprach-ID muss eine hexadezimale Sprachen-ID sein. Unter [Sprach- und Länder-/Regionen-Strings](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) in der *Laufzeit-Bibliothek-Referenz* finden Sie eine Liste der gültigen Sprach-IDs.

Dieser Fehler kann auch auftreten, wenn Sie Ressourcen hinzugefügt und aus der.RC-Datei mithilfe des Tools gelöscht haben. Um dieses Problem zu beheben, öffnen Sie die.RC-Datei in einem Texteditor und bereinigen Sie manuell alle nicht verwendeten Ressourcen.