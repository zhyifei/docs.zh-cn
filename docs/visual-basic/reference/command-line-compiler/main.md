---
title: -主要
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b22b4bb1b6649265eabc02beb6b0145f7c075b27
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-main"></a>-主要
指定包含 `Sub Main` 过程的类或模块。  
  
## <a name="syntax"></a>语法  
  
```  
-main:location  
```  
  
## <a name="arguments"></a>自变量  
 `location`  
 必须的。 名称的类或模块包含`Sub Main`在程序启动时要调用的过程。 这可能是窗体中**的 main: module**或**-main:namespace.module**。  
  
## <a name="remarks"></a>备注  
 在创建可执行文件或 Windows 可执行程序时，请使用此选项。 如果**-主要**省略选项，编译器将搜索有效的共享`Sub Main`所有公共类和模块中。  
  
 请参阅[Visual Basic 中的 Main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)有关的各种形式的讨论`Main`过程。  
  
 当`location`是继承自的类<xref:System.Windows.Forms.Form>，则编译器会提供默认`Main`如果类没有启动的应用程序的过程`Main`过程。 这样，你将在命令行在开发环境中创建的代码编译。  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/main_1.vb)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a>若要设置-主要在 Visual Studio 集成的开发环境  
  
1.  在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。  
  
2.  单击“应用程序”  选项卡。  
  
3.  请确保**启用应用程序框架**未选中复选框。  
  
4.  修改中的值**启动对象**框。  
  
## <a name="example"></a>示例  
 下面的代码编译`T2.vb`和`T3.vb`，并指定，`Sub Main`将在中找到过程`Test2`类。  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-目标 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Visual Basic 中的 main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
