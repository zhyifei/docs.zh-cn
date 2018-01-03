---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b02171b28034d676b7027e96c2c66e36be9ae604
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="rootnamespace"></a>/rootnamespace
指定所有类型声明的命名空间。  
  
## <a name="syntax"></a>语法  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`namespace`|在包含为当前项目的所有类型声明的命名空间名称。|  
  
## <a name="remarks"></a>备注  
 如果你使用 Visual Studio 可执行文件 (Devenv.exe) 来编译创建的项目在 Visual Studio 集成的开发环境中，使用`/rootnamespace`以指定的值<xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>属性。 请参阅[Devenv 命令行开关](/visualstudio/ide/reference/devenv-command-line-switches)有关详细信息。  
  
 使用公共语言运行时 MSIL 反汇编程序 (`Ildasm.exe`) 若要查看你的输出文件中的命名空间名称。  
  
|在 Visual Studio 中设置 /rootnamespace 集成开发环境|  
|---|  
|1.在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“应用程序”  选项卡。<br />3.修改中的值**根 Namespace**框。|  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`和命名空间中包含所有类型声明`mynamespace`。  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Ildasm.exe（IL 反汇编程序）](https://msdn.microsoft.com/library/f7dy01k1)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
