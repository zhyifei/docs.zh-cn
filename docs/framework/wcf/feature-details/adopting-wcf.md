---
title: 采用 Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: bcd6543e6cd47dc723b308acebec6f492fa14fb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="adopting-windows-communication-foundation"></a>采用 Windows Communication Foundation
你可以选择要用于新开发，Windows Communication Foundation (WCF) 时使用 ASP.NET 继续保持现有应用程序开发。 WCF 用于生成与任何方案中的.NET Framework 的应用程序之间通信最适当的选择，因为它可以充当以用于解决各种软件通信问题的方式的标准工具该 ASP.NET不能。  
  
 可以在作为现有的 ASP.NET Web 服务相同的计算机上部署新的 WCF 应用程序。 如果现有的 ASP.NET Web 服务使用的.NET Framework 2.0 版之前的版本，然后可以使用 ASP.NET IIS 注册工具有选择地将.NET Framework 2.0 部署到新的 WCF 应用程序要承载的 IIS 应用程序。 该工具记录在[ASP.NET IIS 注册工具 (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687)，并具有用户界面内置于 IIS 6.0 管理控制台。  
  
 WCF 可用来将新功能添加到现有的 ASP.NET Web 服务，通过添加配置为对在 IIS 中的现有 ASP.NET Web 服务应用程序在 ASP.NET 兼容模式中运行的 WCF 服务。 由于 ASP.NET 兼容模式，新的 WCF 服务的代码可以访问和使用中更新预先存在的 ASP.NET 代码，与相同的应用程序状态信息<xref:System.Web.HttpContext>类。 这些应用程序还可以共享相同的类库。  
  
 WCF 客户端可以使用 ASP.NET Web 服务。 使用配置的 WCF 服务<xref:System.ServiceModel.BasicHttpBinding>可由 ASP.NET Web 服务客户端。 ASP.NET Web 服务可以共存与 WCF 应用程序，并甚至可以使用 WCF 将功能添加到现有的 ASP.NET Web 服务。 有了所有的 WCF 和 ASP.NET Web 服务可以一起使用这些方法，你可能想要将 ASP.NET Web 服务迁移到 WCF，只有当你需要通过 WCF 和不是 ASP.NET Web 服务提供的功能。  
  
 即使在需要进行迁移的少数几种情况下，也请仔细考虑一下，因为将代码从一种技术迁移到另一种技术很少成为一种正确的方法。 采用新技术的原因是为了满足早期技术无法满足的新需求。在上述情况下，正确的做法是设计一个新的解决方案来满足刚刚扩展的需求集。 新的设计将受益于您对现有系统所拥有的经验以及您自该系统被设计以来获得的智慧。 此外，新设计还可以利用新技术的所有功能，而不是在新平台上再现旧设计。 在建立新设计的关键元素的原型之后，可以更轻松地在新系统中重用现有系统中的代码。  
  
 少数情况下从 ASP.NET Web 服务迁移到 WCF 的位置是正确的解决方案下, 一节将提供有关如何继续的一些指导。 其中就如何迁移服务以及如何迁移客户端提出了建议。  
  
 有关如何将现有的 ASP.NET Web 服务迁移到 WCF 的完整分析，请参阅[ASP.NET Web 服务和 Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761)。 本部分介绍如何为你的 ASP.NET Web 服务，实现兼容 WCF 服务的元数据以及如何将 ASP.NET Web 服务和客户端代码迁移到 WCF。  
  
## <a name="see-also"></a>请参阅  
 [如何：检索元数据并实现兼容服务](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [如何：将 ASP.NET Web 服务代码迁移到 Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [如何：将 ASP.NET Web 服务客户端代码迁移到 Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
