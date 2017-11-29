---
title: AspNetRouteIntegration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b54de1c495dee466475979db7e6ba8d8ff9cf55b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="aspnetrouteintegration"></a><span data-ttu-id="9e08e-102">AspNetRouteIntegration</span><span class="sxs-lookup"><span data-stu-id="9e08e-102">AspNetRouteIntegration</span></span>
<span data-ttu-id="9e08e-103">此示例演示如何使用 ASP.NET 路由来承载 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST 服务。</span><span class="sxs-lookup"><span data-stu-id="9e08e-103">This sample demonstrates how to host a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST service using ASP.NET routes.</span></span> <span data-ttu-id="9e08e-104">[基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)示例演示了这种情况下的自承载的版本，并讨论深度中的服务实现。</span><span class="sxs-lookup"><span data-stu-id="9e08e-104">The [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample shows a self-hosted version of this scenario and discusses the service implementation in depth.</span></span> <span data-ttu-id="9e08e-105">本主题重点介绍 ASP.NET 集成功能。</span><span class="sxs-lookup"><span data-stu-id="9e08e-105">This topic focuses on the ASP.NET integration feature.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="9e08e-106"> ASP.NET 路由的更多信息，请参见 <xref:System.Web.Routing>。</span><span class="sxs-lookup"><span data-stu-id="9e08e-106"> ASP.NET Routing, see <xref:System.Web.Routing>.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="9e08e-107">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="9e08e-107">Sample Details</span></span>  
 <span data-ttu-id="9e08e-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务以面向资源的/REST 方式公开客户集合。</span><span class="sxs-lookup"><span data-stu-id="9e08e-108">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service exposes a collection of customers in a resource-oriented/REST manner.</span></span> <span data-ttu-id="9e08e-109">与基于 SOAP 的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务一样，该服务可使用 .svc 文件在 ASP.NET 中承载。</span><span class="sxs-lookup"><span data-stu-id="9e08e-109">Just like a SOAP-based [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, the service can be hosted in ASP.NET using a .svc file.</span></span> <span data-ttu-id="9e08e-110">但是，这通常不是 HTTP 方案的首选，因为它要求该服务的 URL 中有 .svc。</span><span class="sxs-lookup"><span data-stu-id="9e08e-110">However, this is often not preferred for HTTP scenarios because it requires having .svc in the URL for the service.</span></span> <span data-ttu-id="9e08e-111">此外，它还需要与服务库一起部署 .svc 文件。</span><span class="sxs-lookup"><span data-stu-id="9e08e-111">In addition, it requires deploying a .svc file along with the service library.</span></span> <span data-ttu-id="9e08e-112">通过使用 ASP.NET 路由承载该服务，可以避免这些限制，如此示例中所演示。</span><span class="sxs-lookup"><span data-stu-id="9e08e-112">These limitations can be avoided by hosting the service using ASP.NET routes, as is demonstrated in this sample.</span></span>  
  
 <span data-ttu-id="9e08e-113">此示例通过在 Global.asax 文件中添加 <xref:System.ServiceModel.Activation.ServiceRoute> 而在 ASP.NET 中承载该服务。</span><span class="sxs-lookup"><span data-stu-id="9e08e-113">The sample hosts the service in ASP.NET by adding a <xref:System.ServiceModel.Activation.ServiceRoute> in a Global.asax file.</span></span> <span data-ttu-id="9e08e-114"><xref:System.ServiceModel.Activation.ServiceRoute> 指定服务的类型（此例中为“Service”）、用于该服务的服务主机工厂的类型（此例中为 <xref:System.ServiceModel.Activation.WebServiceHostFactory>）和该服务的 HTTP 基址（此例中为“~/Customers”）。</span><span class="sxs-lookup"><span data-stu-id="9e08e-114">The <xref:System.ServiceModel.Activation.ServiceRoute> specifies the type of the service (‘Service’ in this case), the type of the service host factory to use for the service (<xref:System.ServiceModel.Activation.WebServiceHostFactory> in this case) and the HTTP base address for the service (‘~/Customers’ in this case).</span></span>  
  
 <span data-ttu-id="9e08e-115">除此之外，此示例还包含一个用于添加 <xref:System.Web.Routing.UrlRoutingModule>（用于打开 ASP.NET 路由）的 Web.config，并包含该服务的配置。</span><span class="sxs-lookup"><span data-stu-id="9e08e-115">In addition to this, the sample includes a Web.config that adds the <xref:System.Web.Routing.UrlRoutingModule> (to turn on ASP.NET routes) and includes the configuration for the service.</span></span> <span data-ttu-id="9e08e-116">特别是，该配置使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 设置为 <xref:System.ServiceModel.Description.WebHttpEndpoint> 的默认 <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>来配置 `true` 服务。</span><span class="sxs-lookup"><span data-stu-id="9e08e-116">In particular, the configuration configures the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with a default <xref:System.ServiceModel.Description.WebHttpEndpoint> that has the <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> setting to `true`.</span></span> <span data-ttu-id="9e08e-117">因此，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 基础结构在 `http://localhost/Customers/help` 上创建一个基于 HTML 的自动帮助页，该帮助页提供有关如何构造该服务的 HTTP 请求以及如何访问该服务的 HTTP 响应的信息 – 例如，有关如何以 XML 和 JSON 表示客户详细信息的示例。</span><span class="sxs-lookup"><span data-stu-id="9e08e-117">As a result, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure creates an automatic HTML based help page at `http://localhost/Customers/help` that provides information about how to construct HTTP requests to the service and how to access the service’s HTTP response – for instance, an example of how the customer details are represented in XML and JSON.</span></span>  
  
 <span data-ttu-id="9e08e-118">通过以这种方式公开客户集合（一般来说是任何资源），客户端可以使用 URI 和 HTTP `GET`、`PUT`、`DELETE` 和 `POST` 以一种统一的方式与服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="9e08e-118">Exposing the customer collection (and more generally, any resource) in this manner allows a client to interact with a service in a uniform way using URIs and HTTP `GET`, `PUT`, `DELETE` and `POST`.</span></span>  
  
 <span data-ttu-id="9e08e-119">客户端项目中的 Program.cs 演示如何使用 <xref:System.Net.HttpWebRequest> 编写此类客户端。</span><span class="sxs-lookup"><span data-stu-id="9e08e-119">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="9e08e-120">请注意，这只是访问 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的一种方式。</span><span class="sxs-lookup"><span data-stu-id="9e08e-120">Note that this is just one way to access a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="9e08e-121">还可以使用其他 .NET Framework 类（如 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 通道工厂和 <xref:System.Net.WebClient>）来访问该服务。</span><span class="sxs-lookup"><span data-stu-id="9e08e-121">It is also possible to access the service using other .NET Framework classes like the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="9e08e-122">SDK 中的其他示例 (如[基本 HTTP 服务](../../../../docs/framework/wcf/samples/basic-http-service.md)示例和[自动格式选择](../../../../docs/framework/wcf/samples/automatic-format-selection.md)示例) 演示如何使用这些类与通信[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="9e08e-122">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample and the [Automatic Format Selection](../../../../docs/framework/wcf/samples/automatic-format-selection.md) sample) show how to use these classes to communicate with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="9e08e-123">此示例由 3 个项目组成：</span><span class="sxs-lookup"><span data-stu-id="9e08e-123">This sample consists of 3 projects:</span></span>  
  
 <span data-ttu-id="9e08e-124">服务</span><span class="sxs-lookup"><span data-stu-id="9e08e-124">Service</span></span>  
 <span data-ttu-id="9e08e-125">一个 Web 应用程序项目，它包含在 ASP.NET 中承载的 WCF HTTP 服务。</span><span class="sxs-lookup"><span data-stu-id="9e08e-125">A Web application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>  
  
 <span data-ttu-id="9e08e-126">客户端</span><span class="sxs-lookup"><span data-stu-id="9e08e-126">Client</span></span>  
 <span data-ttu-id="9e08e-127">一个对服务进行调用的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="9e08e-127">A console application project that makes calls to the service.</span></span>  
  
 <span data-ttu-id="9e08e-128">公共</span><span class="sxs-lookup"><span data-stu-id="9e08e-128">Common</span></span>  
 <span data-ttu-id="9e08e-129">一个共享库，它包含客户端和服务使用的 `Customer` 类型。</span><span class="sxs-lookup"><span data-stu-id="9e08e-129">A shared library that contains the `Customer` type used by the client and service.</span></span> <span data-ttu-id="9e08e-130">在客户端控制台应用程序运行时，客户端会向服务发出请求，并将响应中的相关信息写入控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="9e08e-130">As the client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9e08e-131">使用此示例</span><span class="sxs-lookup"><span data-stu-id="9e08e-131">To use this sample</span></span>  
  
1.  <span data-ttu-id="9e08e-132">打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中 ASP.NET 路由集成示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="9e08e-132">Open the solution for the ASP.NET Routes Integration sample in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="9e08e-133">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="9e08e-133">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="9e08e-134">如果尚未打开，请按"CTRL + W，S"以打开**解决方案资源管理器**窗口。</span><span class="sxs-lookup"><span data-stu-id="9e08e-134">If it is not already open, press "CTRL+W, S" to open the **Solution Explorer** window.</span></span>  
  
4.  <span data-ttu-id="9e08e-135">从**解决方案资源管理器**，右击**服务**项目，然后将光标放**调试**上下文菜单选项，以便**启动新实例**显示上下文菜单，然后选择**启动新实例**。</span><span class="sxs-lookup"><span data-stu-id="9e08e-135">From the **Solution Explorer** windows, right-click the **Service** project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears and select **Start New Instance**.</span></span>  <span data-ttu-id="9e08e-136">这将启动承载服务的 ASP.NET 开发服务器。</span><span class="sxs-lookup"><span data-stu-id="9e08e-136">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5.  <span data-ttu-id="9e08e-137">从**解决方案资源管理器**，右击**客户端**项目，然后将光标放**调试**上下文菜单选项，以便**启动新实例**显示上下文菜单，然后选择**启动新实例**。</span><span class="sxs-lookup"><span data-stu-id="9e08e-137">From the **Solution Explorer** windows, right-click the **Client** project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears and select **Start New Instance**.</span></span>  
  
6.  <span data-ttu-id="9e08e-138">出现客户端控制台窗口，该窗口提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。</span><span class="sxs-lookup"><span data-stu-id="9e08e-138">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="9e08e-139">可随时通过在浏览器中键入 HTML 帮助页的 URI 来查看该帮助页。</span><span class="sxs-lookup"><span data-stu-id="9e08e-139">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span> <span data-ttu-id="9e08e-140">在示例运行时，客户端将写入当前活动的状态。</span><span class="sxs-lookup"><span data-stu-id="9e08e-140">As the sample runs, the client writes the status of the current activity.</span></span>  
  
7.  <span data-ttu-id="9e08e-141">按任意键可终止客户端控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e08e-141">Press any key to terminate the client console application.</span></span>  
  
8.  <span data-ttu-id="9e08e-142">按 Shift + F5 来停止调试服务，在 Windows 通知区域中，右键单击 ASP.NET 开发服务器图标并选择**停止**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="9e08e-142">Press Shift+F5 to stop debugging the service and in the Windows Notification Area, right-click the ASP.NET development server icon and select **Stop** from the context menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9e08e-143">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9e08e-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9e08e-144">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9e08e-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9e08e-145">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="9e08e-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9e08e-146">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9e08e-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## <a name="see-also"></a><span data-ttu-id="9e08e-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e08e-147">See Also</span></span>
