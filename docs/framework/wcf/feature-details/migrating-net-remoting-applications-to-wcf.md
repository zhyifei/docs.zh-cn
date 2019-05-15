---
title: 将 .NET 远程处理应用程序迁移到 WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: c0ce7c9badc8bad6eedc58827b6efe2595ab2cf8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592868"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="00108-102">将 .NET 远程处理应用程序迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="00108-102">Migrating .NET Remoting Applications to WCF</span></span>
<span data-ttu-id="00108-103">**本主题介绍一项传统技术，保留该技术是为了向后兼容现有的应用程序，不建议对新的开发使用该技术。现在应使用 WCF 开发分布式应用程序。**</span><span class="sxs-lookup"><span data-stu-id="00108-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="00108-104">有两种方法来利用现有的.NET 远程处理应用程序的 WCF： 集成和迁移。</span><span class="sxs-lookup"><span data-stu-id="00108-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="00108-105">集成，可有.NET Remoting 2.0 和 WCF 并行运行，让你无需修改现有的.NET Remoting 2.0 代码同时通过这两种技术公开相同的业务对象。</span><span class="sxs-lookup"><span data-stu-id="00108-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="00108-106">集成要求运行基于.NET Framework 2.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="00108-106">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="00108-107">如果你想要利用 WCF 功能，并且不需要与 Remoting 2.0 系统的网络兼容性，可以将整个服务迁移到 WCF。</span><span class="sxs-lookup"><span data-stu-id="00108-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="00108-108">从.NET Remoting 2.0 迁移到 WCF 要求对远程对象的接口和其配置设置的更改。</span><span class="sxs-lookup"><span data-stu-id="00108-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="00108-109">这两个主题中介绍[从远程处理与 Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403)。</span><span class="sxs-lookup"><span data-stu-id="00108-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](https://go.microsoft.com/fwlink/?LinkId=74403).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00108-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="00108-110">See also</span></span>

- [<span data-ttu-id="00108-111">概念性概述</span><span class="sxs-lookup"><span data-stu-id="00108-111">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)
