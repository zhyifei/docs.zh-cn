---
title: Hosting2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0820c7e5-0b50-4cde-80e7-74e346513002
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cc98a6c6b0e8b552a7bf04d3fc1a97b41883677
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="hosting"></a><span data-ttu-id="dbd6e-102">宿主</span><span class="sxs-lookup"><span data-stu-id="dbd6e-102">Hosting</span></span>
<span data-ttu-id="dbd6e-103">本节中的主题介绍服务承载。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-103">The topics in the section describe service hosting.</span></span> <span data-ttu-id="dbd6e-104">可以承载服务，通过 Internet 信息服务 (IIS)、 Windows 进程激活服务 (WAS)、 Windows Server AppFabric、 Windows 服务，或托管的应用程序-此选项通常称为*自承载*。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-104">A service can be hosted by Internet Information Services (IIS), Windows Process Activation Service (WAS), Windows Server AppFabric, a Windows service, or by a managed application—this option is often referred to as *self hosting*.</span></span>  
  
 <span data-ttu-id="dbd6e-105">值得注意的是，从不受信任的主机运行服务或任何扩展会危害安全。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-105">It is important to note that running a service or any extension from an untrusted host compromises security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbd6e-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="dbd6e-106">In This Section</span></span>  
 [<span data-ttu-id="dbd6e-107">在 Internet 信息服务中承载</span><span class="sxs-lookup"><span data-stu-id="dbd6e-107">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 <span data-ttu-id="dbd6e-108">描述如何[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]服务承载于 Internet 信息服务或[Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496)。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-108">Describes how a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service is hosted in Internet Information Services or [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496).</span></span>  
  
 [<span data-ttu-id="dbd6e-109">在 Windows Process Activation Service 中承载</span><span class="sxs-lookup"><span data-stu-id="dbd6e-109">Hosting in Windows Process Activation Service</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)  
 <span data-ttu-id="dbd6e-110">描述 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务如何承载于 Windows 进程激活服务中。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-110">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted by Windows Process Activation Service.</span></span>  
  
 [<span data-ttu-id="dbd6e-111">在 Windows 服务应用程序中承载</span><span class="sxs-lookup"><span data-stu-id="dbd6e-111">Hosting in a Windows Service Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-windows-service-application.md)  
 <span data-ttu-id="dbd6e-112">描述 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务如何承载于 Windows 服务中。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-112">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted by a Windows service.</span></span>  
  
 [<span data-ttu-id="dbd6e-113">在托管应用程序中承载</span><span class="sxs-lookup"><span data-stu-id="dbd6e-113">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)  
 <span data-ttu-id="dbd6e-114">描述 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务如何承载于托管应用程序中。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-114">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted in a managed application.</span></span>  
  
 [<span data-ttu-id="dbd6e-115">基于配置的 IIS 和 WAS 中的激活</span><span class="sxs-lookup"><span data-stu-id="dbd6e-115">Configuration-Based Activation in IIS and WAS</span></span>](../../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 <span data-ttu-id="dbd6e-116">描述如何在 IIS 或 WAS 下不使用 .svc 文件承载 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-116">Describes how a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted under IIS or WAS without using a .svc file.</span></span>  
  
 [<span data-ttu-id="dbd6e-117">支持多个 IIS 站点绑定</span><span class="sxs-lookup"><span data-stu-id="dbd6e-117">Supporting Multiple IIS Site Bindings</span></span>](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md)  
 <span data-ttu-id="dbd6e-118">描述如何使用同一 URI 方案在一个网站上为一个服务指定多个基址。</span><span class="sxs-lookup"><span data-stu-id="dbd6e-118">Describes how to specify multiple base addresses for a service using the same URI scheme on a single Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd6e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbd6e-119">See Also</span></span>  
 [<span data-ttu-id="dbd6e-120">托管服务</span><span class="sxs-lookup"><span data-stu-id="dbd6e-120">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="dbd6e-121">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="dbd6e-121">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
