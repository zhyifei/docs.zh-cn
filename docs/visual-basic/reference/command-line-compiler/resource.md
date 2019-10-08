---
title: -resource （Visual Basic）
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 5bedc346381f6de293933dce14a8c5c3044b246f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005189"
---
# <a name="-resource-visual-basic"></a>-resource （Visual Basic）
将托管资源嵌入程序集。  
  
## <a name="syntax"></a>语法  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

或  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`filename`|必需。 要嵌入到输出文件中的资源文件的名称。 默认情况下，`filename` 在程序集中是公共的。 如果文件名包含空格，请将文件名用引号（""）引起来。|  
|`identifier`|可选。 资源的逻辑名称;用于加载它的名称。 默认值是文件的名称。 您也可以在程序集清单中指定资源是公共的还是私有的，如下所示： `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>备注  
 使用 `-linkresource` 可将资源链接到程序集，而无需将资源文件放在输出文件中。  
  
 如果 @no__t 0 是创建的 .NET Framework 资源文件（例如，通过[resgen.exe （资源文件生成器）](../../../framework/tools/resgen-exe-resource-file-generator.md)或在开发环境中），则可以使用 <xref:System.Resources> 命名空间中的成员来访问它（有关详细信息，请参阅 <xref:System.Resources.ResourceManager>）。 若要在运行时访问所有其他资源，请使用以下方法之一： <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>、<xref:System.Reflection.Assembly.GetManifestResourceNames%2A> 或 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>。  
  
 `-resource` 的缩写形式是 `-res`。  
  
 有关如何在 Visual Studio IDE 中设置 `-resource` 的信息，请参阅[管理应用程序资源（.net）](/visualstudio/ide/managing-application-resources-dotnet)。  
  
## <a name="example"></a>示例  
 下面的代码编译 `In.vb` 并将资源文件附加 `Rf.resource`。  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource （Visual Basic）](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
