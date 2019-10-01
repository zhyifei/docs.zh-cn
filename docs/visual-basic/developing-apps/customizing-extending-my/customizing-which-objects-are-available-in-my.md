---
title: 自定义 My 中可用的对象 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: caddad463f7c525c8b715d70f49bf8bebcc7cfbd
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701266"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>自定义 My 中可用的对象 (Visual Basic)

本主题介绍如何通过设置项目的 @no__t 条件编译常量来控制启用了哪些 @no__t 的对象。 Visual Studio 集成开发环境（IDE）为与项目的类型同步的项目保留 @no__t 的条件编译常量。  
  
## <a name="predefined-_mytype-values"></a>预定义的 @no__t 0MYTYPE 值  

必须使用 `/define` 编译器选项来设置 @no__t 条件编译常量。 为 `_MYTYPE` 常量指定自己的值时，必须将字符串值用反斜杠/引号（\\ "）序列引起来。 例如，可以使用：  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 下表显示了为多个项目类型设置为的 @no__t 0 条件编译常量。  
  
|项目类型|\_MYTYPE 值|  
|------------------|--------------------|  
|类库|Windows|  
|控制台应用程序|控制台|  
|Web|站点|  
|Web 控件库|WebControl|  
|Windows 应用程序|WindowsForms|  
|Windows 应用程序（从自定义 @no__t|"WindowsFormsWithCustomSubMain"|  
|Windows 控件库|Windows|  
|Windows 服务|控制台|  
|空|空白处|  
  
> [!NOTE]
> 不管 `Option Compare` 语句如何设置，所有条件编译字符串比较均区分大小写。  
  
## <a name="dependent-_my-compilation-constants"></a>从属 @no__t 0MY 编译常量  

@No__t 的条件编译常量又控制多个其他 @no__t 的编译常量的值：  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|控制台|控制台|Windows|未定义|Windows|TRUE|  
|客户|未定义|未定义|未定义|未定义|未定义|  
|空白处|未定义|未定义|未定义|未定义|未定义|  
|站点|未定义|站点|FALSE|站点|FALSE|  
|WebControl|未定义|站点|FALSE|站点|TRUE|  
|"Windows" 或 ""|Windows|Windows|未定义|Windows|TRUE|  
|WindowsForms|WindowsForms|Windows|TRUE|Windows|TRUE|  
|"WindowsFormsWithCustomSubMain"|控制台|Windows|TRUE|Windows|TRUE|  
  
 默认情况下，未定义的条件编译常量解析为 `FALSE`。 在编译项目时，可以指定未定义的常量的值，以重写默认行为。  
  
> [!NOTE]
> 如果 @no__t 设置为 "Custom"，则项目将包含 @no__t 命名空间，但不包含任何对象。 但是，将 @no__t 设置为 "Empty" 可阻止编译器添加 @no__t 命名空间及其对象。  
  
 下表描述了 `_MY` 编译常量的预定义值的效果。  
  
|返回的常量|含义|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|如果常量为 "Console"、"Windows" 或 "WindowsForms"，则启用 `My.Application`：<br /><br /> -"控制台" 版本派生自 <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>。 和具有比 "Windows" 版本少的成员。<br />-"Windows" 版本是从 @no__t 旁1/-0 派生的，其成员少于 "WindowsForms" 版本。<br />-@No__t 的 "WindowsForms" 版本从 @no__t 派生。 如果 @no__t 0 常量定义为 "winexe"，则类包含 @no__t 1 方法。|  
|`_MYCOMPUTERTYPE`|如果常量为 "Web" 或 "Windows"，则启用 `My.Computer`：<br /><br /> -"Web" 版本派生自 <xref:Microsoft.VisualBasic.Devices.ServerComputer>，其成员少于 "Windows" 版本。<br />-@No__t 的 "Windows" 版本从 @no__t 派生。|  
|`_MYFORMS`|如果常量 @no__t 为-1，则启用 `My.Forms`。|  
|`_MYUSERTYPE`|如果常量为 "Web" 或 "Windows"，则启用 `My.User`：<br /><br /> -@No__t 的 "Web" 版本与当前 HTTP 请求的用户标识相关联。<br />-@No__t 的 "Windows" 版本与线程的当前主体关联。|  
|`_MYWEBSERVICES`|如果常量 @no__t 为-1，则启用 `My.WebServices`。|  
|`_MYTYPE`|如果常量为 "Web"，则启用 `My.Log`、`My.Request` 和 `My.Response`。|  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [My 对项目类型的依赖方式](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [/define （Visual Basic）](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms 对象](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request 对象](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response 对象](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices 对象](../../../visual-basic/language-reference/objects/my-webservices-object.md)
