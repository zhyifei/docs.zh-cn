---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005052"
---
# <a name="-vbruntime"></a>-vbruntime
指定编译器应在不引用 Visual Basic 运行库的情况下进行编译，或在引用特定运行库的情况下进行编译。  
  
## <a name="syntax"></a>语法  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>参数  
 \-  
 在不引用 Visual Basic 运行时库的情况下编译。  
  
 \+  
 使用对默认 Visual Basic 运行时库的引用进行编译。  
  
 \*  
 在不引用 Visual Basic 运行时库的情况下进行编译，并将 Visual Basic 运行时库中的核心功能嵌入到程序集中。  
  
 `path`  
 使用对指定库（DLL）的引用进行编译。  
  
## <a name="remarks"></a>备注  
 使用 `-vbruntime` 编译器选项，可以指定编译器应在不引用 Visual Basic 运行库的情况下编译。 如果在不引用 Visual Basic 运行时库的情况下进行编译，则会记录生成对 Visual Basic 运行时帮助程序的调用的代码或语言构造的错误或警告。 （ *Visual Basic 运行时帮助器*是一个在运行时调用的函数，用于执行特定的语言语义。）  
  
 如果未指定 `-vbruntime` 开关，则 `-vbruntime+` 选项将产生相同的行为。 您可以使用 `-vbruntime+` 选项来覆盖以前的 `-vbruntime` 开关。  
  
 使用 `-vbruntime-` 或 `-vbruntime:path` 选项时，不能使用 `My` 类型的大多数对象。  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>嵌入 Visual Basic 运行时核心功能  
 使用 `-vbruntime*` 选项，可以在不引用运行库的情况下编译。 相反，将 Visual Basic 运行时库中的核心功能嵌入用户程序集。 如果你的应用程序在不包含 Visual Basic 运行时的平台上运行，则可以使用此选项。  
  
 以下运行时成员嵌入：  
  
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions> 类  
  
- <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> 方法  
  
- <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> 方法  
  
- <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> 方法  
  
- <xref:Microsoft.VisualBasic.Constants.vbBack> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbCr> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbCrLf> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbFormFeed> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbLf> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbNewLine> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullChar> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullString> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbTab> 常量  
  
- <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 常量  
  
- `My` 类型的某些对象  
  
 如果使用 `-vbruntime*` 选项进行编译，并且你的代码引用了未嵌入核心功能的 Visual Basic 运行时库中的成员，则编译器将返回一个错误，指示该成员不可用。  
  
## <a name="referencing-a-specified-library"></a>引用指定的库  
 您可以使用 `path` 参数通过对自定义运行库的引用进行编译，而不是使用默认 Visual Basic 运行时库。  
  
 如果 `path` 参数的值是 DLL 的完全限定路径，则编译器将使用该文件作为运行时库。 如果 `path` 参数的值不是 DLL 的完全限定路径，则 Visual Basic 编译器将首先在当前文件夹中搜索标识的 DLL。 然后，它将在你使用[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)编译器选项指定的路径中进行搜索。 如果未使用 `-sdkpath` 编译器选项，编译器将在 .NET Framework 文件夹（`%systemroot%\Microsoft.NET\Framework\versionNumber`）中搜索标识的 DLL。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 `-vbruntime` 选项通过对自定义库的引用进行编译。  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 核心– Visual Studio 2010 SP1 中的新编译模式](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
