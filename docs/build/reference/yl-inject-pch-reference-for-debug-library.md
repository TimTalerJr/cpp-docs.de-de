---
title: /Yl (PCH-Verweis für Debugbibliothek einfügen)
ms.date: 01/29/2018
f1_keywords:
- /yl
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
ms.openlocfilehash: 92e47836e0fdae077defa0fe35b515ab4ca20a66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316248"
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (PCH-Verweis für Debugbibliothek einfügen)

Die **/Yl** Option generiert ein eindeutige Symbol in einer vorkompilierten Headerdatei und ein Verweis auf dieses Symbol wird in allen Objektdateien, die Verwendung des vorkompilierten Headers eingefügt.

## <a name="syntax"></a>Syntax

>**/ Yl**
> **/Yl**_Namen_
> **/Yl-**

### <a name="arguments"></a>Argumente

*name*<br/>
Ein optionaler Name als Teil der das eindeutige Symbol verwendet wird.

*\-*<br/>
Deaktiviert ein Bindestrich (-) explizit die **/Yl** -Compileroption.

## <a name="remarks"></a>Hinweise

Die **/Yl** Compileroption erstellt eine eindeutige Symboldefinition in einer vorkompilierten Headerdatei erstellt mithilfe der ["/ Yc"](yc-create-precompiled-header-file.md) Option. Verweise auf dieses Symbol werden automatisch eingefügt, in allen Dateien, die durch die Verwendung des vorkompilierten Headers einbeziehen der ["/ Yu"](yu-use-precompiled-header-file.md) -Compileroption. Die **/Yl** Option ist standardmäßig aktiviert, wenn **"/ Yc"** wird verwendet, um eine vorkompilierte Headerdatei erstellen.

Die **/Yl**_Namen_ Option wird verwendet, um ein identifizierbaren Symbol in der vorkompilierten Headerdatei zu erstellen. Der Compiler verwendet die *Namen* Argument als Teil des ergänzten Symbolnamens erstellt, ähnlich wie `__@@_PchSym_@00@...@name`, wobei die Auslassungspunkte (...) dar, die einen eindeutigen vom Compiler generierter Zeichenfolge Zeichen. Wenn die *Namen* Argument ausgelassen wird, generiert der Compiler einen Symbolnamen automatisch. In der Regel müssen Sie nicht den Namen des Symbols kennen. Wenn Ihr Projekt verwendet jedoch mehr als eine vorkompilierte Headerdatei, die **/Yl**_Namen_ Option ist möglicherweise nützlich, um zu ermitteln, welches Objekt verwenden sollen, die vorkompilierte Header. Sie können *Namen* als Suchzeichenfolge So suchen Sie die Symbolverweis in einer Dumpdatei.

**/Yl-** deaktiviert das Standardverhalten und ist kein identifizierende Symbol in der vorkompilierten Headerdatei. Kompilierte Dateien, die dieses vorkompilierten Headers enthalten ist eine Referenz zu häufigen Symbol nicht abgerufen werden.

Wenn **"/ Yc"** nicht angegeben ist, alle **/Yl** Option hat keine Auswirkungen, aber wenn angegeben, muss dieser entsprechen alle **/Yl** Option übergeben wird, wenn **"/ Yc"** ist angegeben.

Bei Verwendung von **/Yl-**, **"/ Yc"** und ["/ Z7"](z7-zi-zi-debug-information-format.md) Optionen zum Erstellen einer vorkompilierten Headerdatei, die Debuginformationen befindet sich in der Objektdatei, die für die Quelldatei, die zum Erstellen der vorkompilierten Header, anstatt eine separate PDB-Datei. Wenn die Objektdatei Teil einer Bibliothek, klicken Sie dann erfolgt [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) Fehler oder [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) Warnungen können in Builds, die diese Bibliothek und die vorkompilierte Headerdatei verwenden auftreten, wenn die Quelldatei, die zum Erstellen verwendet das vorkompilierte Headerdatei werden keine Symbole selbst definiert. Der Linker kann die Objektdatei über den Link, zusammen mit den zugehörigen Debuginformationen, ausschließen, wenn es sich bei "nothing" in der Objektdatei in der bibliothekclient verwiesen wird. Um dieses Problem zu beheben, geben Sie **/Yl** (oder entfernen Sie die **/Yl-** Option) bei Verwendung von **"/ Yc"** zum Erstellen der vorkompilierten Header-Datei. Dadurch wird sichergestellt, dass die Objektdatei, aus der Bibliothek, die die Debuginformationen enthält, die in Ihrem Build verknüpft ruft.

Weitere Informationen zu vorkompilierten Headern finden Sie unter:

- [/Y (Vorkompilierte Header)](y-precompiled-headers.md)

- [Vorkompilierte Headerdateien](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Hinzufügen der **/Yl**_Namen_ -Compileroption in der **zusätzliche Optionen** Feld. Klicken Sie auf **OK**, um die Änderungen zu speichern.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
