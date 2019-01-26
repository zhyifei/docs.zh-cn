---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 35519be6ddaed64b3e5e2129efb611e0a812ebc3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535173"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
指定此模块所属程序集的名称。  
  
## <a name="syntax"></a>语法  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`assembly_name`|此模块的程序集的名称。|  
  
## <a name="remarks"></a>备注  
 编译器进程`-moduleassemblyname`选项仅当`-target:module`指定选项。 这将导致编译器创建一个模块。 由编译器创建的模块是仅对与指定的程序集的有效`-moduleassemblyname`选项。 如果将模块置于不同的程序集，将发生运行时错误。  
  
 `-moduleassemblyname`选项仅当满足以下条件时，才需要：  
  
-   该模块中的数据类型需要有权`Friend`中引用的程序集中的类型。  
  
-   将在其中生成该模块的程序集引用的程序集具有授予友元程序集访问权限。  
  
 有关创建模块的详细信息，请参阅[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)。 有关友元程序集的详细信息，请参阅[友元程序集](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)。  
  
> [!NOTE]
>  `-moduleassemblyname`选项不是可从 Visual Studio 开发环境中; 它是可仅在编译时从命令提示符。  
  
## <a name="see-also"></a>请参阅
- [如何：生成多文件程序集](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-目标 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-参考 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [友元程序集](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
