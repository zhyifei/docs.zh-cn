---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 0315645eccdc899ac9cf4d0be105297e1fa2a4c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335485"
---
# <a name="-linkresource-visual-basic"></a>-linkresource （Visual Basic）
创建指向托管资源的链接。  
  
## <a name="syntax"></a>语法  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

或  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>参数  
 `filename`  
 必需。 要链接到程序集的资源文件。 如果文件名包含空格，则将该名称括在引号（""）中。  
  
 `identifier`  
 可选。 资源的逻辑名称。 用于加载资源的名称。 默认值是文件的名称。 您也可以在程序集清单中指定文件是公共的还是私有的，例如： `-linkres:filename.res,myname.res,public`。 默认情况下，`filename` 在程序集中是公共的。  
  
## <a name="remarks"></a>备注  
 `-linkresource` 选项不会将资源文件嵌入到输出文件中;使用 `-resource` 选项来执行此操作。  
  
 `-linkresource` 选项需要 `-target:module`之外的 `-target` 选项之一。  
  
 如果 `filename` 是通过[resgen.exe （资源文件生成器）](../../../framework/tools/resgen-exe-resource-file-generator.md)或在开发环境中创建 .NET Framework 资源文件，则可以使用 <xref:System.Resources> 命名空间中的成员来访问它。 （有关详细信息，请参阅 <xref:System.Resources.ResourceManager>。）若要在运行时访问所有其他资源，请使用 <xref:System.Reflection.Assembly> 类中以 `GetManifestResource` 开头的方法。  
  
 文件名可以是任何文件格式。 例如，你可能希望生成程序集的本机 DLL 部分，从而可将它安装到全局程序集缓存中，并且可从该程序集中的托管代码访问它。  
  
 `-linkresource` 的缩写形式是 `-linkres`。  
  
> [!NOTE]
> `-linkresource` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译 `in.vb` 并链接到资源文件 `rf.resource`。  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)
- [-resource （Visual Basic）](../../../visual-basic/reference/command-line-compiler/resource.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
