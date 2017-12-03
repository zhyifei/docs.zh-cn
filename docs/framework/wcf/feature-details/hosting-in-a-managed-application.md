---
title: "在托管应用程序中承载"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e6543f1faec5d3298c9a2b825b3a016eb5e7d09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="hosting-in-a-managed-application"></a><span data-ttu-id="6eb51-102">在托管应用程序中承载</span><span class="sxs-lookup"><span data-stu-id="6eb51-102">Hosting in a Managed Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="6eb51-103"> 服务可以承载于任何 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="6eb51-103"> services can be hosted in any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application.</span></span> <span data-ttu-id="6eb51-104">自承载服务是最灵活的宿主选项，因为此服务部署所需要的基础结构最少。</span><span class="sxs-lookup"><span data-stu-id="6eb51-104">Self-hosting services is the most flexible hosting option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="6eb51-105">但是，此服务也是最不可靠的宿主选项，因为托管应用程序未提供 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]中其他宿主选项（如 Internet 信息服务 (IIS) 和 Windows 服务）的高级宿主和管理功能。</span><span class="sxs-lookup"><span data-stu-id="6eb51-105">However, it is also the least robust hosting option, because managed applications do not provide the advanced hosting and management features of other hosting options in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], such as Internet Information Services (IIS) and Windows services.</span></span>  
  
 <span data-ttu-id="6eb51-106">若要创建自承载服务，请创建并打开 <xref:System.ServiceModel.ServiceHost>的实例以启动侦听消息的服务。</span><span class="sxs-lookup"><span data-stu-id="6eb51-106">To create a self-hosted service, create and open an instance of the <xref:System.ServiceModel.ServiceHost>, which starts a service listening for messages.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="6eb51-107">[如何： 承载于托管应用程序的 WCF 服务](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)。</span><span class="sxs-lookup"><span data-stu-id="6eb51-107"> [How to: Host a WCF Service in a Managed Application](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="6eb51-108">有关如何定义协定、 实现协定，以及承载托管的应用程序内的服务的完整示例，请参阅[入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)和[自承载](../../../../docs/framework/wcf/samples/self-host.md)。</span><span class="sxs-lookup"><span data-stu-id="6eb51-108">For a complete example on how to define a contract, implement the contract, and host a service inside of a managed application see the [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md) and the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md).</span></span>  
  
 <span data-ttu-id="6eb51-109">以下各部分描述了使用此宿主选项的常见情况。</span><span class="sxs-lookup"><span data-stu-id="6eb51-109">The following sections describe common scenarios that use this hosting option.</span></span>  
  
## <a name="console-applications"></a><span data-ttu-id="6eb51-110">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="6eb51-110">Console Applications</span></span>  
 <span data-ttu-id="6eb51-111">自承载支持的常见方案是在控制台应用程序内部运行的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="6eb51-111">Common scenarios that self-hosting enables are [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running inside console applications.</span></span> <span data-ttu-id="6eb51-112">在控制台应用程序内部承载一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务通常在服务的开发阶段非常有用。</span><span class="sxs-lookup"><span data-stu-id="6eb51-112">Hosting a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service inside a console application is typically useful during the development phase of the service.</span></span> <span data-ttu-id="6eb51-113">这使服务变得容易调试，从中跟踪信息以查明应用程序内发生的情况变得更加方便，以及通过将其复制到新的位置进行来回移动变得更加轻松。</span><span class="sxs-lookup"><span data-stu-id="6eb51-113">This makes them easy to debug, easy to get trace information from to find out what is happening inside of the application, and easy to move around by copying them to new locations.</span></span>  
  
## <a name="rich-client-applications"></a><span data-ttu-id="6eb51-114">胖客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="6eb51-114">Rich Client Applications</span></span>  
 <span data-ttu-id="6eb51-115">自承载支持的其他常见方案是胖客户端应用程序，如基于 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] 或 Windows 窗体 (WinForms) 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6eb51-115">Other common scenarios that self-hosting enables are rich client applications, such as those based on [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] or Windows Forms (WinForms).</span></span> <span data-ttu-id="6eb51-116">此宿主选项还使丰富客户端应用程序（如 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 和 WinForms 应用程序）与外部世界的通信变得很容易。</span><span class="sxs-lookup"><span data-stu-id="6eb51-116">This hosting option also makes it easy for rich client applications, such as [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] and WinForms applications, to communicate with the outside world.</span></span> <span data-ttu-id="6eb51-117">例如，一个将 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 用于其用户界面并作为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务主机的对等协作客户端，允许其他客户端连接到它并共享信息。</span><span class="sxs-lookup"><span data-stu-id="6eb51-117">For example, a peer-to-peer collaboration client that uses [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] for its user interface and also hosts a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that allows other clients to connect to it and share information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eb51-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6eb51-118">See Also</span></span>  
 [<span data-ttu-id="6eb51-119">托管服务</span><span class="sxs-lookup"><span data-stu-id="6eb51-119">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="6eb51-120">入门教程</span><span class="sxs-lookup"><span data-stu-id="6eb51-120">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)
