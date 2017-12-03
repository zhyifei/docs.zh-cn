---
title: "将 .NET 远程处理应用程序迁移到 WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 240901f4fa04a2468d5964821680506ea117bf7f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="a1319-102">将 .NET 远程处理应用程序迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="a1319-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="a1319-103">**本主题介绍一项传统技术，保留该技术是为了向后兼容现有的应用程序，不建议对新的开发使用该技术。现在应该使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 来开发分布式应用程序。**</span><span class="sxs-lookup"><span data-stu-id="a1319-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].**</span></span>  
  
 <span data-ttu-id="a1319-104">通过现有的 .NET Remoting 应用程序来利用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 有两种方法：集成和迁移。</span><span class="sxs-lookup"><span data-stu-id="a1319-104">There are two ways to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="a1319-105">通过集成可以并行运行 .Net Remoting 2.0 和 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，从而可以同时通过两种技术公开相同的业务对象，而不必修改现有的 .Net Remoting 2.0 代码。</span><span class="sxs-lookup"><span data-stu-id="a1319-105">Integration allows you to have .Net Remoting 2.0 and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .Net Remoting 2.0 code.</span></span> <span data-ttu-id="a1319-106">集成要求运行 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a1319-106">Integration requires that you are running on [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 or greater.</span></span> <span data-ttu-id="a1319-107">如果您想要利用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的功能而不需要与 Remoting 2.0 系统具有网络兼容性，则可以将整个服务迁移到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a1319-107">If you want to take advantage of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="a1319-108">从 .NET Remoting 2.0 迁移到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 要求更改远程对象接口及其配置设置。</span><span class="sxs-lookup"><span data-stu-id="a1319-108">Migration from .NET Remoting 2.0 to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="a1319-109">中介绍了这两这些主题[从远程处理与 Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403)。</span><span class="sxs-lookup"><span data-stu-id="a1319-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1319-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1319-110">See Also</span></span>  
 [<span data-ttu-id="a1319-111">概念性概述</span><span class="sxs-lookup"><span data-stu-id="a1319-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
