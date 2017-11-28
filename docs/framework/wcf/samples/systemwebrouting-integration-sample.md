---
title: "SystemWebRouting 集成示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5050834ff01ebb6a25e746d88f7d328ded505cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="systemwebrouting-integration-sample"></a>SystemWebRouting 集成示例
此示例演示 <xref:System.Web.Routing> 命名空间中承载层与类的集成。 通过 <xref:System.Web.Routing> 命名空间中的类，应用程序可以使用不直接与物理资源对应的 URL。 开发人员使用 Web 路由可以为随后映射回实际 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的 HTTP 创建虚拟地址。 如果必须以不使用物理文件或资源的方式承载 WCF 服务，或者必须使用不包含 .html 或 .aspx 这类文件的 URL 访问服务时，这会十分有用。 此示例演示如何利用 <xref:System.Web.Routing.RouteTable> 类创建映射到 global.asax 中定义的运行服务的虚拟 URI。 在此示例中，有两个用 WCF 创建的两个 RSS 源：一个 `movies` 源和一个 `channels` 源。 用于激活服务的 Url 不包含扩展，并在中注册`Application_Start`方法`Global`类派生自<xref:System.Web.HttpApplication.Application_Start>类。  
  
> [!NOTE]
>  <xref:System.Web.Routing> 命名空间中的类仅适用于 HTTP 上承载的服务。  
  
> [!NOTE]
>  此示例只能在 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 中运行，因为 [!INCLUDE[iis60](../../../../includes/iis60-md.md)] 使用另一个方法支持不包含扩展名的 URL。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 WebRoutingIntegration.sln 文件。  
  
2.  若要运行解决方案并启动 Web 开发服务器，请按 F5。  
  
     出现该示例的目录列表。 请注意，不存在具有 .svc 文件扩展名的文件。  
  
3.  在地址栏中，将 `movies` 添加到 URL，使其显示为 http://localhost:[端口]/movies，然后按 Enter。  
  
     电影源显示在浏览器中。  
  
4.  在地址栏中，将 `channels` 添加到 URL，使其显示为 http://localhost:[端口]/channels，然后按 Enter。  
  
     通道源显示在浏览器中。  
  
5.  按 Alt+F4 关闭 Web 浏览器。  
  
     如果尚未退出开发服务器，右键单击通知区域图标，然后选择**停止**。  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>在 IIS 中承载时使用此示例  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 WebRoutingIntegration.sln 文件。  
  
2.  按 Ctrl+Shift+B 生成项目。  
  
3.  在 Internet 信息服务 (IIS) 管理器中创建 Web 应用程序。  
  
    1.  在 IIS 管理器中，右键单击**Default Web Site**和选择**添加应用程序**。  
  
    2.  有关**别名**，键入`WebRoutingIntegration`。  
  
    3.  有关**物理路径**，选择项目中的服务文件夹。  
  
    4.  Press **OK**.  
  
4.  右键单击 Web 应用程序并选择启动应用程序，**管理应用程序**然后**浏览**。  
  
5.  在地址栏中，将 `movies` 添加到 URL，使其显示为 http://localhost:[端口]/movies，然后按 Enter。  
  
     电影源显示在浏览器中。  
  
6.  在地址栏中，将 `channels` 添加到 URL，使其显示为 http://localhost:[端口]/channels，然后按 Enter。  
  
     通道源显示在浏览器中。  
  
7.  按 Alt+F4 关闭 Web 浏览器。  
  
 此示例演示可以在承载层中使用 <xref:System.Web.Routing> 命名空间中的类进行编写，以便对 HTTP 上承载的服务的请求进行路由。  
  
> [!NOTE]
>  如果默认应用程序池版本设置为版本 2，请将该版本更新为 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]。  
  
## <a name="see-also"></a>另请参阅  
 [AppFabric 承载和持久性示例](http://go.microsoft.com/fwlink/?LinkId=193961)
