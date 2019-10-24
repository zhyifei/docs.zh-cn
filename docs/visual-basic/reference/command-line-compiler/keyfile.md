---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 2617c42d7b176806cfac0fc2247760727608261a
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775648"
---
# <a name="-keyfile"></a>-keyfile
指定包含密钥或密钥对的文件从而为程序集赋予强名称。  
  
## <a name="syntax"></a>语法  
  
```console 
-keyfile:file  
```  
  
## <a name="arguments"></a>自变量  
 `file`  
 必须的。 包含密钥的文件。 如果文件名包含空格，则将该名称括在引号（""）中。  
  
## <a name="remarks"></a>备注  
 编译器将公钥插入程序集清单中，然后用私钥对最终程序集进行签名。 若要生成密钥文件，请在命令行键入 `sn -k file`。 有关详细信息，请参阅[sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)。  
  
 如果使用 `-target:module`进行编译，则密钥文件的名称将保存在模块中，并合并到在使用[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)编译程序集时创建的程序集。  
  
 也可以使用 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 将加密信息传递给编译器。 如果需要部分签名的程序集，请使用 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)。  
  
 你还可以将此选项指定为任何 Microsoft 中间语言模块的源代码中的自定义特性（<xref:System.Reflection.AssemblyKeyFileAttribute>）。  
  
 如果在同一编译中同时指定 `-keyfile` 和[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) （通过命令行选项或通过自定义特性），则编译器将首先尝试密钥容器。 如果成功，则使用密钥容器中的信息对程序集签名。 如果编译器没有找到密钥容器，则它会尝试 `-keyfile` 指定的文件。 如果此操作成功，则会用密钥文件中的信息对程序集进行签名，并将密钥信息安装到密钥容器中（类似于 `sn -i`），以便在下一次编译时，密钥容器将有效。  
  
 请注意，密钥文件可能仅包含公钥。  
  
 有关对程序集进行签名的详细信息，请参阅[创建和使用具有强名称的程序集](../../../standard/assembly/create-use-strong-named.md)。  
  
> [!NOTE]
> @No__t_0 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。

## <a name="example"></a>示例

下面的代码 `Input.vb` 编译源文件，并指定一个密钥文件。

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>请参阅

- [.NET 中的程序集](../../../standard/assembly/index.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-reference （Visual Basic）](../../../visual-basic/reference/command-line-compiler/reference.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
