---
title: "部署 .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, deploying
- deployment [.NET Framework]
ms.assetid: 19df26c5-4008-461d-a7d7-18f4506312d2
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1320c0364b1fdc3a67d2ac99d0591f37044c36a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="deploying-the-net-framework"></a><span data-ttu-id="72820-102">部署 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="72820-102">Deploying the .NET Framework</span></span>
<span data-ttu-id="72820-103">本部分 .NET Framework 文档所提供的信息适用于安装应用程序的同时想一并安装 .NET Framework 的开发人员，以及想在网络中部署 .NET Framework 的管理员。</span><span class="sxs-lookup"><span data-stu-id="72820-103">This section of the .NET Framework documentation provides information for developers who want to install the .NET Framework with their applications, and administrators who want to deploy the .NET Framework across a network.</span></span> <span data-ttu-id="72820-104">本文还讨论与部署相关的激活和重启问题，并介绍如何监视 .NET Framework 安装的进度。</span><span class="sxs-lookup"><span data-stu-id="72820-104">It also discusses activation and restart issues associated with deployment, and how to monitor the progress of your .NET Framework installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72820-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="72820-105">In This Section</span></span>  
 [<span data-ttu-id="72820-106">面向开发人员的部署指南</span><span class="sxs-lookup"><span data-stu-id="72820-106">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 <span data-ttu-id="72820-107">说明开发人员如何在其计算机的应用程序中安装 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="72820-107">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>  
  
 [<span data-ttu-id="72820-108">面向管理员的部署指南</span><span class="sxs-lookup"><span data-stu-id="72820-108">Deployment Guide for Administrators</span></span>](../../../docs/framework/deployment/guide-for-administrators.md)  
 <span data-ttu-id="72820-109">说明系统管理员如何通过系统中心配置管理器 (SCCM) 跨网络部署 .NET Framework 及其系统依赖项。</span><span class="sxs-lookup"><span data-stu-id="72820-109">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using System Center Configuration Manager (SCCM).</span></span>  
  
 [<span data-ttu-id="72820-110">在 .NET Framework 4.5 安装期间减少系统重新启动次数</span><span class="sxs-lookup"><span data-stu-id="72820-110">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](../../../docs/framework/deployment/reducing-system-restarts.md)  
 <span data-ttu-id="72820-111">描述在任何可能的情况下可以阻止重启的 Restart Manager，并说明安装 .NET Framework 的应用程序如何利用它。</span><span class="sxs-lookup"><span data-stu-id="72820-111">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>  
  
 [<span data-ttu-id="72820-112">如何：获取 .NET Framework 4.5 安装程序的进度</span><span class="sxs-lookup"><span data-stu-id="72820-112">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)  
 <span data-ttu-id="72820-113">描述如何在没有提示的情况下启动和跟踪 .NET Framework 安装进度，同时显示你自己的安装进度视图。</span><span class="sxs-lookup"><span data-stu-id="72820-113">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>  
  
 [<span data-ttu-id="72820-114">.NET Framework 初始化错误：管理用户体验</span><span class="sxs-lookup"><span data-stu-id="72820-114">.NET Framework Initialization Errors: Managing the User Experience</span></span>](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)  
 <span data-ttu-id="72820-115">介绍当 .NET Framework 应用程序所需的 CLR 版本无效或用户电脑上未安装该版本时会发生什么情况，如何解决这些错误以及如何控制向用户显示的错误消息。</span><span class="sxs-lookup"><span data-stu-id="72820-115">Explains what happens when a .NET Framework application requires a CLR version that's invalid or not installed on the user's computer, how to resolve these errors, and how to control the error message displayed to the user.</span></span>  
  
 [<span data-ttu-id="72820-116">如何：调试 CLR 激活问题</span><span class="sxs-lookup"><span data-stu-id="72820-116">How to: Debug CLR Activation Issues</span></span>](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md)  
 <span data-ttu-id="72820-117">介绍如何查看和调试 CLR 激活日志，解决使用正确版本的 CLR 运行应用程序时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="72820-117">Explains how you can view and debug CLR activation logs to resolve issues you may encounter in getting your application to run with the correct version of the CLR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72820-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="72820-118">See Also</span></span>  
 [<span data-ttu-id="72820-119">开发指南</span><span class="sxs-lookup"><span data-stu-id="72820-119">Development Guide</span></span>](../../../docs/framework/development-guide.md)
