---
title: /win32resource
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d839b1100b1ae76fbd4653ebc60c79db11b77685
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="win32resource"></a>/win32resource
在输出文件中插入 Win32 资源文件。  
  
## <a name="syntax"></a>语法  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a>参数  
 `filename`  
 要添加到输出文件的资源文件的名称。 将文件名括在双引号 ("") 如果它包含空格。  
  
## <a name="remarks"></a>备注  
 你可以使用 Microsoft Windows 资源编译器 (RC) 创建的 Win32 资源文件。  
  
 Win32 资源可以包含版本或位图 （图标） 信息，以帮助识别你的应用程序中**文件资源管理器**。 如果不指定`/win32resource`，编译器将生成基于程序集版本的版本信息。 `/win32resource`和`/win32icon`选项互斥。  
  
 请参阅[/linkresource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/linkresource.md)引用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件，或[/resource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/resource.md)附加[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件。  
  
> [!NOTE]
>  `/win32resource`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`，并将附加的 Win32 资源文件， `Rf.res`:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
