---
title: /Tc, /Tp, /TC, /TP (Typ der Quelldatei angeben)
ms.date: 01/11/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.openlocfilehash: c93da6d2498d46e4b7bf3ad37dde852bb6bc82a1
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927627"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Typ der Quelldatei angeben)

Die **/TC** -Option gibt an, dass das Dateinamen Argument eine C-Quelldatei ist, auch wenn Sie nicht über die Erweiterung ". C" verfügt. Die **/tp** -Option gibt an, dass das Datei C++ Namen Argument eine Quelldatei ist, auch wenn es nicht über die Erweiterung. cpp oder. cxx verfügt. Ein Leerzeichen zwischen der Option und dem Dateinamen ist optional. Jede Option gibt eine Datei an. Wenn Sie weitere Dateien angeben möchten, wiederholen Sie die Option.

**/TC** und **/tp** sind globale Varianten von **/TC** und **/tp**. Sie geben dem Compiler an, alle Dateien, die in der Befehlszeile benannt sind, als C-Quelldateien C++ (/TC) oder Quelldateien ( **/tp**) zu behandeln, ohne Berücksichtigung der Position in der Befehlszeile in Bezug auf die Option. Diese globalen Optionen können mithilfe von **/TC** oder **/tp**für eine einzelne Datei überschrieben werden.

## <a name="syntax"></a>Syntax

> **/TC** _Dateiname_ **/Tp filename**/TC/TP
>  
> 
> 

## <a name="arguments"></a>Argumente

*filename*<br/>
Eine C- C++ oder Quelldatei.

## <a name="remarks"></a>Hinweise

Standardmäßig geht **cl** davon aus, dass es sich bei Dateien mit der Erweiterung. c um c-Quelldateien und-Dateien mit der Erweiterung. cpp oder. cxx um Quelldateien handelt C++ .

Wenn entweder die **TC** -oder die **TC** -Option angegeben ist, wird jede Angabe der Option [/Zc: wchar_t (wchar_t ist](zc-wchar-t-wchar-t-is-native-type.md) der systemeigene Typ) ignoriert.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C++C/**  > erweitert aus.

1. Ändern Sie die Eigenschaft **Kompilieren als** . Wählen Sie **OK** oder **anwenden** aus, um die Änderungen zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Beispiele

Diese CL-Befehlszeile gibt an, dass "Main. c", "Test. PRG" und "COLLATE. PRG" alle c-Quelldateien sind. CL erkennt "Print. PRG" nicht.

> CL Main. C/TcTEST.PRG/TcCOLLATE.PRG drucken. PRG

Diese CL-Befehlszeile gibt an, dass test1. c, test2. cxx, "test3". huh und test4. o als C++ Dateien kompiliert werden und test5. z als c-Datei kompiliert wird.

> CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
