---
title: 具有 JSON 和 XML 的 AJAX 服务示例
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: 32964c287b0064daf529aa4c1e28f0927d29a6d5
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="ajax-service-with-json-and-xml-sample"></a>具有 JSON 和 XML 的 AJAX 服务示例
此示例演示如何使用 Windows Communication Foundation (WCF) 来创建异步 JavaScript 和 XML (AJAX) 服务返回 JavaScript 对象表示法 (JSON) 或 XML 数据。 可以从 Web 浏览器客户端使用 JavaScript 代码来访问 AJAX 服务。 此示例基于[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例。  
  
 与其他 AJAX 示例不同的是，此示例不使用 ASP.NET AJAX 和 <xref:System.Web.UI.ScriptManager> 控件。 某些其他配置，可以从任何 HTML 页面通过 JavaScript 访问 WCF AJAX 服务与此方案如下所示。 有关使用 ASP.NET AJAX 的 WCF 示例，请参阅[AJAX 示例](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)。  
  
 此示例演示如何在 JSON 和 XML 之间切换操作的响应类型。 无论服务是配置为由 ASP.NET AJAX 访问还是由 HTML/JavaScript 客户端页面访问，此功能均可用。  
  
> [!NOTE]
>  本主题的最后介绍了此示例的设置过程和生成说明。  
  
 为了启用非 ASP.NET AJAX 客户端，请在 .svc 文件中使用 <xref:System.ServiceModel.Activation.WebServiceHostFactory>（而不是 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>）。 <xref:System.ServiceModel.Activation.WebServiceHostFactory> 将 <xref:System.ServiceModel.Description.WebHttpEndpoint> 标准终结点添加到服务中。 相对于.svc 文件中; 的空地址处配置的终结点这意味着服务的地址是http://localhost/ServiceModelSamples/service.svc，除了操作名以外没有其他后缀。  
  
```svc
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
```  
  
 可以使用 Web.config 中的以下节对终结点进行其他配置更改。 如果不需要额外更改，则可以移除该节。  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name="" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 默认数据格式为<xref:System.ServiceModel.Description.WebHttpEndpoint>时的默认数据格式为 XML，<xref:System.ServiceModel.Description.WebScriptEndpoint>为 JSON。 有关详细信息，请参阅[不使用 ASP.NET 创建 WCF AJAX 服务](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)。  
  
 下面的示例中的服务是具有两个操作的标准 WCF 服务。 这两个操作都需要针对 <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> 或 <xref:System.ServiceModel.Web.WebGetAttribute> 属性使用 <xref:System.ServiceModel.Web.WebInvokeAttribute> 正文样式，该样式特定于 `webHttp` 行为，对于 JSON/XML 数据格式开关没有任何影响。  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```

 该操作的响应格式指定为 XML，这是默认值设置为[ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)行为。 但是，最好显式指定响应格式。  
  
 另一个操作使用 `WebInvokeAttribute` 属性并显式指定响应的 JSON（而不是 XML）。  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```

 请注意，在这两种情况下操作将返回一个复杂类型， `MathResult`，这是标准的 WCF 数据协定类型。  
  
 客户端网页 XmlAjaxClientPage.htm 包含 JavaScript 代码调用上面的两个操作之一，当用户单击**执行计算 (返回 JSON)** 或**执行计算 (返回 XML)** 页上的按钮。 用来调用服务的代码将构造 JSON 正文并使用 HTTP POST 发送它。 创建请求手动在 JavaScript 中，与不同[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)的示例，并使用 ASP.NET AJAX 的其他示例。  

```csharp
// Create HTTP request  
var xmlHttp;  
// Request instantiation code omitted…  
// Result handler code omitted…  
  
// Build the operation URL  
var url = "service.svc/ajaxEndpoint/";  
url = url + operation;  
  
// Build the body of the JSON message  
var body = '{"n1":';  
body = body + document.getElementById("num1").value + ',"n2":';  
body = body + document.getElementById("num2").value + '}';  
  
// Send the HTTP request  
xmlHttp.open("POST", url, true);  
xmlHttp.setRequestHeader("Content-type", "application/json");  
xmlHttp.send(body);  
```

 当服务进行响应时，响应将显示出来，而不会在页面上的文本框中进一步执行任何处理。 这是为了进行演示而实现的，您可以直接遵循所使用的 XML 和 JSON 数据格式。  

```javascript
// Create result handler   
xmlHttp.onreadystatechange=function(){  
     if(xmlHttp.readyState == 4){  
          document.getElementById("result").value = xmlHttp.responseText;  
     }  
}  
```

> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  生成解决方案 XmlAjaxService.sln 中所述[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。  
  
3.  导航到http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm（不要打开 XmlAjaxClientPage.htm 浏览器中从项目目录中）。  
  
## <a name="see-also"></a>请参阅  
 [使用 HTTP POST 的 AJAX 服务](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
