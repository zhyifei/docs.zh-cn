---
title: 使用 HTTP POST 的 AJAX 服务
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: c102d9d403cefb1bf3d4ab75859a81172895c2e0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394910"
---
# <a name="ajax-service-using-http-post"></a>使用 HTTP POST 的 AJAX 服务
此示例演示如何使用 Windows Communication Foundation (WCF) 创建[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]异步 JavaScript 和 XML (AJAX) 服务使用 HTTP POST。 AJAX 服务是指可以从 Web 浏览器客户端使用基本 JavaScript 代码访问的服务。 此示例是基于[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例; 两个示例之间的唯一区别是使用 HTTP POST 而不是 HTTP GET。  
  
 AJAX 支持 Windows Communication Foundation (WCF) 中进行了优化以用于通过 ASP.NET AJAX`ScriptManager`控件。 使用 ASP.NET AJAX 使用 WCF 的示例，请参阅[Ajax 示例](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)。  
  
> [!NOTE]
>  本主题的最后介绍了此示例的设置过程和生成说明。  
  
 下面的示例中的服务是无代码的特定于 AJAX 的 WCF 服务。  
  
 如果<xref:System.ServiceModel.Web.WebInvokeAttribute>特性应用于某个操作，或<xref:System.ServiceModel.Web.WebGetAttribute>特性未应用，则使用默认的 HTTP 谓词 ("POST")。 POST 请求虽然比 GET 请求更难构造，但它们不会被缓存；当不适宜缓存时，应对所有操作使用 POST 请求。  

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
  
 客户端网页 PostAjaxClientPage.aspx 包含 ASP.NET 代码以便在用户单击页面上的操作按钮之一时调用服务。 在服务响应中相同的方式[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例，使用 GET 请求。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  确保执行设置说明[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  如中所述生成解决方案 PostAjaxService.sln[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。  
  
3.  导航到 http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx （不要打开 PostAjaxClientPage.aspx 浏览器中从项目目录中）。  
  
## <a name="see-also"></a>请参阅
