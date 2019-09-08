---
title: 部署服务
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 684b781c568518cfb321d8021e4f7062e855e6aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798138"
---
# <a name="deploying-services"></a><span data-ttu-id="a84b1-102">部署服务</span><span class="sxs-lookup"><span data-stu-id="a84b1-102">Deploying Services</span></span>
<span data-ttu-id="a84b1-103">本主题介绍如何将 Windows Communication Foundation （WCF）应用程序部署到运行时环境。</span><span class="sxs-lookup"><span data-stu-id="a84b1-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="a84b1-104">为您的应用程序选择宿主环境</span><span class="sxs-lookup"><span data-stu-id="a84b1-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="a84b1-105">WCF 服务设计为在支持托管代码的任意 Windows 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="a84b1-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="a84b1-106">要变为活动状态，服务必须承载于创建它并控制它的上下文和生存期的运行时环境中。</span><span class="sxs-lookup"><span data-stu-id="a84b1-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="a84b1-107">宿主选项包括在最简单的控制台应用程序内运行，也包括在服务器环境中运行。服务器环境包括 Windows 服务、Internet 信息服务 (IIS) 或由 Windows 激活服务 (WAS) 托管的辅助进程等等。</span><span class="sxs-lookup"><span data-stu-id="a84b1-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="a84b1-108">若要查看适用于 WCF 应用程序的不同托管选项，请参阅[托管服务](../hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a84b1-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84b1-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a84b1-109">See also</span></span>

- [<span data-ttu-id="a84b1-110">承载</span><span class="sxs-lookup"><span data-stu-id="a84b1-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="a84b1-111">托管服务</span><span class="sxs-lookup"><span data-stu-id="a84b1-111">Hosting Services</span></span>](../hosting-services.md)
