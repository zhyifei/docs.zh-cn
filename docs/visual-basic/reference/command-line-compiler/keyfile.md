---
title: /keyfile
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b7f41b659399ae5a12663d4e359c02606bb6f952
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="keyfile"></a>/keyfile
指定包含密钥或密钥对的文件从而为程序集赋予强名称。  
  
## <a name="syntax"></a>语法  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>参数  
 `file`  
 必需。 包含密钥的文件。 如果文件名包含空格，则将名称括在双引号 ("")。  
  
## <a name="remarks"></a>备注  
 编译器将公钥插入程序集清单，然后使用私钥进行签名最终的程序集。 若要生成的密钥文件，请键入`sn -k file`在命令行。 有关详细信息，请参阅 [Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23)。  
  
 如果使用编译`/target:module`，密钥文件的名称保存在模块中，并合并到编译为程序集时创建的程序集[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)。  
  
 也可以使用 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 将加密信息传递给编译器。 如果需要部分签名的程序集，请使用 [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)。  
  
 你还可以通过以下方式指定此选项的自定义特性 (<xref:System.Reflection.AssemblyKeyFileAttribute>) 为任何 Microsoft 中间语言模块的源代码中。  
  
 两者`/keyfile`和[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) （通过命令行选项或通过自定义特性） 中指定同一编译中，编译器将先尝试密钥容器。 如果成功，则使用密钥容器中的信息对程序集签名。 如果编译器没有找到密钥容器，它将尝试使用指定的文件`/keyfile`。 如果此操作成功，程序集签名的密钥文件中的信息的密钥信息安装到密钥容器中 (类似于`sn -i`)，以便在下一步的编译中，密钥容器才有效。  
  
 请注意，密钥文件可能仅包含公钥。  
  
 请参阅[创建和使用具有强名称程序集](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)有关程序集进行签名的详细信息。  
  
> [!NOTE]
>  `/keyfile`选项不是可从[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译源文件`Input.vb`，并指定密钥文件。  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
