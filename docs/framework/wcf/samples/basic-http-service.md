---
title: "基本 HTTP 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9da2addce9c837499783664bb3b1417d30b937b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="basic-http-service"></a>基本 HTTP 服务
此示例演示如何实现基于 HTTP 的、 基于 RPC 的服务 （一般称为"POX"(Plain Old XML) 服务） 使用[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]REST 编程模型。 此示例由两个组件组成：一个自承载 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] HTTP 服务 (Service.cs) 和一个创建服务并对该服务进行调用的控制台应用程序 (Program.cs)。  
  
## <a name="sample-details"></a>示例详细信息  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务公开 2 个操作：`EchoWithGet` 和 `EchoWithPost`，后者返回作为输入传递的字符串。  
  
 `EchoWithGet` 操作使用 <xref:System.ServiceModel.Web.WebGetAttribute> 添加批注，后者指示该操作处理 HTTP `GET` 请求。 由于 <xref:System.ServiceModel.Web.WebGetAttribute> 不显式指定 <xref:System.UriTemplate>，因此该操作需要使用名称为 `s` 的查询字符串参数来传递输入字符串。 请注意，可以使用 <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A> 属性来自定义服务所需的 URI 格式。  
  
 `EchoWithPost` 操作使用 <xref:System.ServiceModel.Web.WebInvokeAttribute> 添加批注，后者指示该操作不是 `GET` 操作（它具有副作用）。 由于 <xref:System.ServiceModel.Web.WebInvokeAttribute> 不显式指定 `Method`，因此该操作处理在请求正文中具有字符串（例如，以 XML 格式）的 HTTP `POST` 请求。 请注意，可分别使用 <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> 和 <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate> 属性来自定义该请求的 URI 的 HTTP 方法和格式。  
  
 App.config 文件使用 <xref:System.ServiceModel.Description.WebHttpEndpoint> 属性设置为 <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> 的默认 `true` 来配置 WCF 服务。 因此，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 基础结构在 `http://localhost:8000/Customers/help` 创建一个基于 HTML 的自动帮助页，该帮助页提供有关如何构造该服务的 HTTP 请求以及如何使用该服务的 HTTP 响应的信息。  
  
 Program.cs 演示如何将 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 通道工厂用于对服务和进程响应进行调用。 请注意，这只是访问 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的一种方式。 还可以使用其他 .NET Framework 类（如 <xref:System.Net.HttpWebRequest> 和 <xref:System.Net.WebClient>）来访问该服务。 SDK 中的其他示例 (如[自动格式选择](../../../../docs/framework/wcf/samples/automatic-format-selection.md)示例和[基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)示例) 演示如何使用这些类与通信[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]服务。  
  
 此示例包含一个自承载服务和一个客户端，它们都在一个控制台应用程序内运行。 在控制台应用程序运行时，客户端会对服务进行请求，并将响应中的相关信息写入控制台窗口。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  打开基本 HTTP 服务示例的解决方案。 在启动 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 时，必须以管理员身份运行才能成功执行该示例。 执行此操作，请右键单击[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]图标并选择**以管理员身份运行**从上下文菜单。  
  
2.  按 Ctrl+Shilf+B 生成解决方案，然后按 Ctrl+F5 运行控制台应用程序而不进行调试。 将出现控制台窗口，它提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。 可随时通过在浏览器中键入 HTML 帮助页的 URI 来查看该帮助页。 在示例运行时，客户端将写入当前活动的状态。  
  
3.  按任何键可终止示例。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## <a name="see-also"></a>另请参阅  
 [自动格式选择](../../../../docs/framework/wcf/samples/automatic-format-selection.md)  
 [基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)
