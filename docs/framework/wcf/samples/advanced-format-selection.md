---
title: "高级格式选择"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e02d9082-4d55-41d8-9329-98f6d1c77f06
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 124bf59f29ff04e643200edf686f79f573937a03
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="advanced-format-selection"></a><span data-ttu-id="9a278-102">高级格式选择</span><span class="sxs-lookup"><span data-stu-id="9a278-102">Advanced Format Selection</span></span>
<span data-ttu-id="9a278-103">本示例演示如何扩展 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST 编程模型以支持新的传出响应格式。</span><span class="sxs-lookup"><span data-stu-id="9a278-103">This sample demonstrates how to extend the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST programming model to support new outgoing response formats.</span></span> <span data-ttu-id="9a278-104">此外，本示例使用 T4 模板以 HTML 页的形式返回响应，从而演示如何实现视图样式编程模型。</span><span class="sxs-lookup"><span data-stu-id="9a278-104">In addition, the sample uses a T4 Template to return the response as an XHTML page, demonstrating how a view-style programming model can be implemented.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="9a278-105">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="9a278-105">Sample Details</span></span>  
 <span data-ttu-id="9a278-106">本示例包含一个简单服务以及向该服务进行请求的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="9a278-106">The sample consists of a simple service along with client code that makes requests to the service.</span></span>  <span data-ttu-id="9a278-107">该服务支持一个 [WebGet] 操作，该操作具有以下方法签名：`Message EchoListWithGet(string list);`</span><span class="sxs-lookup"><span data-stu-id="9a278-107">The service supports a single [WebGet] operation, which has the following method signature: `Message EchoListWithGet(string list);`</span></span>  
  
 <span data-ttu-id="9a278-108">当客户端向服务进行请求时，会通过 `list` 查询字符串参数提供一个逗号分隔的项列表，服务以下列格式之一返回同一个列表：XML、JSON、Atom、XHTML 或 jpeg。</span><span class="sxs-lookup"><span data-stu-id="9a278-108">When the client makes a request to the service, it provides a comma-separated list of items from the `list` query-string parameter and the service returns that same list in one of the following formats: XML, JSON, Atom, XHTML, or jpeg.</span></span>  
  
 <span data-ttu-id="9a278-109">服务返回的响应格式首先由 `format` 查询字符串参数确定，其次由与请求一起提供的 HTTP Accept 标头确定。</span><span class="sxs-lookup"><span data-stu-id="9a278-109">The response format returned by the service is determined first by a `format` query-string parameter and second by an HTTP Accept header supplied with the request.</span></span> <span data-ttu-id="9a278-110">如果 `format` 查询字符串参数的值是上面格式中的一种，则以该格式返回响应。</span><span class="sxs-lookup"><span data-stu-id="9a278-110">If the value of `format` query-string parameter is one of the preceding formats, then the response is returned in that format.</span></span> <span data-ttu-id="9a278-111">如果不存在 `format` 查询字符串，则服务会遍历来自请求的 Accept 标头元素并返回服务支持的第一个内容类型的格式。</span><span class="sxs-lookup"><span data-stu-id="9a278-111">If the `format` query-string is not present, then the service iterates through the Accept header elements from the request and returns the format of the first content-type that the service supports.</span></span>  
  
 <span data-ttu-id="9a278-112">需要注意操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="9a278-112">The return type of the operation is worth noting.</span></span> <span data-ttu-id="9a278-113">当操作返回的类型不是 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 时，<xref:System.ServiceModel.Channels.Message> REST 编程模型本身只支持 XML 和 JSON 响应格式。</span><span class="sxs-lookup"><span data-stu-id="9a278-113">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST programming model only natively supports XML and JSON response formats when an operation returns a type other than <xref:System.ServiceModel.Channels.Message>.</span></span> <span data-ttu-id="9a278-114">但是，当使用 <xref:System.ServiceModel.Channels.Message> 作为返回类型时，开发人员可以完全控制应如何格式化消息内容。</span><span class="sxs-lookup"><span data-stu-id="9a278-114">However, when using <xref:System.ServiceModel.Channels.Message> as the return type, the developer has complete control over how the content of the message should be formatted.</span></span>  
  
 <span data-ttu-id="9a278-115">本示例使用 <xref:System.ServiceModel.Web.WebOperationContext.CreateXmlResponse%2A>、<xref:System.ServiceModel.Web.WebOperationContext.CreateJsonResponse%2A> 和 <xref:System.ServiceModel.Web.WebOperationContext.CreateAtom10Response%2A> 方法将字符串列表分别序列化为 XML、JSON 和 ATOM 消息。</span><span class="sxs-lookup"><span data-stu-id="9a278-115">The sample uses the <xref:System.ServiceModel.Web.WebOperationContext.CreateXmlResponse%2A>, <xref:System.ServiceModel.Web.WebOperationContext.CreateJsonResponse%2A> and <xref:System.ServiceModel.Web.WebOperationContext.CreateAtom10Response%2A> methods to serialize the list of strings into XML, JSON, and ATOM messages respectively.</span></span> <span data-ttu-id="9a278-116">对于 jpeg 响应格式，使用 <xref:System.ServiceModel.Web.WebOperationContext.CreateStreamResponse%2A> 方法并将图像保存到流中。</span><span class="sxs-lookup"><span data-stu-id="9a278-116">For the jpeg response format, the <xref:System.ServiceModel.Web.WebOperationContext.CreateStreamResponse%2A> method is used and the image is saved to the stream.</span></span> <span data-ttu-id="9a278-117">对于 XHTML 响应，使用 <xref:System.ServiceModel.Web.WebOperationContext.CreateTextResponse%2A> 以及预处理的 T4 模板，该模板由一个 .tt 文件和一个自动生成的 .cs 文件组成。</span><span class="sxs-lookup"><span data-stu-id="9a278-117">For the XHTML response, the <xref:System.ServiceModel.Web.WebOperationContext.CreateTextResponse%2A> is used along with a preprocessed T4 template, which consists of a .tt file and an auto-generated .cs file.</span></span> <span data-ttu-id="9a278-118">通过 .tt 文件，开发人员可以采用包含变量和控制结构的模板形式编写响应。</span><span class="sxs-lookup"><span data-stu-id="9a278-118">The .tt file allows a developer to write a response in a template form that contains variables and control structures.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9a278-119">T4 的更多信息，请参阅[通过使用文本模板生成项目](http://go.microsoft.com/fwlink/?LinkId=166023)。</span><span class="sxs-lookup"><span data-stu-id="9a278-119"> T4, see [Generating Artifacts By Using Text Templates](http://go.microsoft.com/fwlink/?LinkId=166023).</span></span>  
  
 <span data-ttu-id="9a278-120">此示例包含一个自承载服务和一个客户端，它们都在一个控制台应用程序内运行。</span><span class="sxs-lookup"><span data-stu-id="9a278-120">The sample consists of a self-hosted service and a client that runs within a console application.</span></span> <span data-ttu-id="9a278-121">在控制台应用程序运行时，客户端会对服务进行请求，并将响应中的相关信息写入控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="9a278-121">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="9a278-122">运行此示例</span><span class="sxs-lookup"><span data-stu-id="9a278-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="9a278-123">打开高级格式选择示例的解决方案。</span><span class="sxs-lookup"><span data-stu-id="9a278-123">Open the solution for the Advanced Format Selection Sample.</span></span> <span data-ttu-id="9a278-124">在启动 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 时，应以管理员身份运行才能成功执行该示例。</span><span class="sxs-lookup"><span data-stu-id="9a278-124">When launching [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], you should run as an administrator for the sample to execute successfully.</span></span> <span data-ttu-id="9a278-125">执行此操作，请右键单击[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]图标并选择**以管理员身份运行**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="9a278-125">Do this by right-clicking the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icon and choosing **Run as Administrator** from the context menu.</span></span>  
  
