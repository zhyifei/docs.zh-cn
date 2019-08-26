---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 6eb9d50a3ecd80acb0349f1ba315d9cf8ccc6dc2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937242"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
标识用户定义的 Win32 应用程序清单文件要嵌入到项目的可移植可执行 (PE) 文件。  
  
## <a name="syntax"></a>语法  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`fileName`|自定义清单文件的路径。|  
  
## <a name="remarks"></a>备注  
 默认情况下, Visual Basic 编译器嵌入指定请求的 asInvoker 执行级别的应用程序清单。 它在生成可执行文件的同一文件夹中创建清单, 通常在使用 Visual Studio 时是 bin\Debug 或 bin\Release 文件夹。 如果要提供自定义清单 (例如, 若要指定 highestAvailable 或 requireAdministrator 的请求执行级别), 请使用此选项指定文件的名称。  
  
> [!NOTE]
> 此选项和[-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)选项是互斥的。 如果尝试在同一命令行中使用这两个选项, 将会出现生成错误。  
  
 如果应用程序没有用于指定请求执行级别的应用程序清单，将受到 Windows Vista 的用户帐户控制功能下的文件/注册表虚拟化的影响。 有关虚拟化的详细信息，请参阅 [Windows Vista 上的 ClickOnce 部署](/visualstudio/deployment/clickonce-deployment-on-windows-vista)。  
  
 如果满足以下任一条件, 你的应用程序将受到虚拟化的限制:  
  
1. 使用`-nowin32manifest`选项时, 不会在以后的生成步骤中提供清单, 也不会`-win32resource`使用选项在 Windows 资源 (.res) 文件中提供清单。  
  
2. 提供的自定义清单未指定请求执行级别。  
  
 Visual Studio 创建默认 .manifest 文件，并将它与可执行文件一起存储在“调试”和“发布”目录中。 您可以通过在项目设计器中单击 "**应用程序**" 选项卡上的 "**查看 UAC 设置**" 来查看或编辑默认的 app.config 文件。 有关详细信息，请参阅 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)（应用程序页、项目设计器 (Visual Basic)。  
  
 可以通过使用`-nowin32manifest`选项, 将应用程序清单作为自定义后期生成步骤或 Win32 资源文件的一部分提供。 如果希望应用程序受到 Windows Vista 的文件或注册表虚拟化的影响，请使用该选项。 这会阻止编译器在 PE 文件中创建和嵌入默认清单。  
  
## <a name="example"></a>示例  
 下面的示例演示 Visual Basic 编译器插入到 PE 中的默认清单。  
  
> [!NOTE]
> 编译器将标准应用程序名称 MyApplication 插入到清单 XML 中。 这是一种使应用程序可以在 Windows Server 2003 Service Pack 3 上运行的解决方法。  
  
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
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
