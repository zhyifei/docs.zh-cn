---
title: /win32manifest (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a46641181c3ff66882468f8372bb97c3a49a8462
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="win32manifest-visual-basic"></a>/win32manifest (Visual Basic)
标识用户定义的 Win32 应用程序清单文件要嵌入到项目的可移植可执行 (PE) 文件。  
  
## <a name="syntax"></a>语法  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`fileName`|自定义清单文件的路径。|  
  
## <a name="remarks"></a>备注  
 默认情况下，Visual Basic 编译器将嵌入指定 asInvoker 的请求的执行级别的应用程序清单。 它在其中可执行文件的生成，通常的 bin\Debug 或 bin\Release 文件夹时使用 Visual Studio 的相同文件夹中创建清单。 如果你想要提供自定义清单，例如，若要指定请求的执行级别的 highestAvailable 或 requireAdministrator，使用此选项以指定文件的名称。  
  
> [!NOTE]
>  此选项与[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)选项互斥。 如果你尝试在相同的命令行中使用这两个选项，则会生成错误。  
  
 如果应用程序没有用于指定请求执行级别的应用程序清单，将受到 Windows Vista 的用户帐户控制功能下的文件/注册表虚拟化的影响。 有关虚拟化的详细信息，请参阅[ClickOnce 部署在 Windows Vista 上](/visualstudio/deployment/clickonce-deployment-on-windows-vista)。  
  
 如果以下条件之一为 true，你的应用程序都将遵循虚拟化：  
  
1.  你使用`/nowin32manifest`选项，你不提供清单中的更高版本的生成步骤或 Windows 资源 (.res) 文件的一部分使用`/win32resource`选项。  
  
2.  提供的自定义清单未指定请求执行级别。  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 创建默认的 .manifest 文件，并将该文件与可执行文件一起存储在 debug 和 release 目录中。 你可以查看或通过单击编辑默认应用程序清单文件**视图 UAC 设置**上**应用程序**项目设计器中的选项卡。 有关详细信息，请参阅 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)（应用程序页、项目设计器 (Visual Basic)。  
  
 你可以提供应用程序清单作为自定义的生成后步骤或 Win32 资源文件的一部分使用`/nowin32manifest`选项。 如果希望应用程序受到 Windows Vista 的文件或注册表虚拟化的影响，请使用该选项。 这将使编译器无法创建和嵌入在 PE 文件中的默认清单。  
  
## <a name="example"></a>示例  
 下面的示例演示了 Visual Basic 编译器将插入 PE 默认清单。  
  
> [!NOTE]
>  编译器将插入清单 XML 的标准应用程序名称 MyApplication.app。 这是一种使应用程序可以在 Windows Server 2003 Service Pack 3 上运行的解决方法。  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
