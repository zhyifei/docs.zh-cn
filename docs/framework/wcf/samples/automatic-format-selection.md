---
title: "自动格式选择"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dab51e56-8517-4a6a-bb54-b55b15ab37bb
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5c3465611fcf418e194c44815c765f8823d8ad83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="automatic-format-selection"></a><span data-ttu-id="54357-102">自动格式选择</span><span class="sxs-lookup"><span data-stu-id="54357-102">Automatic Format Selection</span></span>
<span data-ttu-id="54357-103">本示例演示如何通过 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST 编程模型启用自动格式选择（XML 或 JSON），以及如何在操作代码中显式设置格式。</span><span class="sxs-lookup"><span data-stu-id="54357-103">This sample demonstrates how to enable automatic format selection (XML or JSON) with the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST programming model, as well as how to explicitly set the format in the operation code.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="54357-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="54357-104">Sample Details</span></span>  
 <span data-ttu-id="54357-105">本示例包含一个服务以及向该服务进行请求的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="54357-105">The sample consists of a service along with client code that makes requests to the service.</span></span> <span data-ttu-id="54357-106">该服务支持一个 HTTP `GET` 操作 (`EchoWithGet`) 和一个 HTTP `POST` 操作 (`EchoWithPost`)。</span><span class="sxs-lookup"><span data-stu-id="54357-106">The service supports a single HTTP `GET` operation (`EchoWithGet`) and a single HTTP `POST` operation (`EchoWithPost`).</span></span> <span data-ttu-id="54357-107">这两个操作都需要一个字符串，然后在响应中返回字符串。</span><span class="sxs-lookup"><span data-stu-id="54357-107">Both operations expect a string and then return the string in the response.</span></span> <span data-ttu-id="54357-108">对于 `GET` 操作，字符串在 URI 查询字符串参数中提供。</span><span class="sxs-lookup"><span data-stu-id="54357-108">With the `GET` operation, the string is provided in a URI query-string parameter.</span></span> <span data-ttu-id="54357-109">对于 `POST` 操作，字符串在请求正文中提供（以 XML 格式序列化）。</span><span class="sxs-lookup"><span data-stu-id="54357-109">With the `POST` operation, the string is provided in the body of the request, serialized in XML.</span></span> <span data-ttu-id="54357-110">利用 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 中新的自动格式选择和命令性格式选择功能，服务能够以 XML 或 JSON 格式返回响应。</span><span class="sxs-lookup"><span data-stu-id="54357-110">The service is able to return responses in either XML or JSON, utilizing the new automatic format selection and imperative format selection features in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span></span>  
  
 <span data-ttu-id="54357-111">在本示例中，使用 App.config 文件启用自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="54357-111">In the sample, automatic format selection is enabled using the App.config file.</span></span> <span data-ttu-id="54357-112">在默认的 Web HTTP 终结点上，为 `automaticFormatSelectionEnabled` 特性提供值 `true`。</span><span class="sxs-lookup"><span data-stu-id="54357-112">On the default Web HTTP endpoint, the `automaticFormatSelectionEnabled` attribute has been given a value of `true`.</span></span> <span data-ttu-id="54357-113">启用自动格式选择后，给定请求的 HTTP Accept 或 Content-Type 标头，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 基础结构会选择最合适的响应格式（XML 或 JSON）。</span><span class="sxs-lookup"><span data-stu-id="54357-113">With automatic format selection enabled, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure selects the most appropriate response format (XML or JSON) given the HTTP Accept or Content-Type headers of the request.</span></span> <span data-ttu-id="54357-114">除了将 `automaticFormatSelectionEnabled` 特性设置为 `true`，开发人员不需要提供任何其他代码或配置便可使用此新功能。</span><span class="sxs-lookup"><span data-stu-id="54357-114">The developer is not required to provide any additional code or configuration other than setting the `automaticFormatSelectionEnabled` attribute to `true` to use this new feature.</span></span> <span data-ttu-id="54357-115">在 Program.cs 中的客户端代码，请求会发送对这两个`GET`和`POST`的 HTTP Accept 标头，指定为"application/xml"或"应用程序/json"服务和服务操作返回的响应相应的格式。</span><span class="sxs-lookup"><span data-stu-id="54357-115">In the client code in Program.cs, requests are sent to both the `GET` and `POST` operations of the service with the HTTP Accept header specified as either "application/xml" or "application/json" and the service returns a response in that respective format.</span></span>  
  
 <span data-ttu-id="54357-116">在 `GET` 操作中，还使用了命令性格式选择。</span><span class="sxs-lookup"><span data-stu-id="54357-116">Also in the `GET` operation, imperative format selection is used.</span></span> <span data-ttu-id="54357-117">`GET` 操作检查是否存在可选的 `format` 查询字符串参数，如果存在，则在 <xref:System.ServiceModel.Web.WebOperationContext.OutgoingResponse%2A> 属性上设置响应格式。</span><span class="sxs-lookup"><span data-stu-id="54357-117">The `GET` operation checks for an optional `format` query-string parameter and if present, sets the response format on the <xref:System.ServiceModel.Web.WebOperationContext.OutgoingResponse%2A> property.</span></span> <span data-ttu-id="54357-118">以这种方式强制设置响应格式会重写 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 基础结构进行的自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="54357-118">Imperatively setting the response format in this way overrides the automatic format selection done by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure.</span></span>  
  
 <span data-ttu-id="54357-119">此示例包含一个自承载服务和一个客户端，它们都在一个控制台应用程序内运行。</span><span class="sxs-lookup"><span data-stu-id="54357-119">The sample consists of a self-hosted service and a client that runs within a console application.</span></span> <span data-ttu-id="54357-120">在控制台应用程序运行时，客户端会对服务进行请求，并将响应中的相关信息写入控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="54357-120">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="54357-121">使用此示例</span><span class="sxs-lookup"><span data-stu-id="54357-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="54357-122">打开自动格式选择示例的解决方案。</span><span class="sxs-lookup"><span data-stu-id="54357-122">Open the solution for the Automatic Format Selection Sample.</span></span> <span data-ttu-id="54357-123">在启动 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 时，必须以管理员身份运行才能成功执行该示例。</span><span class="sxs-lookup"><span data-stu-id="54357-123">When launching [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], you must run as an administrator for the sample to execute successfully.</span></span> <span data-ttu-id="54357-124">执行此操作，请右键单击[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]图标并选择**以管理员身份运行**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="54357-124">Do this by right-clicking the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icon and select **Run as Administrator** from the context menu.</span></span>  
  
