---
title: "部署服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75069b00fa07078ff0eb2d49e64f046d5415d154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-services"></a><span data-ttu-id="e0c4b-102">部署服务</span><span class="sxs-lookup"><span data-stu-id="e0c4b-102">Deploying Services</span></span>
<span data-ttu-id="e0c4b-103">本主题介绍如何将 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 应用程序部署到运行时环境。</span><span class="sxs-lookup"><span data-stu-id="e0c4b-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="e0c4b-104">为您的应用程序选择宿主环境</span><span class="sxs-lookup"><span data-stu-id="e0c4b-104">Choosing the Hosting Environment for Your Application</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="e0c4b-105"> 服务设计为在支持托管代码的任意 Windows 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="e0c4b-105"> services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="e0c4b-106">要变为活动状态，服务必须承载于创建它并控制它的上下文和生存期的运行时环境中。</span><span class="sxs-lookup"><span data-stu-id="e0c4b-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="e0c4b-107">宿主选项包括在最简单的控制台应用程序内运行，也包括在服务器环境中运行。服务器环境包括 Windows 服务、Internet 信息服务 (IIS) 或由 Windows 激活服务 (WAS) 托管的辅助进程等等。</span><span class="sxs-lookup"><span data-stu-id="e0c4b-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="e0c4b-108">若要查看为不同的宿主选项你[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]应用程序，请参阅[托管服务](../../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e0c4b-108">To review the different hosting options for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c4b-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0c4b-109">See Also</span></span>  
 [<span data-ttu-id="e0c4b-110">承载</span><span class="sxs-lookup"><span data-stu-id="e0c4b-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="e0c4b-111">托管服务</span><span class="sxs-lookup"><span data-stu-id="e0c4b-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
