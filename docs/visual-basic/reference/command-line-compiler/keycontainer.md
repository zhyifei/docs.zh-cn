---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 5892baaa2732d95cfe698147e06b914af968adc5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929428"
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
|`container`|必需。 包含密钥的容器文件。 如果名称包含空格, 请将文件名用引号 ("") 引起来。|  
  
## <a name="remarks"></a>备注  
 编译器通过将公钥插入程序集清单并通过使用私钥对最终程序集进行签名来创建可共享的组件。 若要生成密钥文件，请在命令行键入 `sn -k file`。 `-i`选项将密钥对安装到容器中。 有关详细信息, 请参阅[sn.exe (强名称工具)](../../../framework/tools/sn-exe-strong-name-tool.md)。  
  
 如果使用进行`-target:module`编译, 则密钥文件的名称将保存在模块中, 并合并到在使用[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)编译程序集时创建的程序集中。  
  
 还可以将此选项指定为任何 Microsoft 中间语言 (MSIL) 模块的源代码中的自定义特性 (<xref:System.Reflection.AssemblyKeyNameAttribute>)。  
  
 此外，可使用 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 将加密信息传递给编译器。 如果需要部分签名的程序集，请使用 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)。  
  
 有关对程序集进行签名的详细信息, 请参阅[创建和使用具有强名称的程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)。  
  
> [!NOTE]
> 此`-keycontainer`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="example"></a>示例  
 下面的代码编译源文件`Input.vb`并指定密钥容器。  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>请参阅

- [.NET 中的程序集](../../../standard/assembly/index.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
