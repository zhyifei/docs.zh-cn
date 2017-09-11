---
title: "System.Net 类的最佳实践"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4fb997efc1ba23620cad4a63bd7fa683020a9056
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="best-practices-for-systemnet-classes"></a><span data-ttu-id="8647d-102">System.Net 类的最佳实践</span><span class="sxs-lookup"><span data-stu-id="8647d-102">Best Practices for System.Net Classes</span></span>
<span data-ttu-id="8647d-103">以下建议有助于你充分利用 <xref:System.Net> 中包含的类：</span><span class="sxs-lookup"><span data-stu-id="8647d-103">The following recommendations will help you use the classes contained in <xref:System.Net> to their best advantage:</span></span>  
  
-   <span data-ttu-id="8647d-104">要转换到子代类，请尽可能使用 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse>，而不是使用类。</span><span class="sxs-lookup"><span data-stu-id="8647d-104">Use <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> whenever possible instead of type casting to descendant classes.</span></span> <span data-ttu-id="8647d-105">使用 WebRequest 和 WebResponse 的应用程序，无需大范围修改代码，便可充分利用新的 Internet 协议。</span><span class="sxs-lookup"><span data-stu-id="8647d-105">Applications that use **WebRequest** and **WebResponse** can take advantage of new Internet protocols without needing extensive code changes.</span></span>  
  
-   <span data-ttu-id="8647d-106">用 System.Net 类编写在服务器上运行的 ASP.NET 应用程序时，从性能的角度来看，使用 <xref:System.Net.WebRequest.GetResponse%2A> 和 <xref:System.Net.WebResponse.GetResponseStream%2A> 异步方法要更好些。</span><span class="sxs-lookup"><span data-stu-id="8647d-106">When writing ASP.NET applications that run on a server using the **System.Net** classes, it is often better, from a performance standpoint, to use the asynchronous methods for <xref:System.Net.WebRequest.GetResponse%2A> and <xref:System.Net.WebResponse.GetResponseStream%2A>.</span></span>  
  
-   <span data-ttu-id="8647d-107">对 Internet 资源开放的连接数会对网络性能和吞吐量产生显著的影响。</span><span class="sxs-lookup"><span data-stu-id="8647d-107">The number of connections opened to an Internet resource can have a significant impact on network performance and throughput.</span></span> <span data-ttu-id="8647d-108">默认情况下，System.Net 在每个主机的每个应用程序中使用两个连接。</span><span class="sxs-lookup"><span data-stu-id="8647d-108">**System.Net** uses two connections per application per host by default.</span></span> <span data-ttu-id="8647d-109">为应用程序在 <xref:System.Net.ServicePoint> 中设置 <xref:System.Net.ServicePoint.ConnectionLimit%2A> 属性，可为特定主机增加此连接数。</span><span class="sxs-lookup"><span data-stu-id="8647d-109">Setting the <xref:System.Net.ServicePoint.ConnectionLimit%2A> property in the <xref:System.Net.ServicePoint> for your application can increase this number for a particular host.</span></span> <span data-ttu-id="8647d-110">设置 <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=fullName> 属性可为所有主机提高此默认设置。</span><span class="sxs-lookup"><span data-stu-id="8647d-110">Setting the <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=fullName> property can increase this default for all hosts.</span></span>  
  
-   <span data-ttu-id="8647d-111">编写套接字级别协议时，尝试尽可能使用 <xref:System.Net.Sockets.TcpClient> 或 <xref:System.Net.Sockets.UdpClient> 编写，而不是直接写入 <xref:System.Net.Sockets.Socket> 中。</span><span class="sxs-lookup"><span data-stu-id="8647d-111">When writing socket-level protocols, try to use <xref:System.Net.Sockets.TcpClient> or <xref:System.Net.Sockets.UdpClient> whenever possible instead of writing directly to a <xref:System.Net.Sockets.Socket>.</span></span> <span data-ttu-id="8647d-112">这两个客户端类封装了 TCP 和 UDP 套接字的创建，因此无需处理此连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8647d-112">These two client classes encapsulate the creation of TCP and UDP sockets without requiring you to handle the details of the connection.</span></span>  
  
-   <span data-ttu-id="8647d-113">若要访问需要凭据的站点，请使用 <xref:System.Net.CredentialCache> 类创建凭据缓存，而非为每个站点提供请求。</span><span class="sxs-lookup"><span data-stu-id="8647d-113">When accessing sites that require credentials, use the <xref:System.Net.CredentialCache> class to create a cache of credentials rather than supplying them with every request.</span></span> <span data-ttu-id="8647d-114">使用 CredentialCache 类可搜索缓存，查找符合请求的合适凭据，如此，你便无需基于 URL 创建和提供凭据。</span><span class="sxs-lookup"><span data-stu-id="8647d-114">The **CredentialCache** class searches the cache to find the appropriate credential to present with a request, relieving you of the responsibility of creating and presenting credentials based on the URL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8647d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8647d-115">See Also</span></span>  
 [<span data-ttu-id="8647d-116">.NET Framework 中的网络编程</span><span class="sxs-lookup"><span data-stu-id="8647d-116">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)

