---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 82a7114027451d1342e6dc0846799933ce44d968
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
使编译器接受指定的 Visual Basic 语言版本中包含的语法。  
  
## <a name="syntax"></a>语法  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>自变量  
 `version`  
 必须的。 要在编译期间使用的语言版本。 接受的值是`9`， `9.0`， `10`，和`10.0`。  
  
## <a name="remarks"></a>备注  
 `-langversion`选项指定编译器接受哪些语法。 例如，如果你指定的语言版本为 9.0，编译器将生成有关仅在版本 10.0 中有效和更高版本的语法错误。  
  
 当你面向不同版本的.NET framework 开发应用程序时，你可以使用此选项。 例如，如果你正面向.NET Framework 3.5，你可以使用此选项以确保不使用从语言版本 10.0 的语法。  
  
 你可以设置`-langversion`直接只能通过使用命令行。 有关详细信息，请参阅[面向特定的 .NET Framework 版本](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)。  
  
## <a name="example"></a>示例  
 下面的代码编译`sample.vb`对于 Visual Basic 9.0 版。  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [面向特定的 .NET Framework 版本](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
