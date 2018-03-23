---
title: -addmodule
ms.date: 03/09/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c17d5541fe2d02ba88f4c5ef259b2248f371dfe5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-addmodule"></a>-addmodule
使编译器让指定文件中的所有类型信息可供当前正在编译的项目使用。  
  
## <a name="syntax"></a>语法  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>自变量  
 `fileList`  
 必须的。 包含的元数据，但不是包含程序集清单的文件以逗号分隔列表。 文件名称中包含空格应该用引号引起来 ("")。  
  
## <a name="remarks"></a>备注  
 通过列出的文件`fileList`参数必须用来创建`-target:module`选项，或与另一编译器等效于`-target:module`。  
  
 使用添加的所有模块`-addmodule`必须在运行时是输出文件所在的同一目录中。 也就是说，你也可以在编译时，指定在任何目录中的模块，但在运行时的模块必须在应用程序目录。 如果不是这样，你将获取<xref:System.TypeLoadException>错误。  
  
 如果您指定 （隐式或显式） 任何[-目标 (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)选项而不`-target:module`与`-addmodule`，传递给文件`-addmodule`成为项目的程序集的一部分。 运行具有一个输出文件所需的程序集或使用更多的文件添加`-addmodule`。  
  
 使用[/reference (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/reference.md)从包含程序集的文件导入元数据。  
  
> [!NOTE]
>  `-addmodule`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码创建一个模块。  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 下面的代码导入模块的类型。  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 当你运行`t1`，它将输出`802`。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-目标 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [-参考 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
