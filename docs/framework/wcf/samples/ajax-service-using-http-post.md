---
title: "使用 HTTP POST 的 AJAX 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 004bb41ad1662ddd6518c25acc1cac36dda3339c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ajax-service-using-http-post"></a>使用 HTTP POST 的 AJAX 服务
此示例演示如何使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 创建使用 HTTP POST 的 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 异步 JavaScript 和 XML (AJAX) 服务。 AJAX 服务是指可以从 Web 浏览器客户端使用基本 JavaScript 代码访问的服务。 此示例基于[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例; 两个样本之间的唯一区别是使用 HTTP POST 而不是 HTTP GET。  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 对 AJAX 的支持经过了优化，以便通过 `ScriptManager` 控件与 ASP.NET AJAX 一起使用。 有关使用示例[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]与 ASP.NET AJAX，请参阅[Ajax 示例](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)。  
  
> [!NOTE]
>  本主题的最后介绍了此示例的设置过程和生成说明。  
  
 以下示例中的服务是不包含 AJAX 特定代码的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。  
  
 如果<xref:System.ServiceModel.Web.WebInvokeAttribute>属性应用于某个操作，或<xref:System.ServiceModel.Web.WebGetAttribute>特性未应用，则使用默认的 HTTP 谓词 ("POST")。 POST 请求虽然比 GET 请求更难构造，但它们不会被缓存；当不适宜缓存时，应对所有操作使用 POST 请求。  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
```  
  
 通过使用 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 在服务上创建 AJAX 终结点，就像在基本 AJAX 服务示例中一样。  
  
 与 GET 请求不同的是，不能从浏览器中调用 POST 服务。 例如，导航到 http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 将导致出错，因为 POST 服务要求在消息正文中（而不是在 URL 中）采用 JSON 格式发送 `n1` 和 `n2` 参数。  
  
 客户端网页 PostAjaxClientPage.aspx 包含 ASP.NET 代码以便在用户单击页面上的操作按钮之一时调用服务。 服务响应中的相同方式为[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例 GET 请求。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  确保你执行的设置说明[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  生成解决方案 PostAjaxService.sln 中所述[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。  
  
3.  定位到 http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx（不要在浏览器中从项目目录中打开 PostAjaxClientPage.aspx）。  
  
## <a name="see-also"></a>另请参阅
