---
title: 示例编译命令行 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b0f1fc1d269801efdbf2e89d10679dc8159851f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653658"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>示例编译命令行 (Visual Basic)
作为编译 Visual Basic 程序从 Visual Studio 中的替代方法，你可以从命令行以生成可执行文件 (.exe) 文件或动态链接库 (.dll) 文件进行编译。  
  
 Visual Basic 命令行编译器支持一组完整的选项来控制输入和输出文件、 程序集，和调试和预处理器的选项。 每个选项可在两个可互换的窗体中：`-option`和`/option`。 本文档只会显示`-option`窗体。  
  
 下表列出了你可以修改供自己使用的一些示例命令行。  
  
|到|使用|  
|--------|---------|  
|编译 File.vb 并创建 File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|编译 File.vb 并创建 File.dll|`vbc -target:library File.vb`|  
|编译 File.vb 并创建 My.exe|`vbc -out:My.exe File.vb`|  
|编译 File.vb 并创建一个库和名为 File.dll 引用程序集|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|在当前目录中，通过使用优化的所有 Visual Basic 文件都编译上和`DEBUG`定义，从而生成 File2.exe 的符号|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|在当前目录中，而不显示的徽标或警告生成 File2.dll 的调试版本的所有 Visual Basic 文件都编译|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|编译到 Something.dll 的当前目录中的所有 Visual Basic 文件|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  通过使用 Visual Studio IDE 生成项目时，你可以显示有关信息关联**vbc**命令使用其在输出窗口中的编译器选项。 若要显示此信息，请打开[选项对话框、 项目和解决方案、 生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后设置**MSBuild 项目生成输出详细级别**到**正常**或更高级别的详细级别。   
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
