---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a612a68cffd927f3e360406cca6d9daae4f66c86
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775623"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
指定此模块所属程序集的名称。  
  
## <a name="syntax"></a>语法  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`assembly_name`|此模块所属的程序集的名称。|  
  
## <a name="remarks"></a>备注  
 仅当指定了 `-target:module` 选项时，编译器才处理 `-moduleassemblyname` 选项。 这将导致编译器创建模块。 编译器创建的模块仅对使用 `-moduleassemblyname` 选项指定的程序集有效。 如果将模块放在不同的程序集中，则会发生运行时错误。  
  
 仅当满足以下条件时，才需要 `-moduleassemblyname` 选项：  
  
- 模块中的数据类型需要访问所引用程序集中的 `Friend` 类型。  
  
- 引用的程序集已向要在其中生成模块的程序集授予友元程序集访问权限。  
  
 有关创建模块的详细信息，请参阅[-target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)。 有关友元程序集的详细信息，请参阅[友元程序集](../../../standard/assembly/friend.md)。  
  
> [!NOTE]
> @No__t_0 选项在 Visual Studio 开发环境中不可用;仅当在命令提示符下进行编译时，它才可用。  
  
## <a name="see-also"></a>请参阅

- [如何：生成多文件程序集](../../../framework/app-domains/build-multifile-assembly.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-reference （Visual Basic）](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [.NET 中的程序集](../../../standard/assembly/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [友元程序集](../../../standard/assembly/friend.md)
