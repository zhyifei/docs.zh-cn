---
title: 在托管应用程序中承载
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 1895f6622f7c528979badd741f5994970bbd1a8c
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169794"
---
# <a name="hosting-in-a-managed-application"></a>在托管应用程序中承载
可以在任何.NET Framework 应用程序中承载 Windows Communication Foundation (WCF) 服务。 自承载服务是最灵活的宿主选项，因为此服务部署所需要的基础结构最少。 但是，它也是最不可靠宿主选项，因为托管应用程序不提供的高级宿主和管理功能，如 Internet 信息服务 (IIS) 和 Windows 服务在 WCF 中，其他托管选项。  
  
 若要创建自承载服务，请创建并打开 <xref:System.ServiceModel.ServiceHost>的实例以启动侦听消息的服务。 有关详细信息，请参阅[如何：承载于托管应用程序的 WCF 服务](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)。  
  
 有关如何定义协定、 实现协定，和托管应用程序内托管服务的完整示例请参阅[入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)并[自承载](../../../../docs/framework/wcf/samples/self-host.md)。  
  
 以下各部分描述了使用此宿主选项的常见情况。  
  
## <a name="console-applications"></a>控制台应用程序  
 自承载支持的常见方案是控制台应用程序内运行的 WCF 服务。 承载 WCF 服务中的控制台应用程序服务在开发阶段是通常很有用。 这使服务变得容易调试，从中跟踪信息以查明应用程序内发生的情况变得更加方便，以及通过将其复制到新的位置进行来回移动变得更加轻松。  
  
## <a name="rich-client-applications"></a>胖客户端应用程序  
 自承载支持是丰富的客户端应用程序，如基于 Windows Presentation Foundation (WPF) 或 Windows 窗体 (WinForms) 其他常见方案。 此宿主选项还便于丰富的客户端应用程序，如 WPF 和 WinForms 应用程序，与外界进行通信。 例如，为其用户界面中使用 WPF 和也承载 WCF 服务，允许其他客户端连接到它并共享信息的对等协作客户端。  
  
## <a name="see-also"></a>请参阅

- [托管服务](../../../../docs/framework/wcf/hosting-services.md)
- [入门教程](../../../../docs/framework/wcf/getting-started-tutorial.md)
