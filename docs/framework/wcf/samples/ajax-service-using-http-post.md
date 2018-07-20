---
title: 使用 HTTP POST 的 AJAX 服务
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: f904a26d87a21a931035b45261dbcd970f7d63a1
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804103"
---
# <a name="ajax-service-using-http-post"></a>使用 HTTP POST 的 AJAX 服务
此示例演示如何使用 Windows Communication Foundation (WCF) 来创建[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]使用 HTTP POST 的异步 JavaScript 和 XML (AJAX) 服务。 AJAX 服务是指可以从 Web 浏览器客户端使用基本 JavaScript 代码访问的服务。 此示例基于[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例; 两个样本之间的唯一区别是使用 HTTP POST 而不是 HTTP GET。  
  
 针对与通过 ASP.NET AJAX 一起使用的 AJAX 支持 Windows Communication Foundation (WCF) 中进行了优化`ScriptManager`控件。 有关使用 ASP.NET AJAX 的 WCF 示例，请参阅[Ajax 示例](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)。  
  
> [!NOTE]
>  本主题的最后介绍了此示例的设置过程和生成说明。  
  
 下面的示例中的服务是不包含 AJAX 特定代码的 WCF 服务。  
  
 如果<xref:System.ServiceModel.Web.WebInvokeAttribute>属性应用于某个操作，或<xref:System.ServiceModel.Web.WebGetAttribute>特性未应用，则使用默认的 HTTP 谓词 ("POST")。 POST 请求虽然比 GET 请求更难构造，但它们不会被缓存；当不适宜缓存时，应对所有操作使用 POST 请求。  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 通过使用 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 在服务上创建 AJAX 终结点，就像在基本 AJAX 服务示例中一样。  
  
 与 GET 请求不同的是，不能从浏览器中调用 POST 服务。 例如，导航到 http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 产生错误，因为 POST 服务要求`n1`和`n2`要在消息正文中发送的参数-采用 JSON 格式-，不能在 URL。  
  
 客户端网页 PostAjaxClientPage.aspx 包含 ASP.NET 代码以便在用户单击页面上的操作按钮之一时调用服务。 服务响应中的相同方式为[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例 GET 请求。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  确保你执行的设置说明[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  生成解决方案 PostAjaxService.sln 中所述[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。  
  
3.  导航到 http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx （不要打开 PostAjaxClientPage.aspx 浏览器中从项目目录中）。  
  
## <a name="see-also"></a>请参阅
