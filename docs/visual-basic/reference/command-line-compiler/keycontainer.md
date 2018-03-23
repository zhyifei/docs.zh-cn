---
title: -keycontainer
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b433182a502761fb3840ed2003cc50e053fb072a
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-keycontainer"></a>-keycontainer
指定密钥对的密钥容器名称从而为程序集赋予强名称。  
  
## <a name="syntax"></a>语法  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`container`|必须的。 包含密钥的容器文件。 将文件名括在双引号 ("") 如果名称包含空格。|  
  
## <a name="remarks"></a>备注  
 通过将公钥插入程序集清单，并使用私钥签名最终的程序集中，编译器将创建可共享的组件。 若要生成的密钥文件，请键入`sn -k``file`在命令行。 `-i`选项将安装到容器的密钥对。 有关详细信息，请参阅 [Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md))。  
  
 如果使用编译`-target:module`，密钥文件的名称保存在模块中，并合并到编译为程序集时创建的程序集[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)。  
  
 还可以将此选项指定为任何 Microsoft 中间语言 (MSIL) 模块的源代码中的自定义特性 (<xref:System.Reflection.AssemblyKeyNameAttribute>)。  
  
 此外，可使用 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 将加密信息传递给编译器。 如果需要部分签名的程序集，请使用 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)。  
  
 请参阅[创建和使用具有强名称程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)有关程序集进行签名的详细信息。  
  
> [!NOTE]
>  `-keycontainer`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译源文件`Input.vb`和指定的密钥容器。  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