2.  <span data-ttu-id="9a278-126">按 Ctrl+Shift+B 生成解决方案，然后按 Ctrl+F5 运行控制台应用程序 AdvancedFormatSelection 项目而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="9a278-126">Press CTRL+SHIFT+B to build the solution and then press Ctrl-F5 to run the console application AdvancedFormatSelection project without debugging.</span></span> <span data-ttu-id="9a278-127">将出现控制台窗口，它提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。</span><span class="sxs-lookup"><span data-stu-id="9a278-127">The console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span>  
  
3.  <span data-ttu-id="9a278-128">在示例运行时，客户端会向服务发送请求，并将响应写入控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="9a278-128">As the sample runs, the client sends requests to the service and writes the responses to the console window.</span></span> <span data-ttu-id="9a278-129">请注意响应的不同格式：XML、JSON、Atom 和 XHTML。</span><span class="sxs-lookup"><span data-stu-id="9a278-129">Notice the different formats of the responses: XML, JSON, Atom, and XHTML.</span></span>  
  
4.  <span data-ttu-id="9a278-130">随后会提示您浏览到可以用于请求 .jpeg 格式的响应的 URI。</span><span class="sxs-lookup"><span data-stu-id="9a278-130">You are then prompted to browse to a URI in which you can request the response in a .jpeg format.</span></span> <span data-ttu-id="9a278-131">打开浏览器并浏览至给定 URI。</span><span class="sxs-lookup"><span data-stu-id="9a278-131">Open a browser and browse to the given URI.</span></span>  
  
5.  <span data-ttu-id="9a278-132">按任何键可终止示例。</span><span class="sxs-lookup"><span data-stu-id="9a278-132">Press any key to terminate the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9a278-133">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9a278-133">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9a278-134">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9a278-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9a278-135">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="9a278-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9a278-136">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9a278-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AdvancedFormatSelection`  
  
## <a name="see-also"></a><span data-ttu-id="9a278-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a278-137">See Also</span></span>
