---
title: My.WebServices 对象
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9f2c4017a1df8059f2cc57e7c30a96c474cfda0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mywebservices-object"></a>My.WebServices 对象
提供用于创建和访问当前的项目所引用的每个 XML Web 服务的单个实例的属性。  
  
## <a name="remarks"></a>备注  
 `My.WebServices` 对象提供当前项目所引用的每个 Web 服务的实例。 按需实例化每个实例。 可以通过 `My.WebServices` 对象的属性访问这些 Web 服务。 该属性的名称与该属性所访问的 Web 服务的名称相同。 任何自 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> 继承的类均为 Web 服务。 有关将 Web 服务添加到项目的信息，请参阅[访问应用程序 Web 服务](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)。  
  
 `My.WebServices`对象公开仅与当前项目关联的 Web 服务。 它不提供对 Web 服务在被引用的 Dll 中声明的访问。 若要访问 DLL 提供的 Web 服务，必须使用 Web 服务的限定的名称的形式*dll 名称*。*WebServiceName*。 有关详细信息，请参阅[访问应用程序 Web 服务](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)。  
  
 对象和其属性将不可用的 Web 应用程序。  
  
## <a name="properties"></a>属性  
 每个属性`My.WebServices`对象提供访问的 Web 服务的当前项目所引用的实例。 属性的名称属性访问时，Web 服务的名称相同，因此该属性类型是 Web 服务的类型相同。  
  
> [!NOTE]
>  如果没有名称冲突，访问 Web 服务的属性名称是*RootNamespace*_*Namespace*\_*ServiceName*。 例如，考虑名为的两个 Web 服务`Service1`。 如果这些服务之一是中的根命名空间`WindowsApplication1`和命名空间中`Namespace1`，你将通过使用访问该服务`My.WebServices.WindowsApplication1_Namespace1_Service1`。  
  
 当首次访问之一`My.WebServices`对象的属性，它创建的 Web 服务的新实例并将其存储。 该属性的后续访问返回 Web 服务的该的实例。  
  
 您可以通过分配释放的 Web 服务`Nothing`到该 Web 服务的属性。 属性 setter 将分配`Nothing`与存储的值。 如果不将任何值赋`Nothing`setter 的属性，将引发<xref:System.ArgumentException>异常。  
  
 你可以测试的属性是否`My.WebServices`对象通过使用存储的 Web 服务实例`Is`或`IsNot`运算符。 你可以使用这些运算符检查属性的值是否为`Nothing`。  
  
> [!NOTE]
>  通常情况下，`Is`或`IsNot`运算符具有要读取的属性进行比较的值。 但是，如果该属性当前存储`Nothing`，属性创建 Web 服务的新实例，然后返回该实例。 但是，Visual Basic 编译器处理的属性`My.WebServices`专门，对象，并允许`Is`或`IsNot`运算符检查而不改变其值的属性的状态。  
  
## <a name="example"></a>示例  
 此示例调用`FahrenheitToCelsius`方法`TemperatureConverter`XML Web 服务，并返回结果。  
  
 [!code-vb[VbVbalrMyWebService#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-webservices-object_1.vb)]  
  
 为此示例正常工作，你的项目必须引用一个名为的 Web 服务`Converter`，并且该 Web 服务必须公开`ConvertTemperature`方法。 有关详细信息，请参阅[访问应用程序 Web 服务](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)。  
  
 此代码不会在 Web 应用程序项目中无效。  
  
## <a name="requirements"></a>要求  
  
### <a name="availability-by-project-type"></a>项目类型的可用性  
  
|项目类型|可用|  
|---|---|  
|Windows 应用程序|**是**|  
|类库|**是**|  
|控制台应用程序|**是**|  
|Windows 控件库|**是**|  
|Web 控件库|**是**|  
|Windows 服务|**是**|  
|网站|No|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>  
 <xref:System.ArgumentException>  
 [访问应用程序 Web 服务](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
