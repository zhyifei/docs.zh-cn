---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266737"
---
# <a name="-keyfile"></a>-keyfile
指定包含密钥或密钥对的文件从而为程序集赋予强名称。  
  
## <a name="syntax"></a>语法  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>参数  
 `file`  
 必需。 包含密钥的文件。 如果文件名包含空格，则用引号 （""） 括上名称。  
  
## <a name="remarks"></a>备注  
 编译器将公钥插入程序集清单，然后使用私钥对最终程序集进行签名。 若要生成密钥文件，请在命令行键入 `sn -k file`。 有关详细信息，请参阅[Sn.exe（强名称工具）。](../../../framework/tools/sn-exe-strong-name-tool.md)  
  
 如果使用 编译，`-target:module`则密钥文件的名称将包含在模块中，并合并[到编译程序集](../../../visual-basic/reference/command-line-compiler/addmodule.md)时创建的程序集中，  
  
 您还可以使用[-key 容器](../../../visual-basic/reference/command-line-compiler/keycontainer.md)将加密信息传递给编译器。 如果需要部分签名的程序集，请使用[延迟符号](../../../visual-basic/reference/command-line-compiler/delaysign.md)。  
  
 您还可以在任何 Microsoft 中间语言模块的源代码中<xref:System.Reflection.AssemblyKeyFileAttribute>指定此选项为自定义属性 （ ） 。  
  
 如果在同`-keyfile`一编译中指定和[-key 容器](../../../visual-basic/reference/command-line-compiler/keycontainer.md)（通过命令行选项或自定义属性），编译器首先尝试密钥容器。 如果成功，则使用密钥容器中的信息对程序集签名。 如果编译器找不到密钥容器，它将尝试使用`-keyfile`指定的文件。 如果成功，程序集将使用密钥文件中的信息进行签名，并且密钥信息安装在密钥容器中（类似于`sn -i`），以便在下一次编译时密钥容器将有效。  
  
 请注意，密钥文件可能仅包含公钥。  
  
 有关对程序集进行签名的详细信息，请参阅[创建和使用强名称程序集](../../../standard/assembly/create-use-strong-named.md)。  
  
> [!NOTE]
> 该`-keyfile`选项在可视化工作室开发环境中不可用;因此，该选项在可视化工作室开发环境中不可用。它仅在从命令行编译时可用。

## <a name="example"></a>示例

以下代码编译源文件`Input.vb`并指定密钥文件。

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>另请参阅

- [.NET 中的程序集](../../../standard/assembly/index.md)
- [可视化基本命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-参考（视觉基础）](../../../visual-basic/reference/command-line-compiler/reference.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
