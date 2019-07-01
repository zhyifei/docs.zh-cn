---
title: 在 Internet 信息服务中承载
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 3940d8436ba5441d4e884879213a7a782214cb05
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486754"
---
# <a name="hosting-in-internet-information-services"></a><span data-ttu-id="eabaa-102">在 Internet 信息服务中承载</span><span class="sxs-lookup"><span data-stu-id="eabaa-102">Hosting in Internet Information Services</span></span>
<span data-ttu-id="eabaa-103">用于承载 Windows Communication Foundation (WCF) 服务的一个选项是 Internet 信息服务 (IIS) 应用程序内。</span><span class="sxs-lookup"><span data-stu-id="eabaa-103">One option for hosting Windows Communication Foundation (WCF) services is inside of an Internet Information Services (IIS) application.</span></span> <span data-ttu-id="eabaa-104">此承载模型是类似于使用 ASP.NET 和 ASP.NET Web 服务 (ASMX) Web 服务的模型。</span><span class="sxs-lookup"><span data-stu-id="eabaa-104">This hosting model is similar to the model used by ASP.NET and ASP.NET Web services (ASMX) Web Services.</span></span>  
  
## <a name="versions-of-iis"></a><span data-ttu-id="eabaa-105">IIS 的版本</span><span class="sxs-lookup"><span data-stu-id="eabaa-105">Versions of IIS</span></span>  
 <span data-ttu-id="eabaa-106">可以在以下操作系统上的以下版本的 IIS 上承载 WCF:</span><span class="sxs-lookup"><span data-stu-id="eabaa-106">WCF can be hosted on the following versions of IIS on the following operating systems:</span></span>  
  
