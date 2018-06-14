---
title: ASP.NET 缓存集成
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: 744ecbff8b51565906ff4c619ba8c8aecff123c7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805403"
---
# <a name="aspnet-caching-integration"></a>ASP.NET 缓存集成
此示例演示如何通过 WCF WEB HTTP 编程模型使用 ASP.NET 输出缓存。 请参阅[基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)自承载版本讨论深度中的服务实现此方案的示例。 本主题重点介绍 ASP.NET 输出缓存集成功能。  
  
## <a name="demonstrates"></a>演示  
 与 ASP.NET 输出缓存的集成  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a>讨论  
 此示例使用<xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>来利用 ASP.NET 输出缓存与 Windows Communication Foundation (WCF) 服务。 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> 应用于服务操作，并在应该应用于给定操作的响应的配置文件中提供缓存配置文件的名称。  
  
 在 Service.cs 文件中的示例服务项目中，同时`GetCustomer`和`GetCustomers`操作标记为<xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>，它提供缓存配置文件名称"CacheFor60Seconds"。 在服务项目的 Web.config 文件中，缓存配置文件"CacheFor60Seconds"下提供了 <`caching`> 元素的 <`system.web`>。 对于此缓存配置文件的值`duration`属性是"60"，因此与此配置文件关联的响应在 ASP.NET 输出缓存中缓存 60 秒。 此外，对于此缓存配置文件中，`varmByParam`属性设置为"format"具有不同的值是请求`format`查询字符串参数分别缓存其响应。 最后，缓存配置文件的`varyByHeader`属性设置为"Accept"，因此具有不同 Accept 标头值的请求会分别缓存其响应。  
  
 客户端项目中的 Program.cs 演示如何使用 <xref:System.Net.HttpWebRequest> 编写此类客户端。 请注意，这只是访问 WCF 服务的一种方式。 还有可能使用其他.NET Framework 类与 WCF 通道工厂类似访问服务和<xref:System.Net.WebClient>。 SDK 中的其他示例 (如[基本 HTTP 服务](../../../../docs/framework/wcf/samples/basic-http-service.md)示例和[自动格式选择](../../../../docs/framework/wcf/samples/automatic-format-selection.md)示例) 演示如何使用这些类与 WCF 服务进行通信。  
  
## <a name="to-run-the-sample"></a>运行示例  
 该示例由三个项目组成：  
  
-   **服务**： 包含在 ASP.NET 中承载的 WCF HTTP 服务的一个 Web 应用程序项目。  
  
-   **客户端**： 对服务进行调用的控制台应用程序项目。  
  
-   **常见**： 一个共享的库，包含使用客户端和服务的客户类型。  
  
 在客户端控制台应用程序运行时，客户端会对服务进行请求，并将响应中的相关信息写入控制台窗口。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  打开 ASP.NET 缓存集成示例的解决方案。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  如果**解决方案资源管理器**窗口未打开，请按 CTRL + W + S。  
  
4.  从**解决方案资源管理器**窗口中，右键单击**服务**项目，然后选择**启动新实例**。 这将启动承载服务的 ASP.NET 开发服务器。  
  
5.  从**解决方案资源管理器**窗口中，右键单击**客户端**项目，然后选择**启动新实例**。  
  
6.  出现客户端控制台窗口，该窗口提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。 可随时通过在浏览器中键入 HTML 帮助页的 URI 来查看该帮助页。  
  
7.  在示例运行时，客户端将写入当前活动的状态。  
  
8.  按任意键可终止客户端控制台应用程序。  
  
9. 按 Shift+F5 可停止调试服务。  
  
10. 在 Windows 通知区域中，右键单击 ASP.NET 开发服务器图标，然后选择**停止**。
