---
title: /target
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d9a5307970ac745b4f102d0008e64b985c00e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname"></a>/target
指定此模块所属程序集的名称。  
  
## <a name="syntax"></a>语法  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`assembly_name`|此模块的程序集的名称。|  
  
## <a name="remarks"></a>备注  
 编译器进程`/moduleassemblyname`选项仅当`/target:module`指定选项。 这将导致编译器创建的模块。 由编译器创建的模块是仅对与指定的程序集有效`/moduleassemblyname`选项。 如果将模块放在不同的程序集时，将发生运行时错误。  
  
 `/moduleassemblyname`仅当满足以下条件时，才需要选项：  
  
-   模块中的数据类型需要访问`Friend`引用的程序集中的类型。  
  
-   引用的程序集具有友元程序集访问权限授予将在其中生成该模块的程序集。  
  
 有关创建模块的详细信息，请参阅[/target (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)。 友元程序集有关的详细信息，请参阅[友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)。  
  
> [!NOTE]
>  `/moduleassemblyname`选项不是可从 Visual Studio 开发环境中; 它是可用仅编译时从命令提示符。  
  
## <a name="see-also"></a>另请参阅  
 [如何：生成多文件程序集](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
