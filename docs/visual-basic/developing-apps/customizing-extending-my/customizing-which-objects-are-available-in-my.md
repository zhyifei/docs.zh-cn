---
title: 自定义 My 中可用的对象 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: b06e71784a4d02bcbcd755d14e57ef88c4322f7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>自定义 My 中可用的对象 (Visual Basic)
本主题介绍如何控制哪些`My`通过设置你的项目的情况下启用对象`_MYTYPE`条件编译常量。 Visual Studio 集成开发环境 (IDE) 保留`_MYTYPE`与项目的类型同步的项目的条件编译常量。  
  
## <a name="predefined-mytype-values"></a>预定义的 _MYTYPE 值  
 必须使用`/define`编译器选项来设置`_MYTYPE`条件编译常量。 指定为你自己的值时`_MYTYPE`常量，你必须括起的字符串值中反斜杠/引号 (\\") 序列。 例如，你可以使用：  
  
```  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 下表显示什么`_MYTYPE`条件编译常量设置为几种项目类型。  
  
|项目类型|_MYTYPE 值|  
|------------------|--------------------|  
|类库|"Windows"|  
|控制台应用程序|"控制台"|  
|Web|"Web"|  
|Web 控件库|"WebControl"|  
|Windows 应用程序|"WindowsForms"|  
|Windows 应用程序，使用自定义启动时 `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Windows 控件库|"Windows"|  
|Windows 服务|"控制台"|  
|空|"空"|  
  
> [!NOTE]
>  所有条件编译字符串比较都是区分大小写，而不考虑如何`Option Compare`设置语句。  
  
## <a name="dependent-my-compilation-constants"></a>相关 _MY 编译常数  
 `_MYTYPE`条件编译常量，反过来，控制的其他几个值`_MY`编译常量：  
  
|_MYTYPE|_MYAPPLICATIONTYPE|_MYCOMPUTERTYPE|_MYFORMS|_MYUSERTYPE|_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"控制台"|"控制台"|"Windows"|未定义|"Windows"|true|  
|"Custom"|未定义|未定义|未定义|未定义|未定义|  
|"空"|未定义|未定义|未定义|未定义|未定义|  
|"Web"|未定义|"Web"|false|"Web"|false|  
|"WebControl"|未定义|"Web"|false|"Web"|true|  
|"Windows"或""|"Windows"|"Windows"|未定义|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|true|"Windows"|true|  
|"WindowsFormsWithCustomSubMain"|"控制台"|"Windows"|true|"Windows"|true|  
  
 默认情况下，未定义的条件编译常数解析为`FALSE`。 编译你的项目以重写默认行为时，你可以指定为未定义的常数的值。  
  
> [!NOTE]
>  当`_MYTYPE`设置为"Custom"，该项目包含`My`命名空间，但它不包含的对象。 但是，将设置`_MYTYPE`到"Empty"，则可阻止编译器在添加`My`命名空间及其对象。  
  
 下表介绍的预定义的值的效果`_MY`编译常量。  
  
|返回的常量|含义|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|使`My.Application`，如果常量是"控制台"窗口，"或"WindowsForms":<br /><br /> -"控制台"版本派生自<xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>。 并提供比"Windows"版本较少的成员。<br />-"Windows"版本派生自<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>和具有比"WindowsForms"版本较少的成员。<br />-的版本"WindowsForms"`My.Application`派生自<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>。 如果`TARGET`常量被定义为"winexe"，则该类包括`Sub Main`方法。|  
|`_MYCOMPUTERTYPE`|使`My.Computer`，如果常量是"Web"或"Windows":<br /><br /> -"Web"版本派生自<xref:Microsoft.VisualBasic.Devices.ServerComputer>，并且具有较少的成员，于"Windows"版本。<br />-的版本"Windows"`My.Computer`派生自<xref:Microsoft.VisualBasic.Devices.Computer>。|  
|`_MYFORMS`|使`My.Forms`，如果常量是`TRUE`。|  
|`_MYUSERTYPE`|使`My.User`，如果常量是"Web"或"Windows":<br /><br /> -"Web"版`My.User`与当前 HTTP 请求的用户标识相关联。<br />-的版本"Windows"`My.User`与线程的当前主体相关联。|  
|`_MYWEBSERVICES`|使`My.WebServices`，如果常量是`TRUE`。|  
|`_MYTYPE`|使`My.Log`， `My.Request`，和`My.Response`，如果常量是"Web"。|  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.Logging.Log>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [My 对项目类型的依赖方式](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)  
 [My.Forms 对象](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.Request 对象](../../../visual-basic/language-reference/objects/my-request-object.md)  
 [My.Response 对象](../../../visual-basic/language-reference/objects/my-response-object.md)  
 [My.WebServices 对象](../../../visual-basic/language-reference/objects/my-webservices-object.md)
