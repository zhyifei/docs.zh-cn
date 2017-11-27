---
title: /linkresource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e51f844695985485210a1e4bedfef7ac968326c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-visual-basic"></a>/linkresource (Visual Basic)
创建指向托管资源的链接。  
  
## <a name="syntax"></a>语法  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>参数  
 `filename`  
 必需。 要将链接到程序集的资源文件。 如果文件名包含空格，则将名称括在双引号 ("")。  
  
 `identifier`  
 可选。 资源的逻辑名称。 用于加载资源的名称。 默认值是文件的名称。 或者，可以指定文件是否是公用或专用在程序集清单中，例如： `/linkres:filename.res,myname.res,public`。 默认情况下，`filename`在程序集是公共的。  
  
## <a name="remarks"></a>备注  
 `/linkresource`选项不会将资源文件嵌入到输出文件中; 使用`/resource`选项以执行此操作。  
  
 `/linkresource`选项需要一个`/target`选项以外`/target:module`。  
  
 如果`filename`是[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]创建资源文件，例如，通过[Resgen.exe （资源文件生成器）](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4)或在开发环境中，它可以访问其成员保持<xref:System.Resources>命名空间。 （有关详细信息，请参阅 <xref:System.Resources.ResourceManager>。）若要在运行时访问所有其他资源，使用的方法的开头`GetManifestResource`中<xref:System.Reflection.Assembly>类。  
  
 文件名称可以是任何文件格式。 例如，你可能希望生成程序集的本机 DLL 部分，从而可将它安装到全局程序集缓存中，并且可从该程序集中的托管代码访问它。  
  
 `/linkresource` 的缩写形式是 `/linkres`。  
  
> [!NOTE]
>  `/linkresource`选项将不可用从 Visual Studio 开发环境，它可仅编译时从命令行。  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`并链接到资源文件`Rf.resource`。  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
