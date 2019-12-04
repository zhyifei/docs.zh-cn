---
title: 无配置的 AJAX 服务
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: bf80f00bbca370c973dab9f20024284a465be521
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716197"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="79241-102">无配置的 AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="79241-102">AJAX Service Without Configuration</span></span>

<span data-ttu-id="79241-103">此示例演示如何使用 Windows Communication Foundation （WCF）来创建基本 ASP.NET 异步 JavaScript 和 XML （AJAX）服务（可通过从 Web 浏览器客户端使用 JavaScript 代码访问的服务）而无需使用任何配置设置。</span><span class="sxs-lookup"><span data-stu-id="79241-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="79241-104">该服务在 .svc 文件中使用特殊语法来自动启用 AJAX 终结点。</span><span class="sxs-lookup"><span data-stu-id="79241-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>

<span data-ttu-id="79241-105">WCF 中的 AJAX 支持经过优化，可通过 `ScriptManager` 控件与 ASP.NET AJAX 一起使用。</span><span class="sxs-lookup"><span data-stu-id="79241-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="79241-106">有关将 WCF 与 ASP.NET AJAX 一起使用的示例，请参阅[Ajax 示例](ajax.md)。</span><span class="sxs-lookup"><span data-stu-id="79241-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="79241-107">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="79241-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="79241-108">此示例是基于使用 HTTP POST 的 AJAX 服务生成的。</span><span class="sxs-lookup"><span data-stu-id="79241-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="79241-109">如[基本 AJAX 服务](../../../../docs/framework/wcf/samples/basic-ajax-service.md)示例中所述，<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 用于宿主服务。</span><span class="sxs-lookup"><span data-stu-id="79241-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>

```text
<%ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"
%>
```

<span data-ttu-id="79241-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 自动将 <xref:System.ServiceModel.Description.WebScriptEndpoint> 添加到服务。</span><span class="sxs-lookup"><span data-stu-id="79241-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="79241-111">如果不需要对终结点进行任何配置更改，则可从服务的 Web.config 文件中完全移除 `<system.ServiceModel>` 部分。</span><span class="sxs-lookup"><span data-stu-id="79241-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="79241-112">Web.config 文件包含一些由 ConfigFreeClientPage.aspx 使用的 ASP.NET 设置。</span><span class="sxs-lookup"><span data-stu-id="79241-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="79241-113">如果不是这样，则可以移除整个 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="79241-113">If that were not the case, the entire Web.config file could be removed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79241-114">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="79241-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="79241-115">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="79241-115">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="79241-116">如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="79241-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="79241-117">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="79241-117">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="79241-118">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="79241-118">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="79241-119">确保在[Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)中执行设置说明。</span><span class="sxs-lookup"><span data-stu-id="79241-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="79241-120">按照[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)中所述生成解决方案 ConfigFreeAjaxService。</span><span class="sxs-lookup"><span data-stu-id="79241-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="79241-121">导航到 `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` （不要在浏览器中从项目目录中打开 Configfreeclientpage.aspx）。</span><span class="sxs-lookup"><span data-stu-id="79241-121">Navigate to `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>

> [!NOTE]
> <span data-ttu-id="79241-122">运行此示例时，请确保不要对 IIS 中的 ServiceModelSamples 文件夹同时启用匿名身份验证和 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="79241-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="79241-123">如果同时启用了这两种身份验证，请禁用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="79241-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="79241-124">运行了该示例后，请启用 Windows 身份验证并运行“iisreset”。</span><span class="sxs-lookup"><span data-stu-id="79241-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>

## <a name="see-also"></a><span data-ttu-id="79241-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79241-125">See also</span></span>

- [<span data-ttu-id="79241-126">基本 AJAX 服务</span><span class="sxs-lookup"><span data-stu-id="79241-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
