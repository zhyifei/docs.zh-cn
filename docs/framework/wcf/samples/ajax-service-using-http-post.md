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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59195742fb799e9bc26034d5689f0be196e5362d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="205be-102">使用 HTTP POST 的 AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="205be-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="205be-103">此示例演示如何使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 创建使用 HTTP POST 的 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 异步 JavaScript 和 XML (AJAX) 服务。</span><span class="sxs-lookup"><span data-stu-id="205be-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="205be-104">AJAX 服务是指可以从 Web 浏览器客户端使用基本 JavaScript 代码访问的服务。</span><span class="sxs-lookup"><span data-stu-id="205be-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="205be-105">此示例基于[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例; 两个样本之间的唯一区别是使用 HTTP POST 而不是 HTTP GET。</span><span class="sxs-lookup"><span data-stu-id="205be-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="205be-106">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 对 AJAX 的支持经过了优化，以便通过 `ScriptManager` 控件与 ASP.NET AJAX 一起使用。</span><span class="sxs-lookup"><span data-stu-id="205be-106">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="205be-107">有关使用示例[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]与 ASP.NET AJAX，请参阅[Ajax 示例](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)。</span><span class="sxs-lookup"><span data-stu-id="205be-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="205be-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="205be-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="205be-109">以下示例中的服务是不包含 AJAX 特定代码的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="205be-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="205be-110">如果<xref:System.ServiceModel.Web.WebInvokeAttribute>属性应用于某个操作，或<xref:System.ServiceModel.Web.WebGetAttribute>特性未应用，则使用默认的 HTTP 谓词 ("POST")。</span><span class="sxs-lookup"><span data-stu-id="205be-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="205be-111">POST 请求虽然比 GET 请求更难构造，但它们不会被缓存；当不适宜缓存时，应对所有操作使用 POST 请求。</span><span class="sxs-lookup"><span data-stu-id="205be-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
```  
  
 <span data-ttu-id="205be-112">通过使用 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 在服务上创建 AJAX 终结点，就像在基本 AJAX 服务示例中一样。</span><span class="sxs-lookup"><span data-stu-id="205be-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="205be-113">与 GET 请求不同的是，不能从浏览器中调用 POST 服务。</span><span class="sxs-lookup"><span data-stu-id="205be-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="205be-114">例如，导航到 http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 将导致出错，因为 POST 服务要求在消息正文中（而不是在 URL 中）采用 JSON 格式发送 `n1` 和 `n2` 参数。</span><span class="sxs-lookup"><span data-stu-id="205be-114">For example, navigating to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body—in the JSON format—and not in the URL.</span></span>  
  
 <span data-ttu-id="205be-115">客户端网页 PostAjaxClientPage.aspx 包含 ASP.NET 代码以便在用户单击页面上的操作按钮之一时调用服务。</span><span class="sxs-lookup"><span data-stu-id="205be-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="205be-116">服务响应中的相同方式为[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例 GET 请求。</span><span class="sxs-lookup"><span data-stu-id="205be-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="205be-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="205be-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="205be-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="205be-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="205be-119">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="205be-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="205be-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="205be-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="205be-121">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="205be-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="205be-122">确保你执行的设置说明[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="205be-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="205be-123">生成解决方案 PostAjaxService.sln 中所述[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="205be-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="205be-124">定位到 http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx（不要在浏览器中从项目目录中打开 PostAjaxClientPage.aspx）。</span><span class="sxs-lookup"><span data-stu-id="205be-124">Navigate to http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="205be-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="205be-125">See Also</span></span>