- <span data-ttu-id="eabaa-107">[!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)] 上的 IIS 5.1。</span><span class="sxs-lookup"><span data-stu-id="eabaa-107">IIS 5.1 on [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)].</span></span> <span data-ttu-id="eabaa-108">此环境对于设计和开发 IIS 承载的应用程序非常有用，这些应用程序稍后将部署在 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 等服务器操作系统上。</span><span class="sxs-lookup"><span data-stu-id="eabaa-108">This environment is useful for the design and development of IIS-hosted applications that are later deployed on a server operating system such as [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span>  
  
- <span data-ttu-id="eabaa-109">上的 IIS 6.0 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eabaa-109">IIS 6.0 on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span></span> <span data-ttu-id="eabaa-110">IIS 6.0 提供了一个高级的过程模型，提供改进的可伸缩性、 可靠性和应用程序隔离。</span><span class="sxs-lookup"><span data-stu-id="eabaa-110">IIS 6.0 provides an advanced process model that offers improved scalability, reliability, and application isolation.</span></span> <span data-ttu-id="eabaa-111">此环境适合以独占方式使用 HTTP 通信的 WCF 服务的生产部署。</span><span class="sxs-lookup"><span data-stu-id="eabaa-111">This environment is suitable for production deployment of WCF services that use HTTP communication exclusively.</span></span>  
  
- <span data-ttu-id="eabaa-112">[!INCLUDE[wv](../../../../includes/wv-md.md)] 和 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上的 IIS 7.0。</span><span class="sxs-lookup"><span data-stu-id="eabaa-112">IIS 7.0 on [!INCLUDE[wv](../../../../includes/wv-md.md)] and [!INCLUDE[lserver](../../../../includes/lserver-md.md)].</span></span> <span data-ttu-id="eabaa-113">IIS 7.0 提供与 IIS 6.0 相同的高级的进程模型，但使用 Windows 进程激活服务 (WAS) 允许通过 HTTP 之外的协议进行激活和网络通信。</span><span class="sxs-lookup"><span data-stu-id="eabaa-113">IIS 7.0 provides the same advanced process model as IIS 6.0, but uses the Windows Process Activation Service (WAS) to allow activation and network communication over protocols other than HTTP.</span></span> <span data-ttu-id="eabaa-114">此环境适合于通过任何支持的 WCF （包括 HTTP、 net.tcp、 net.pipe 和 net.msmq） 的网络协议进行通信的 WCF 服务的开发。</span><span class="sxs-lookup"><span data-stu-id="eabaa-114">This environment is suitable for the development of WCF services that communicate over any network protocol supported by WCF (including HTTP, net.tcp, net.pipe, and net.msmq).</span></span> <span data-ttu-id="eabaa-115">有关 WAS 的详细信息，请参阅[在 Windows 进程激活服务中承载](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)。</span><span class="sxs-lookup"><span data-stu-id="eabaa-115">For more information about WAS, see [Hosting in Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).</span></span>  
  
- <span data-ttu-id="eabaa-116">[Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496)适用于 IIS 7.0 和 Windows 进程激活服务 (WAS) 提供丰富的应用程序托管为 NET4 WCF 和 WF 服务的环境。</span><span class="sxs-lookup"><span data-stu-id="eabaa-116">[Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) works with IIS 7.0 and Windows Process Activation Service (WAS) to provide a rich application hosting environment for NET4 WCF and WF services.</span></span> <span data-ttu-id="eabaa-117">这些优点包括进程生命周期管理、进程回收、共享承载、快速失败保护、进程孤立、按需激活和运行状况监视。</span><span class="sxs-lookup"><span data-stu-id="eabaa-117">These benefits include process life-cycle management, process recycling, shared hosting, rapid failure protection, process orphaning, on-demand activation, and health monitoring.</span></span> <span data-ttu-id="eabaa-118">有关详细信息，请参阅[AppFabric 承载功能](https://go.microsoft.com/fwlink/?LinkId=196494)并[AppFabric 承载概念](https://go.microsoft.com/fwlink/?LinkId=196495)。</span><span class="sxs-lookup"><span data-stu-id="eabaa-118">For detailed information, see [AppFabric Hosting Features](https://go.microsoft.com/fwlink/?LinkId=196494) and [AppFabric Hosting Concepts](https://go.microsoft.com/fwlink/?LinkId=196495).</span></span>  
  
## <a name="benefits-of-iis-hosting"></a><span data-ttu-id="eabaa-119">IIS 承载的好处</span><span class="sxs-lookup"><span data-stu-id="eabaa-119">Benefits of IIS Hosting</span></span>  
 <span data-ttu-id="eabaa-120">承载在 IIS 中的 WCF 服务有以下优点：</span><span class="sxs-lookup"><span data-stu-id="eabaa-120">Hosting WCF services in IIS has several benefits:</span></span>  
  
- <span data-ttu-id="eabaa-121">在 IIS 中承载的 WCF 服务部署和管理与任何其他类型的 IIS 应用程序，包括 ASP.NET 应用程序和 ASMX 一样。</span><span class="sxs-lookup"><span data-stu-id="eabaa-121">WCF services hosted in IIS are deployed and managed like any other type of IIS application, including ASP.NET applications and ASMX.</span></span>  
  
- <span data-ttu-id="eabaa-122">IIS 提供进程激活、运行状况管理和回收功能以提高承载的应用程序的可靠性。</span><span class="sxs-lookup"><span data-stu-id="eabaa-122">IIS provides process activation, health management, and recycling capabilities to increase the reliability of hosted applications.</span></span>  
  
- <span data-ttu-id="eabaa-123">如 ASP.NET，ASP.NET 中承载的 WCF 服务可以充分利用 ASP.NET 共享的承载模型其中多个应用程序驻留在一个公共辅助进程以提高的服务器密度和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="eabaa-123">Like ASP.NET, WCF services hosted in ASP.NET can take advantage of the ASP.NET shared hosting model where multiple applications reside in a common worker process for improved server density and scalability.</span></span>  
  
- <span data-ttu-id="eabaa-124">在 IIS 中承载的 WCF 服务使用相同的动态编译模型作为 ASP.NET 2.0 中，这简化了开发和部署托管服务。</span><span class="sxs-lookup"><span data-stu-id="eabaa-124">WCF services hosted in IIS use the same dynamic compilation model as ASP.NET 2.0, which simplifies development and deployment of hosted services.</span></span>  
  
 <span data-ttu-id="eabaa-125">在决定在 IIS 中承载 WCF 服务时，务必要记住 IIS 5.1 和 IIS 6.0 仅限于仅使用 HTTP 通信。</span><span class="sxs-lookup"><span data-stu-id="eabaa-125">When deciding to host WCF services in IIS, it is important to remember that IIS 5.1 and IIS 6.0 are limited to HTTP communication only.</span></span> <span data-ttu-id="eabaa-126">有关选择宿主环境的详细信息，请参阅[托管服务](../../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="eabaa-126">For more information about choosing a hosting environment, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a><span data-ttu-id="eabaa-127">部署 IIS 承载的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="eabaa-127">Deploying an IIS-Hosted WCF Service</span></span>  
 <span data-ttu-id="eabaa-128">开发和部署 IIS 承载的 WCF 服务包含以下任务：</span><span class="sxs-lookup"><span data-stu-id="eabaa-128">Developing and deploying an IIS-hosted WCF service consists of the following tasks:</span></span>  
  
- <span data-ttu-id="eabaa-129">请确保，IIS、 ASP.NET、 WCF 和 WCF HTTP 激活组件正确安装和注册。</span><span class="sxs-lookup"><span data-stu-id="eabaa-129">Ensure that IIS, ASP.NET, WCF and the WCF HTTP activation component are correctly installed and registered.</span></span>  
  
- <span data-ttu-id="eabaa-130">创建新的 IIS 应用程序，或重新使用现有的 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="eabaa-130">Create a new IIS application, or reuse an existing ASP.NET application.</span></span>  
  
- <span data-ttu-id="eabaa-131">创建 WCF 服务的.svc 文件。</span><span class="sxs-lookup"><span data-stu-id="eabaa-131">Create a .svc file for the WCF service.</span></span>  
  
- <span data-ttu-id="eabaa-132">将服务实现部署到 IIS 应用程序。</span><span class="sxs-lookup"><span data-stu-id="eabaa-132">Deploy the service implementation to the IIS application.</span></span>  
  
- <span data-ttu-id="eabaa-133">配置 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="eabaa-133">Configure the WCF service.</span></span>  
  
 <span data-ttu-id="eabaa-134">每个任务的讨论，请参阅[部署服务承载的 WCF 服务](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="eabaa-134">For a discussion of each of these tasks, see [Deploying an Internet Information Services-Hosted WCF Service](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).</span></span>  
  
## <a name="wcf-services-and-aspnet"></a><span data-ttu-id="eabaa-135">WCF 服务和 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="eabaa-135">WCF Services and ASP.NET</span></span>  
 <span data-ttu-id="eabaa-136">WCF 服务可以是托管任一端的并排使用 ASP.NET 或 ASP.NET 兼容模式下在其中服务可以充分利用 ASP.NET Web 应用程序平台提供的功能。</span><span class="sxs-lookup"><span data-stu-id="eabaa-136">WCF services can be hosted either side-by-side with ASP.NET or in ASP.NET Compatibility Mode in which services can take full advantage of features provided by the ASP.NET Web application platform.</span></span> <span data-ttu-id="eabaa-137">有关这些功能的讨论，请参阅[WCF 服务和 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)。</span><span class="sxs-lookup"><span data-stu-id="eabaa-137">For a discussion of these features, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eabaa-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="eabaa-138">See also</span></span>

- [<span data-ttu-id="eabaa-139">使用 ServiceHostFactory 扩展宿主</span><span class="sxs-lookup"><span data-stu-id="eabaa-139">Extending Hosting Using ServiceHostFactory</span></span>](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)
- [<span data-ttu-id="eabaa-140">部署承载于 Internet Information Services 中的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="eabaa-140">Deploying an Internet Information Services-Hosted WCF Service</span></span>](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)
- [<span data-ttu-id="eabaa-141">WCF 服务和 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="eabaa-141">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [<span data-ttu-id="eabaa-142">Internet Information Services 承载最佳做法</span><span class="sxs-lookup"><span data-stu-id="eabaa-142">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="eabaa-143">为 Windows Communication Foundation 配置 Internet Information Services 7.0</span><span class="sxs-lookup"><span data-stu-id="eabaa-143">Configuring Internet Information Services 7.0 for Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)
- [<span data-ttu-id="eabaa-144">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="eabaa-144">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
