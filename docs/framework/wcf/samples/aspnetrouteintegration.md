---
title: AspNetRouteIntegration
ms.date: 03/30/2017
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
ms.openlocfilehash: 8d9a0710e5106cbc3d02a06e81f4f8ed9ae3e03b
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43788806"
---
# <a name="aspnetrouteintegration"></a>AspNetRouteIntegration
此示例演示如何承载使用 ASP.NET 路由的 Windows Communication Foundation (WCF) REST 服务。 [基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)示例演示了此方案中的自承载的版本，并讨论了深度中的服务实现。 本主题重点介绍 ASP.NET 集成功能。 有关 ASP.NET 路由的详细信息，请参阅<xref:System.Web.Routing>。  
  
## <a name="sample-details"></a>示例详细信息  
 WCF 服务公开客户的集合资源面向/REST 的方式。 就像基于 SOAP 的 WCF 服务，可以在 ASP.NET 中使用.svc 文件承载该服务。 但是，这通常不是 HTTP 方案的首选，因为它要求该服务的 URL 中有 .svc。 此外，它还需要与服务库一起部署 .svc 文件。 通过使用 ASP.NET 路由承载该服务，可以避免这些限制，如此示例中所演示。  
  
 此示例通过在 Global.asax 文件中添加 <xref:System.ServiceModel.Activation.ServiceRoute> 而在 ASP.NET 中承载该服务。 <xref:System.ServiceModel.Activation.ServiceRoute> 指定服务的类型（此例中为“Service”）、用于该服务的服务主机工厂的类型（此例中为 <xref:System.ServiceModel.Activation.WebServiceHostFactory>）和该服务的 HTTP 基址（此例中为“~/Customers”）。  
  
 除此之外，此示例还包含一个用于添加 <xref:System.Web.Routing.UrlRoutingModule>（用于打开 ASP.NET 路由）的 Web.config，并包含该服务的配置。 具体而言，配置都配置 WCF 服务，默认值<xref:System.ServiceModel.Description.WebHttpEndpoint>，其<xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>将设置为`true`。 因此，WCF 基础结构创建的自动的基于 HTML 帮助页在`http://localhost/Customers/help`，它提供有关如何构造 HTTP 请求的信息服务以及如何访问服务的 HTTP 响应 – 例如，如何的示例客户在 XML 和 JSON 表示的详细信息。  
  
 通过以这种方式公开客户集合（一般来说是任何资源），客户端可以使用 URI 和 HTTP `GET`、`PUT`、`DELETE` 和 `POST` 以一种统一的方式与服务进行交互。  
  
 客户端项目中的 Program.cs 演示如何使用 <xref:System.Net.HttpWebRequest> 编写此类客户端。 请注意，这只是访问 WCF 服务的一种方式。 还有可能要等 WCF 通道工厂使用其他.NET Framework 类访问服务和<xref:System.Net.WebClient>。 SDK 中的其他示例 (如[基本 HTTP 服务](../../../../docs/framework/wcf/samples/basic-http-service.md)示例和[自动格式选择](../../../../docs/framework/wcf/samples/automatic-format-selection.md)示例) 演示如何使用这些类与 WCF 服务进行通信。  
  
 此示例由 3 个项目组成：  
  
 服务  
 一个 Web 应用程序项目，它包含在 ASP.NET 中承载的 WCF HTTP 服务。  
  
 客户端  
 一个对服务进行调用的控制台应用程序项目。  
  
 公共  
 一个共享库，它包含客户端和服务使用的 `Customer` 类型。 在客户端控制台应用程序运行时，客户端会向服务发出请求，并将响应中的相关信息写入控制台窗口。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中 ASP.NET 路由集成示例解决方案。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  如果尚未打开，请按"CTRL + W，S"以打开**解决方案资源管理器**窗口。  
  
4.  从**解决方案资源管理器**，右击**服务**项目，然后将光标放**调试**上下文菜单选项，以便**开始新实例**上下文菜单，然后选择**启动新实例**。  这将启动承载服务的 ASP.NET 开发服务器。  
  
5.  从**解决方案资源管理器**，右击**客户端**项目，然后将光标放**调试**上下文菜单选项，以便**新启动实例**上下文菜单，然后选择**启动新实例**。  
  
6.  出现客户端控制台窗口，该窗口提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。 可随时通过在浏览器中键入 HTML 帮助页的 URI 来查看该帮助页。 在示例运行时，客户端将写入当前活动的状态。  
  
7.  按任意键可终止客户端控制台应用程序。  
  
8.  按 Shift + F5 来停止调试服务，在 Windows 通知区域中，右键单击 ASP.NET 开发服务器图标并选择**停止**从上下文菜单。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## <a name="see-also"></a>请参阅
