---
title: 异步操作（WCF 数据服务）
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: 01212b859e10ec1bbbb452486ce1aa6a2cecb583
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965817"
---
# <a name="asynchronous-operations-wcf-data-services"></a>异步操作（WCF 数据服务）
与内部网络中运行的应用程序相比，Web 应用程序必须适应客户端与服务器之间更长时间的延迟。 若要优化应用程序的性能和用户体验，建议你在通过 Web 访问 <xref:System.Data.Services.Client.DataServiceContext> 服务器时使用 <xref:System.Data.Services.Client.DataServiceQuery%601> 和 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 类的异步方法。  
  
 尽管 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 服务器异步处理 HTTP 请求，但是 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 客户端库的某些方法是同步的，并且会一直等到整个请求-响应交换完成后才会继续执行。 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 客户端库的异步方法不会等待此交换完成，并且允许应用程序同时保持具有响应能力的用户界面。  
  
 您可以通过<xref:System.Data.Services.Client.DataServiceContext>对和<xref:System.Data.Services.Client.DataServiceQuery%601>类使用一对方法, 分别以*Begin*和*End*开头来执行异步操作。 *Begin*方法在操作完成时注册服务调用的委托。 应在注册的委托中调用*End*方法, 以处理已完成操作的回调。 在调用*End*方法以完成异步操作时, 必须从用于开始操作的相同<xref:System.Data.Services.Client.DataServiceQuery%601>或<xref:System.Data.Services.Client.DataServiceContext>实例执行此操作。 每个*Begin*方法都`state`使用一个参数, 该参数可将一个状态对象传递给回调。 此状态对象是从与回调<xref:System.IAsyncResult>一起提供的中检索的, 用于调用相应的*结束*方法以完成异步操作。 例如，如果在对 <xref:System.Data.Services.Client.DataServiceQuery%601> 实例调用 `state` 方法时提供该实例作为 <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> 参数，那么 <xref:System.Data.Services.Client.DataServiceQuery%601> 将返回同一个 <xref:System.IAsyncResult> 实例。 随后将使用 <xref:System.Data.Services.Client.DataServiceQuery%601> 的这个实例调用 <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> 方法以完成查询操作。 有关详细信息，请参阅[如何：执行异步数据服务查询](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md)。  
  
> [!NOTE]
> .NET Framework for Silverlight 中提供的客户端库仅支持异步操作。 有关详细信息, 请参阅[WCF 数据服务 (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)。  
  
 .NET Framework 客户端库支持下列异步操作：  
  
|操作|方法|  
|---------------|-------------|  
|执行 <xref:System.Data.Services.Client.DataServiceQuery%601>。|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|从 <xref:System.Data.Services.Client.DataServiceContext> 执行查询。|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|从 <xref:System.Data.Services.Client.DataServiceContext> 执行批查询。|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|将相关实体加载到 <xref:System.Data.Services.Client.DataServiceContext> 中。|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|保存对 <xref:System.Data.Services.Client.DataServiceContext> 中对象的更改|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>异步操作的线程注意事项  
 在多线程应用程序中, 不一定会在用于调用*Begin*方法的同一线程上调用注册为异步操作回调的委托, 这会创建初始请求。 对于必须在特定线程中调用回调的应用程序, 必须将处理响应的*结束*方法的执行显式封送到所需的线程。 例如，在基于 Windows Presentation Foundation (WPF) 的应用程序和基于 Silverlight 的应用程序中，必须通过对 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 对象使用 <xref:System.Windows.Threading.Dispatcher> 方法，将响应封送回 UI 线程。 有关详细信息, 请参阅[查询数据服务 (WCF 数据服务/Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc903932(v=vs.95))。  
  
## <a name="see-also"></a>请参阅

- [WCF Data Services 客户端库](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
