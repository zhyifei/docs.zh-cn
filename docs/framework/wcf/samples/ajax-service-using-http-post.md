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
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="714f5-102">使用 HTTP POST 的 AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="714f5-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="714f5-103">此示例演示如何使用 Windows Communication Foundation (WCF) 来创建[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]使用 HTTP POST 的异步 JavaScript 和 XML (AJAX) 服务。</span><span class="sxs-lookup"><span data-stu-id="714f5-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="714f5-104">AJAX 服务是指可以从 Web 浏览器客户端使用基本 JavaScript 代码访问的服务。</span><span class="sxs-lookup"><span data-stu-id="714f5-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="714f5-105">此示例基于[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例; 两个样本之间的唯一区别是使用 HTTP POST 而不是 HTTP GET。</span><span class="sxs-lookup"><span data-stu-id="714f5-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="714f5-106">针对与通过 ASP.NET AJAX 一起使用的 AJAX 支持 Windows Communication Foundation (WCF) 中进行了优化`ScriptManager`控件。</span><span class="sxs-lookup"><span data-stu-id="714f5-106">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="714f5-107">有关使用 ASP.NET AJAX 的 WCF 示例，请参阅[Ajax 示例](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)。</span><span class="sxs-lookup"><span data-stu-id="714f5-107">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="714f5-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="714f5-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="714f5-109">下面的示例中的服务是不包含 AJAX 特定代码的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="714f5-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="714f5-110">如果<xref:System.ServiceModel.Web.WebInvokeAttribute>属性应用于某个操作，或<xref:System.ServiceModel.Web.WebGetAttribute>特性未应用，则使用默认的 HTTP 谓词 ("POST")。</span><span class="sxs-lookup"><span data-stu-id="714f5-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="714f5-111">POST 请求虽然比 GET 请求更难构造，但它们不会被缓存；当不适宜缓存时，应对所有操作使用 POST 请求。</span><span class="sxs-lookup"><span data-stu-id="714f5-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 <span data-ttu-id="714f5-112">通过使用 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 在服务上创建 AJAX 终结点，就像在基本 AJAX 服务示例中一样。</span><span class="sxs-lookup"><span data-stu-id="714f5-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="714f5-113">与 GET 请求不同的是，不能从浏览器中调用 POST 服务。</span><span class="sxs-lookup"><span data-stu-id="714f5-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="714f5-114">例如，导航到 http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 产生错误，因为 POST 服务要求`n1`和`n2`要在消息正文中发送的参数-采用 JSON 格式-，不能在 URL。</span><span class="sxs-lookup"><span data-stu-id="714f5-114">For example, navigating to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body—in the JSON format—and not in the URL.</span></span>  
  
 <span data-ttu-id="714f5-115">客户端网页 PostAjaxClientPage.aspx 包含 ASP.NET 代码以便在用户单击页面上的操作按钮之一时调用服务。</span><span class="sxs-lookup"><span data-stu-id="714f5-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="714f5-116">服务响应中的相同方式为[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例 GET 请求。</span><span class="sxs-lookup"><span data-stu-id="714f5-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="714f5-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="714f5-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="714f5-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="714f5-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="714f5-119">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="714f5-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="714f5-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="714f5-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="714f5-121">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="714f5-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="714f5-122">确保你执行的设置说明[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="714f5-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="714f5-123">生成解决方案 PostAjaxService.sln 中所述[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="714f5-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="714f5-124">导航到 http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx （不要打开 PostAjaxClientPage.aspx 浏览器中从项目目录中）。</span><span class="sxs-lookup"><span data-stu-id="714f5-124">Navigate to http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714f5-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="714f5-125">See Also</span></span>
