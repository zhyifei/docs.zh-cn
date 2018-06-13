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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d28d0556a662099e4e5e74b22583fc3c8b4c313f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656108"
---
# <a name="-vbruntime"></a>-vbruntime
指定编译器应在不引用 Visual Basic 运行库的情况下进行编译，或在引用特定运行库的情况下进行编译。  
  
## <a name="syntax"></a>语法  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>自变量  
 \-  
 编译而无需对 Visual Basic 运行时库的引用。  
  
 \+  
 使用默认的 Visual Basic 运行时库的引用进行编译。  
  
 \*  
 编译而不引用 Visual Basic 运行库，并将嵌入到程序集从 Visual Basic 运行库的核心功能。  
  
 `path`  
 使用指定的库 (DLL) 的引用进行编译。  
  
## <a name="remarks"></a>备注  
 `-vbruntime`编译器选项，可指定编译器应编译而无需对 Visual Basic 运行时库的引用。 如果编译而无需对 Visual Basic 运行时库的引用时，在生成的 Visual Basic 运行时帮助程序调用的代码或语言构造记录错误或警告。 (A *Visual Basic 运行时帮助器*是在运行时执行特定的语言语义时调用的 Microsoft.VisualBasic.dll 中定义的函数。)  
  
 `-vbruntime+`选项生成相同的行为，如果没有则会发生`-vbruntime`指定开关。 你可以使用`-vbruntime+`选项重写之前`-vbruntime`开关。  
  
 大多数对象`My`使用时，类型将不可用`-vbruntime-`或`-vbruntime:path`选项。  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>嵌入 Visual Basic 运行时核心功能  
 `-vbruntime*`选项使你能够对运行时库的引用的情况下编译。 相反，从 Visual Basic 运行库的核心功能嵌入中用户程序集。 如果在不包含 Visual Basic 运行时的平台上运行你的应用程序，你可以使用此选项。  
  
 嵌入以下运行时成员：  
  
-   <xref:Microsoft.VisualBasic.CompilerServices.Conversions> 类  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> 方法  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> 方法  
  
-   <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> 方法  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab> 常量  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 常量  
  
-   某些对象`My`类型  
  
 如果在编译时使用`-vbruntime*`选项和你的代码从未嵌入的核心功能与 Visual Basic 运行时库引用的成员，编译器将返回错误，该值指示成员不可用。  
  
## <a name="referencing-a-specified-library"></a>引用指定的库  
 你可以使用`path`自变量使用对自定义运行时库，而不是默认的 Visual Basic 运行时库的引用进行编译。  
  
 如果值`path`参数为 DLL 的完全限定的路径，则编译器将使用该文件作为运行时库。 如果值`path`参数不是 DLL 的完全限定的路径，Visual Basic 编译器将首先搜索当前文件夹中标识的 DLL。 它然后将在使用指定的路径中搜索[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)编译器选项。 如果`-sdkpath`不使用编译器选项，编译器将搜索在.NET Framework 文件夹中的标识 dll (`%systemroot%\Microsoft.NET\Framework\versionNumber`)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`-vbruntime`选项使用对自定义库的引用进行编译。  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 核心 – 在 Visual Studio 2010 SP1 中的新编译模式](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
