---
title: -资源 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab5593455546e65bdd760d9e60532031dc1f12a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-resource-visual-basic"></a>-资源 (Visual Basic)
将托管资源嵌入程序集。  
  
## <a name="syntax"></a>语法  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`filename`|必须的。 要嵌入到输出文件中的资源文件的名称。 默认情况下，`filename`在程序集是公共的。 将文件名括在双引号 ("") 如果它包含空格。|  
|`identifier`|可选。 资源; 的逻辑名称用来加载它的名称。 默认值是文件的名称。 或者，你可以指定的资源是公用或专用在程序集清单中，与以下： `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>备注  
 使用`-linkresource`若要将资源链接到程序集，而无需将资源文件放置在输出文件。  
  
 如果`filename`是[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]创建资源文件，例如，通过[Resgen.exe （资源文件生成器）](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4)或在开发环境中，它可以访问其成员保持<xref:System.Resources>命名空间 （请参阅<xref:System.Resources.ResourceManager>有关详细信息)。 若要在运行时访问所有其他资源，请使用以下方法之一： <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>， <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>，或<xref:System.Reflection.Assembly.GetManifestResourceStream%2A>。  
  
 `-resource` 的缩写形式是 `-res`。  
  
 有关如何设置`-resource`在 Visual Studio IDE 中，请参阅[管理应用程序资源 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)。  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`和附加的资源文件`Rf.resource`。  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)  
 [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)  
 [-目标 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
