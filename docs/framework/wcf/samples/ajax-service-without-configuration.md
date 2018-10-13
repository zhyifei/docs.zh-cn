---
title: 无配置的 AJAX 服务
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 60b61a26574764f0f2ea4ca834c5ba92b49a043d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2018
ms.locfileid: "49308369"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="2ac86-102">无配置的 AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="2ac86-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="2ac86-103">此示例演示如何使用 Windows Communication Foundation (WCF) 来创建基本的 ASP.NET 异步 JavaScript 和 XML (AJAX) 服务 （使用从 Web 浏览器客户端的 JavaScript 代码可以访问的服务），而无需使用任何配置设置。</span><span class="sxs-lookup"><span data-stu-id="2ac86-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="2ac86-104">该服务在 .svc 文件中使用特殊语法来自动启用 AJAX 终结点。</span><span class="sxs-lookup"><span data-stu-id="2ac86-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="2ac86-105">WCF 中的 AJAX 支持适用于与通过 ASP.NET AJAX 一起使用`ScriptManager`控件。</span><span class="sxs-lookup"><span data-stu-id="2ac86-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="2ac86-106">使用 ASP.NET AJAX 使用 WCF 的示例，请参阅[Ajax 示例](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)。</span><span class="sxs-lookup"><span data-stu-id="2ac86-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ac86-107">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="2ac86-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2ac86-108">此示例是基于使用 HTTP POST 的 AJAX 服务生成的。</span><span class="sxs-lookup"><span data-stu-id="2ac86-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="2ac86-109">如中所述[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例中，<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>用于承载服务。</span><span class="sxs-lookup"><span data-stu-id="2ac86-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <span data-ttu-id="2ac86-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 自动将 <xref:System.ServiceModel.Description.WebScriptEndpoint> 添加到服务。</span><span class="sxs-lookup"><span data-stu-id="2ac86-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="2ac86-111">如果不需要对终结点进行任何配置更改，则可从服务的 Web.config 文件中完全移除 `<system.ServiceModel>` 部分。</span><span class="sxs-lookup"><span data-stu-id="2ac86-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="2ac86-112">Web.config 文件包含一些由 ConfigFreeClientPage.aspx 使用的 ASP.NET 设置。</span><span class="sxs-lookup"><span data-stu-id="2ac86-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="2ac86-113">如果不是这样，则可以移除整个 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="2ac86-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ac86-114">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="2ac86-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2ac86-115">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="2ac86-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2ac86-116">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="2ac86-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2ac86-117">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="2ac86-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2ac86-118">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="2ac86-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2ac86-119">确保执行中的设置说明[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2ac86-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="2ac86-120">如中所述生成解决方案 ConfigFreeAjaxService.sln[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2ac86-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="2ac86-121">导航到`http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx`（不要打开 ConfigFreeClientPage.aspx 在浏览器中从项目目录中）。</span><span class="sxs-lookup"><span data-stu-id="2ac86-121">Navigate to `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ac86-122">运行此示例时，请确保不要对 IIS 中的 ServiceModelSamples 文件夹同时启用匿名身份验证和 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="2ac86-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="2ac86-123">如果同时启用了这两种身份验证，请禁用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="2ac86-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="2ac86-124">运行了该示例后，请启用 Windows 身份验证并运行“iisreset”。</span><span class="sxs-lookup"><span data-stu-id="2ac86-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac86-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ac86-125">See Also</span></span>  
 [<span data-ttu-id="2ac86-126">基本 AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="2ac86-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
