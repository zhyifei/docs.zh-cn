---
title: 示例编译命令行 (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7c3fac318e05c5e3d6fb9dd7117cac70ead03dc
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a>示例编译命令行 (Visual Basic)
作为编译的替代方法[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]内程序[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]，你可以从命令行以生成可执行文件 (.exe) 文件或动态链接库 (.dll) 文件进行编译。  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]命令行编译器支持一组完整的控制输入和输出文件、 程序集，以及调试的选项和预处理器的选项。 每个选项可在两个可互换的窗体中：`-option`和`/option`。 本文档只会显示`-option`窗体。  
  
 下表列出了你可以修改供自己使用的一些示例命令行。  
  
|到|使用|  
|--------|---------|  
|编译 File.vb 并创建 File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|编译 File.vb 并创建 File.dll|`vbc -target:library File.vb`|  
|编译 File.vb 并创建 My.exe|`vbc -out:My.exe File.vb`|  
|编译所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]在上文件在当前目录中，通过使用优化和`DEBUG`定义，从而生成 File2.exe 的符号|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|编译所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]在当前目录中，而不显示的徽标或警告生成 File2.dll 的调试版本的文件|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|编译所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Something.dll 到当前目录中的文件|`vbc -target:library -out:Something.dll *.vb`|  
  
 在从命令行编译时，必须显式引用 Microsoft[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]通过运行时库`-reference`编译器选项。  
  
> [!TIP]
>  通过使用 Visual Studio IDE 生成项目时，你可以显示有关信息关联**vbc**命令使用其在输出窗口中的编译器选项。 若要显示此信息，请打开[选项对话框、 项目和解决方案、 生成和运行](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)，然后设置**MSBuild 项目生成输出详细级别**到**正常**或更高级别的详细级别。 有关详细信息，请参阅[如何：查看、保存和配置生成日志文件](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
