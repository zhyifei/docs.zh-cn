---
title: My 对项目类型的依赖方式 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a37bf43096931597278974099becb9be6ae133d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>My 对项目类型的依赖方式 (Visual Basic)
`My`公开特定项目类型所需的那些对象。 例如，`My.Forms`对象是在 Windows 窗体应用程序中可用但在一个控制台应用程序中不可用。 本主题介绍其中`My`对象可在不同项目类型。  
  
## <a name="my-in-windows-applications-and-web-sites"></a>我在 Windows 应用程序和网站  
 `My`公开在当前的项目类型中; 很有用的对象将禁止不适用的对象。 例如下, 图显示`My`Windows 窗体项目中的对象模型。  
  
 ![形状我在 Windows 窗体应用程序中](../../../visual-basic/developing-apps/development-with-my/media/myinwinform.png "MyInWinForm")  
  
 在网站项目中，`My`公开与 Web 开发人员相关的对象 (如`My.Request`和`My.Response`对象) 时禁止显示不相关的对象 (如`My.Forms`对象)。 下图显示`My`网站项目中的对象模型：  
  
 ![形状的我的 Web 应用中](../../../visual-basic/developing-apps/development-with-my/media/myinweb.png "MyInWeb")  
  
## <a name="project-details"></a>项目详细信息  
 下表显示了哪些`My`对象启用默认情况下，为八个项目类型： Windows 应用程序、 类库、 控制台应用程序、 Windows 控件库，Web 控件库、 Windows 服务、 为空和网站。  
  
 有三种版本的`My.Application`对象、 两个版本的`My.Computer`对象，并且两个版本的`My.User`对象; 在表后的批注中给出有关这些版本的详细信息。  
  
|My 对象|Windows 应用程序|类库|控制台应用程序|Windows 控件库|Web 控件库|Windows 服务|空|网站|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**是** <sup>1</sup>|**是** <sup>2</sup>|**是** <sup>3</sup>|**是** <sup>2</sup>|No|**是** <sup>3</sup>|No|No|  
|`My.Computer`|**是** <sup>4</sup>|**是** <sup>4</sup>|**是** <sup>4</sup>|**是** <sup>4</sup>|**是** <sup>5</sup>|**是** <sup>4</sup>|No|**是** <sup>5</sup>|  
|`My.Forms`|**是**|No|No|**是**|No|No|No|No|  
|`My.Log`|No|No|No|No|No|No|No|**是**|  
|`My.Request`|No|No|No|No|No|No|No|**是**|  
|`My.Resources`|**是**|**是**|**是**|**是**|**是**|**是**|No|No|  
|`My.Response`|No|No|No|No|No|No|No|**是**|  
|`My.Settings`|**是**|**是**|**是**|**是**|**是**|**是**|No|No|  
|`My.User`|**是** <sup>6</sup>|**是** <sup>6</sup>|**是** <sup>6</sup>|**是** <sup>6</sup>|**是** <sup>7</sup>|**是** <sup>6</sup>|No|**是** <sup>7</sup>|  
|`My.WebServices`|**是**|**是**|**是**|**是**|**是**|**是**|No|No|  
  
 <sup>1</sup>的 Windows 窗体版本`My.Application`。 派生自控制台版本 （请参阅说明 3）;添加支持与应用程序的 windows 交互，并且提供[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]应用程序模型。  
  
 <sup>2</sup>的库版本`My.Application`。 提供应用程序所需的基本功能： 用于写入应用程序日志，并访问应用程序信息的成员。  
  
 <sup>3</sup>控制台版本`My.Application`。 派生自的库版本 （请参阅备注 2），并将其他成员添加用于访问应用程序的命令行自变量和 ClickOnce 部署信息。  
  
 <sup>4</sup>的 Windows 版本`My.Computer`。 派生自的服务器版本 （请参阅备注 5），并在客户端计算机上，例如键盘、 屏幕和鼠标提供有用的对象的访问权限。  
  
 <sup>5</sup>服务器版本`My.Computer`。 提供计算机的信息，如名称、 访问的时钟和等等的基本信息。  
  
 <sup>6</sup>的 Windows 版本`My.User`。 此对象是与线程的当前标识相关联。  
  
 <sup>7</sup> web 版本的`My.User`。 此对象是与应用程序的当前 HTTP 请求的用户标识相关联。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [My.Forms 对象](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.Request 对象](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [My.Response 对象](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [My.WebServices 对象](../../../visual-basic/language-reference/objects/my-webservices-object.md)
