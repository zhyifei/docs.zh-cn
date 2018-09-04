---
title: 条件 Get 和 Put
ms.date: 03/30/2017
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
ms.openlocfilehash: 29819f89327128cdd71cc89eb8d14126522dc2df
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43539378"
---
# <a name="conditional-get-and-put"></a>条件 Get 和 Put
此示例演示如何将新条件检索和更新 API 用于 WCF REST 编程模型。 由于条件检索和更新最适合面向资源的和 REST 服务，此示例扩展[基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)示例。 此示例重点介绍添加对条件检索和更新的支持[基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)示例使用新的 Api 中引入[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]。  
  
## <a name="demonstrates"></a>演示  
 条件检索和更新  
  
## <a name="discussion"></a>讨论  
 此示例中的 WCF 服务以面向资源和 REST 的方式公开客户集合。 有关服务实现的详细说明，请参阅[基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)示例。  
  
 此示例添加了条件检索和更新功能[基本资源服务](../../../../docs/framework/wcf/samples/basic-resource-service.md)示例。 条件检索和更新使用 HTTP 实体标记以及 HTTP If-None-Match 和 If-Match 标头来验证客户端是否具有给定资源的最新实体。 但是，为了正确分析 HTTP If-None-Match 和 If-Match 标头而实现该代码可能单调乏味并且容易出错。 因此，<xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 和 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 方法已添加到 <xref:System.ServiceModel.Web.IncomingWebRequestContext>（可使用 <xref:System.ServiceModel.Web.WebOperationContext> 的当前实例来访问）。 此外，`SetETag` 方法也已添加到 <xref:System.ServiceModel.Web.OutgoingWebRequestContext>，这使得返回有效的实体标记更为容易。  
  
 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 方法旨在与 [WebGet] 操作一起使用。 它将给定资源的当前实体视为 `entityTag` 参数，该参数可以是 `string`、`int`、`long` 或 `Guid`。 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 方法针对请求的 HTTP If-None-Match 标头来检查实体标记。 如果 HTTP If-None-Match 标头中存在该实体标记，则将引发状态代码为 304（未修改）的 <xref:System.ServiceModel.Web.WebFaultException>，否则该方法返回。 通过条件检索机制，客户端可以通知服务器它拥有此实体，并且只有在该客户端尚没有当前实体时才发送该实体。 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 方法的示例用法可以在该服务的 `GetCustomer` 和 `GetCustomers` 操作中看到。 需要特别注意的是，对 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 的调用可能不会返回。 开发人员应实现该操作，以便在执行对 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 的调用之前已经知道请求成功，因此，如果对 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 的调用不存在，则该服务将使用成功的状态代码来发送响应。  
  
 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 方法类似于 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 方法。 它还将使用给定资源的当前实体标记。 但是，它旨在与在其中的方法设置为"PUT"或"删除"的 [WebInvoke] 操作一起使用。 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 方法针对请求的 HTTP If-Match 标头来检查该实体标记。 如果 HTTP If-Match 标头中不存在该实体标记，则将引发状态代码为 412（前提条件失败）的 <xref:System.ServiceModel.Web.WebFaultException>。 通过条件更新机制，客户端可以通知服务器它拥有该资源的实体，并且只允许客户端更改该资源（如果它所拥有的实体为当前实体）。 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 方法的示例用法可以在该服务的 `UpdateCustomer` 和 `DeleteCustomer` 操作中看到。 就像在 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> 中那样，需要特别注意的是，对 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 的调用可能不会返回。 开发人员应实现该操作，以便在执行对 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 的调用之前已经知道请求成功，因此，如果对 <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> 的调用不存在，则该服务将使用成功状态代码加以响应。  
  
 此示例包含一个自承载服务和一个客户端，它们都在一个控制台应用程序内运行。 在控制台应用程序运行时，客户端会对服务进行请求，并将响应中的相关信息写入控制台窗口。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  打开条件 Get 和 Put 示例的解决方案。 在启动 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 时，必须以管理员身份运行才能成功执行示例。 执行此操作，请右键单击[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]图标并选择**以管理员身份运行**从上下文菜单。  
  
2.  按 Ctrl+Shift+B 生成解决方案，然后按 Ctrl+F5 运行控制台应用程序项目。 如果在启用调试的情况下运行此项目（按 F5 而不是 Ctrl+F5），则在条件 GET 和 PUT 检查引发异常时，调试器将停止。 发生这种情况时，按 F5 可继续执行示例。  
  
3.  将出现控制台窗口，它提供了正在运行的服务的 URI，以及该服务的 HTML 帮助页的 URI。  
  
4.  在示例运行时，客户端会向服务发送请求，并将响应写入控制台窗口。  
  
5.  按任何键可终止示例。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`