2.  <span data-ttu-id="54357-125">按 Ctrl+Shift+B 生成解决方案，然后按 Ctrl+F5 运行控制台应用程序 AutomaticFormatSelection 项目。</span><span class="sxs-lookup"><span data-stu-id="54357-125">Press CTRL+SHIFT+B to build the solution and then press Ctrl+F5 to run the console application AutomaticFormatSelection project.</span></span> <span data-ttu-id="54357-126">将出现控制台窗口，它提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。</span><span class="sxs-lookup"><span data-stu-id="54357-126">The console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span>  
  
3.  <span data-ttu-id="54357-127">在示例运行时，客户端会向服务发送请求，并将响应写入控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="54357-127">As the sample runs, the client sends requests to the service and writes the responses to the console window.</span></span> <span data-ttu-id="54357-128">请注意采用 XML 和 JSON 的不同格式的响应。</span><span class="sxs-lookup"><span data-stu-id="54357-128">Notice the different formats of the responses in XML and JSON.</span></span>  
  
4.  <span data-ttu-id="54357-129">按任何键可终止示例。</span><span class="sxs-lookup"><span data-stu-id="54357-129">Press any key to terminate the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="54357-130">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="54357-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="54357-131">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="54357-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="54357-132">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="54357-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="54357-133">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="54357-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AutomaticFormatSelection`  
  
## <a name="see-also"></a><span data-ttu-id="54357-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54357-134">See Also</span></span>
