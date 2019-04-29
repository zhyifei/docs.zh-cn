---
title: 部署服务
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 2c3cd17b597fafcd02b9155089bc583fafbc9dea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784977"
---
# <a name="deploying-services"></a><span data-ttu-id="eb18e-102">部署服务</span><span class="sxs-lookup"><span data-stu-id="eb18e-102">Deploying Services</span></span>
<span data-ttu-id="eb18e-103">本主题介绍如何部署到运行时环境的 Windows Communication Foundation (WCF) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb18e-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="eb18e-104">为您的应用程序选择宿主环境</span><span class="sxs-lookup"><span data-stu-id="eb18e-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="eb18e-105">WCF 服务设计为支持托管代码的任何 Windows 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="eb18e-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="eb18e-106">要变为活动状态，服务必须承载于创建它并控制它的上下文和生存期的运行时环境中。</span><span class="sxs-lookup"><span data-stu-id="eb18e-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="eb18e-107">宿主选项包括在最简单的控制台应用程序内运行，也包括在服务器环境中运行。服务器环境包括 Windows 服务、Internet 信息服务 (IIS) 或由 Windows 激活服务 (WAS) 托管的辅助进程等等。</span><span class="sxs-lookup"><span data-stu-id="eb18e-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="eb18e-108">若要查看您的 WCF 应用程序的不同托管选项，请参阅[托管服务](../../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="eb18e-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb18e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb18e-109">See also</span></span>

- [<span data-ttu-id="eb18e-110">承载</span><span class="sxs-lookup"><span data-stu-id="eb18e-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)
- [<span data-ttu-id="eb18e-111">托管服务</span><span class="sxs-lookup"><span data-stu-id="eb18e-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
