---
title: -rootnamespace
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45dce293549674e7e6aac2714e1a7a569719c597
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-rootnamespace"></a>-rootnamespace
指定所有类型声明的命名空间。  
  
## <a name="syntax"></a>语法  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`namespace`|在包含为当前项目的所有类型声明的命名空间名称。|  
  
## <a name="remarks"></a>备注  
 如果你使用 Visual Studio 可执行文件 (Devenv.exe) 来编译创建的项目在 Visual Studio 集成的开发环境中，使用`-rootnamespace`以指定的值<xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>属性。 请参阅[Devenv 命令行开关](/visualstudio/ide/reference/devenv-command-line-switches)有关详细信息。  
  
 使用公共语言运行时 MSIL 反汇编程序 (`Ildasm.exe`) 若要查看你的输出文件中的命名空间名称。  
  
|在 Visual Studio 集成的开发环境中设置的根命名空间|  
|---|  
|1.在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“应用程序”  选项卡。<br />3.修改中的值**根 Namespace**框。|  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`和命名空间中包含所有类型声明`mynamespace`。  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Ildasm.exe（IL 反汇编程序）](https://msdn.microsoft.com/library/f7dy01k1)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
