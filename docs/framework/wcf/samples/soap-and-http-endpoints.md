---
title: "SOAP 和 HTTP 终结点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d122512a16a0959d60bfa658d96aa87a52e40299
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="soap-and-http-endpoints"></a>SOAP 和 HTTP 终结点
本示例演示如何实现基于 RPC 的服务并将其公开以 SOAP 格式和"Plain Old XML"(POX) 格式使用[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]Web 编程模型。 请参阅[基本 HTTP 服务](../../../../docs/framework/wcf/samples/basic-http-service.md)示例有关服务的 HTTP 绑定详细信息。 本示例重点介绍有关使用不同绑定通过 SOAP 和 HTTP 公开相同服务的详细信息。  
  
## <a name="demonstrates"></a>演示  
 使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 通过 SOAP 和 HTTP 公开 RPC 服务。  
  
## <a name="discussion"></a>讨论  
 本示例由两个组件组成：一个包含 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的 Web 应用程序项目（服务），以及一个使用 SOAP 和 HTTP 绑定调用服务操作的控制台应用程序（客户端）。  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务公开 2 个操作：`GetData` 和 `PutData`，后者回显作为输入传递的字符串。 这些服务操作使用 <xref:System.ServiceModel.Web.WebGetAttribute> 和 <xref:System.ServiceModel.Web.WebInvokeAttribute> 进行批注。 这些特性控制这些操作的 HTTP 投影。 此外，这些操作使用 <xref:System.ServiceModel.OperationContractAttribute> 进行批注，从而使其可以通过 SOAP 绑定进行公开。 服务的 `PutData` 方法引发 <xref:System.ServiceModel.Web.WebFaultException>，该异常使用 HTTP 状态代码通过 HTTP 发回，通过 SOAP 作为 SOAP 错误发回。  
  
 Web.config 文件通过 3 个终结点配置 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务：  
  
-   ~/service.svc/mex 终结点，公开服务元数据供基于 SOAP 的客户端访问。  
  
-   ~/service.svc/http 终结点，使客户端可以使用 HTTP 绑定访问服务。  
  
-   ~/service.svc/soap 终结点，使客户端可以使用 SOAP over HTTP 绑定访问服务。  
  
 HTTP 终结点通过 <`webHttp`> 标准终结点进行配置，该标准终结点的 `helpEnabled` 设置为 `true`。 因此，服务在 ~/service.svc/http/help 上公开基于 XHTML 的页面，基于 HTTP 的客户端可以使用该页面访问服务。  
  
 客户端项目演示如何访问使用 SOAP 代理的服务 (通过生成**添加服务引用**) 和访问服务使用<xref:System.Net.WebClient>。  
  
 该示例包含一个 Web 承载的服务和一个控制台应用程序。 在控制台应用程序运行时，客户端会对服务进行请求，并将响应中的相关信息写入控制台窗口。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  打开 SOAP 和 HTTP 终结点示例的解决方案。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  如果尚未打开，请按 CTRL + W，S 打开**解决方案资源管理器**窗口。  
  
4.  从**解决方案资源管理器**窗口中，右键单击**服务**项目，然后将光标放**调试**上下文菜单选项，以便**启动新实例**出现上下文菜单。 单击**启动新实例**。 这将启动承载服务的 ASP.NET 开发服务器。  
  
5.  从解决方案资源管理器窗口中，右键单击客户端项目，并将光标放**调试**上下文菜单选项，以便**启动新实例**出现上下文菜单。 单击**启动新实例**。  
  
6.  出现客户端控制台窗口，该窗口提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。 可随时通过在浏览器中键入 HTML 帮助页的 URI 来查看该帮助页。  
  
7.  在示例运行时，客户端将写入当前活动的状态。  
  
8.  按任意键可终止客户端控制台应用程序。  
  
9. 按 Shift+F5 可停止调试服务。  
  
10. 在 Windows 通知区域中，右击 ASP.NET 开发服务器图标并选择**停止**从上下文菜单。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
