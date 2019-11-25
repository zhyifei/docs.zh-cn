---
title: My.WebServices 对象
ms.date: 07/20/2015
f1_keywords:
- My.WebServices
- My.MyProject.WebServices
helpviewer_keywords:
- My.WebServices object
ms.assetid: f188dc05-2c75-41b6-bb68-122d1c3110a2
ms.openlocfilehash: 290d025985663bc45fe605a2e9904fc90fb2bc63
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350338"
---
# <a name="mywebservices-object"></a>My.WebServices 对象
Provides properties for creating and accessing a single instance of each XML Web service referenced by the current project.  
  
## <a name="remarks"></a>备注  
 `My.WebServices` 对象提供当前项目所引用的每个 Web 服务的实例。 按需实例化每个实例。 可以通过 `My.WebServices` 对象的属性访问这些 Web 服务。 该属性的名称与该属性所访问的 Web 服务的名称相同。 任何自 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> 继承的类均为 Web 服务。 For information about adding Web services to a project, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 The `My.WebServices` object exposes only the Web services associated with the current project. It does not provide access to Web services declared in referenced DLLs. To access a Web service that a DLL provides, you must use the qualified name of the Web service, in the form *DllName*.*WebServiceName*. For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 The object and its properties are not available for Web applications.  
  
## <a name="properties"></a>属性  
 Each property of the `My.WebServices` object provides access to an instance of a Web service referenced by the current project. The name of the property is the same as the name of the Web service that the property accesses, and the property type is the same as the Web service's type.  
  
> [!NOTE]
> If there is a name collision, the property name for accessing a Web service is *RootNamespace*_*Namespace*\_*ServiceName*. For example, consider two Web services named `Service1`. If one of these services is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that service by using `My.WebServices.WindowsApplication1_Namespace1_Service1`.  
  
 When you first access one of the `My.WebServices` object's properties, it creates a new instance of the Web service and stores it. Subsequent accesses of that property return that instance of the Web service.  
  
 You can dispose of a Web service by assigning `Nothing` to the property for that Web service. The property setter assigns `Nothing` to the stored value. If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.  
  
 You can test whether a property of the `My.WebServices` object stores an instance of the Web service by using the `Is` or `IsNot` operator. You can use those operators to check if the value of the property is `Nothing`.  
  
> [!NOTE]
> Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison. However, if the property currently stores `Nothing`, the property creates a new instance of the Web service and then returns that instance. However, the Visual Basic compiler treats the properties of the `My.WebServices` object specially, and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.  
  
## <a name="example"></a>示例  
 This example calls the `FahrenheitToCelsius` method of the `TemperatureConverter` XML Web service, and returns the result.  
  
 [!code-vb[VbVbalrMyWebService#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWebService/VB/Form1.vb#1)]  
  
 For this example to work, your project must reference a Web service named `Converter`, and that Web service must expose the `ConvertTemperature` method. For more information, see [Accessing Application Web Services](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md).  
  
 This code does not work in a Web application project.  
  
## <a name="requirements"></a>要求  
  
### <a name="availability-by-project-type"></a>Availability by Project Type  
  
|项目类型|可用|  
|---|---|  
|Windows 应用程序|**是**|  
|类库|**是**|  
|控制台应用程序|**是**|  
|Windows Control Library|**是**|  
|Web Control Library|**是**|  
|Windows 服务|**是**|  
|网站|No|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>
- <xref:System.ArgumentException>
- [访问应用程序 Web 服务](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
