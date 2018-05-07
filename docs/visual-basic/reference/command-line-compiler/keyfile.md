---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 12895e4a18203a0d6c409a3b2117abbc59fab7a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-keyfile"></a>-keyfile
指定包含密钥或密钥对的文件从而为程序集赋予强名称。  
  
## <a name="syntax"></a>语法  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a>自变量  
 `file`  
 必须的。 包含密钥的文件。 如果文件名包含空格，则将名称括在双引号 ("")。  
  
## <a name="remarks"></a>备注  
 编译器将公钥插入程序集清单，然后使用私钥进行签名最终的程序集。 若要生成的密钥文件，请键入`sn -k file`在命令行。 有关详细信息，请参阅 [Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md))。  
  
 如果使用编译`-target:module`，密钥文件的名称保存在模块中，并合并到编译为程序集时创建的程序集[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)。  
  
 也可以使用 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 将加密信息传递给编译器。 如果需要部分签名的程序集，请使用 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)。  
  
 你还可以通过以下方式指定此选项的自定义特性 (<xref:System.Reflection.AssemblyKeyFileAttribute>) 为任何 Microsoft 中间语言模块的源代码中。  
  
 两者`-keyfile`和[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) （通过命令行选项或通过自定义特性） 中指定同一编译中，编译器将先尝试密钥容器。 如果成功，则使用密钥容器中的信息对程序集签名。 如果编译器没有找到密钥容器，它将尝试使用指定的文件`-keyfile`。 如果此操作成功，程序集签名的密钥文件中的信息的密钥信息安装到密钥容器中 (类似于`sn -i`)，以便在下一步的编译中，密钥容器才有效。  
  
 请注意，密钥文件可能仅包含公钥。  
  
 请参阅[创建和使用具有强名称程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)有关程序集进行签名的详细信息。  
  
> [!NOTE]
>  `-keyfile`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译源文件`Input.vb`，并指定密钥文件。  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-参考 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
