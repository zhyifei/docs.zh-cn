---
title: 在 Internet 信息服务中承载
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 8ea7602e82d13425bb678555dde1f44ccbbf5a0f
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837462"
---
# <a name="hosting-in-internet-information-services"></a>在 Internet 信息服务中承载
承载 Windows Communication Foundation （WCF）服务的一种方法是在 Internet Information Services （IIS）应用程序中。 此托管模型与 ASP.NET 和 ASP.NET Web 服务（.ASMX） Web 服务使用的模型类似。  
  
## <a name="versions-of-iis"></a>IIS 的版本  
 可以在以下操作系统上的 IIS 版本上承载 WCF：  
  
- [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)] 上的 IIS 5.1。 此环境对于设计和开发 IIS 承载的应用程序非常有用，这些应用程序稍后将部署在 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 等服务器操作系统上。  
  
- [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]上的 IIS 6.0。 IIS 6.0 提供了一个高级的进程模型，该模型提供经过改进的可伸缩性、可靠性和应用程序隔离。 此环境适用于仅使用 HTTP 通信的 WCF 服务的生产部署。  
  
- Windows Vista 上的 IIS 7.0 和 [!INCLUDE[lserver](../../../../includes/lserver-md.md)]。 IIS 7.0 提供与 IIS 6.0 相同的高级进程模型，但使用 Windows 进程激活服务（WAS）允许通过 HTTP 以外的协议进行激活和网络通信。 此环境适用于 WCF 服务的开发，这些服务通过 WCF 支持的任何网络协议（包括 HTTP、net.tcp、net.pipe 和 net.tcp）进行通信。 有关 WAS 的详细信息，请参阅[Windows 进程激活服务中的托管](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)。  
  
- [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496)使用 IIS 7.0 和 Windows 进程激活服务（WAS）为 NET4 WCF 和 WF 服务提供丰富的应用程序宿主环境。 这些优点包括进程生命周期管理、进程回收、共享承载、快速失败保护、进程孤立、按需激活和运行状况监视。 有关详细信息，请参阅[Appfabric 托管功能](https://go.microsoft.com/fwlink/?LinkId=196494)和[appfabric 托管概念](https://go.microsoft.com/fwlink/?LinkId=196495)。  
  
## <a name="benefits-of-iis-hosting"></a>IIS 承载的好处  
 在 IIS 中承载 WCF 服务有多个优点：  
  
- IIS 中承载的 WCF 服务的部署和管理与任何其他类型的 IIS 应用程序（包括 ASP.NET 应用程序和 .ASMX）一样。  
  
- IIS 会提供进程激活、良好的管理和重复利用功能，以提高所承载应用程序的可靠性。  
  
- 与 ASP.NET 一样，ASP.NET 中托管的 WCF 服务可以利用 ASP.NET 共享的托管模型，其中，多个应用程序驻留在常见的工作进程中，以提高服务器的密度和可伸缩性。  
  
- 在 IIS 中托管的 WCF 服务使用与 ASP.NET 2.0 相同的动态编译模型，从而简化了托管服务的开发和部署。  
  
 当决定在 IIS 中承载 WCF 服务时，请记住 IIS 5.1 和 IIS 6.0 仅限于 HTTP 通信，这一点很重要。 有关选择宿主环境的详细信息，请参阅[托管服务](../../../../docs/framework/wcf/hosting-services.md)。  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>部署 IIS 承载的 WCF 服务  
 开发和部署 IIS 承载的 WCF 服务包含以下任务：  
  
- 确保正确安装并注册了 IIS、ASP.NET、WCF 和 WCF HTTP 激活组件。  
  
- 创建新的 IIS 应用程序，或重复使用现有的 ASP.NET 应用程序。  
  
- 为 WCF 服务创建 .svc 文件。  
  
- 将服务实现部署到 IIS 应用程序。  
  
- 配置 WCF 服务。  
  
 有关每项任务的讨论，请参阅[部署 Internet Information Services 承载的 WCF 服务](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)。  
  
## <a name="wcf-services-and-aspnet"></a>WCF 服务和 ASP.NET  
 WCF 服务可与 ASP.NET 或在 ASP.NET 兼容模式下并行托管，在此模式中，服务可充分利用 ASP.NET Web 应用程序平台提供的功能。 有关这些功能的讨论，请参阅[WCF 服务和 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)。  
  
## <a name="see-also"></a>另请参阅

- [使用 ServiceHostFactory 扩展宿主](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)
- [部署承载于 Internet Information Services 中的 WCF 服务](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)
- [WCF 服务和 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Internet Information Services 承载最佳做法](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [为 Windows Communication Foundation 配置 Internet Information Services 7.0](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)
- [Windows Server App Fabric 承载功能](https://go.microsoft.com/fwlink/?LinkId=201276)
