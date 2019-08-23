---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 052d6937846df39bd94d532e1b63ebe522dbf6c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964677"
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
|`assembly_name`|此模块所属的程序集的名称。|  
  
## <a name="remarks"></a>备注  
 `-moduleassemblyname` 仅`-target:module`当指定了选项时, 编译器才会处理该选项。 这将导致编译器创建模块。 编译器创建的模块仅对使用`-moduleassemblyname`选项指定的程序集有效。 如果将模块放在不同的程序集中, 则会发生运行时错误。  
  
 仅当满足以下条件时才需要选项:`-moduleassemblyname`  
  
- 模块中的数据类型需要访问引用程序集中`Friend`的类型。  
  
- 引用的程序集已向要在其中生成模块的程序集授予友元程序集访问权限。  
  
 有关创建模块的详细信息, 请参阅[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)。 有关友元程序集的详细信息, 请参阅[友元程序集](../../../standard/assembly/friend-assemblies.md)。  
  
> [!NOTE]
> 此`-moduleassemblyname`选项在 Visual Studio 开发环境中不可用; 它仅在从命令提示符编译时可用。  
  
## <a name="see-also"></a>请参阅

- [如何：生成单文件程序集](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [.NET 中的程序集](../../../standard/assembly/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [友元程序集](../../../standard/assembly/friend-assemblies.md)
