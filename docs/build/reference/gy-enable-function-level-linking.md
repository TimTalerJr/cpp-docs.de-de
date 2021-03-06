---
title: /Gy (Funktionslevel-Linking aktivieren)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 9643b8b4b4b26b3f7a8a59ed0085601b1a53094d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270723"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (Funktionslevel-Linking aktivieren)

Ermöglicht dem Compiler, einzelne Funktionen in Form von kompilierten Funktionen (COMDATs) zu kompilieren.

## <a name="syntax"></a>Syntax

```
/Gy[-]
```

## <a name="remarks"></a>Hinweise

Der Linker ist erforderlich, dass Funktionen separat als COMDATs ausgeschlossen oder bestellen einzelne Funktionen in einer DLL oder .exe-Datei verpackt werden.

Sie können die Linkeroption [/OPT (Optimierungen)](opt-optimizations.md) , die .exe-Datei nicht referenzierte Paketfunktionen ausgeschlossen werden sollen.

Sie können die Linkeroption [/Order (Put-Funktionen in Reihenfolge)](order-put-functions-in-order.md) Paketfunktionen in einer bestimmten Reihenfolge in die .exe-Datei eingeschlossen.

Inline-Funktionen sind immer verpackt, wenn sie als Aufrufe instanziiert werden (Dies geschieht z. B. wenn inlining ist deaktiviert oder eine Funktionsadresse). Darüber hinaus werden in der Klassendeklaration definierte C++-Memberfunktionen automatisch gepackt; andere Funktionen sind nicht, und nach Auswahl dieser Option ist erforderlich, um sie als Paketfunktionen kompilieren.

> [!NOTE]
>  Die ["/ Zi"](z7-zi-zi-debug-information-format.md) -Option zum Bearbeiten und fortfahren, setzt automatisch das **/Gy** Option.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Funktionslevel-Linking aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
