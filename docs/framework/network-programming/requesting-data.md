---
title: "正在请求数据..."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bb5c79980246a9afa5a7e5024049c26815cab49d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="requesting-data"></a><span data-ttu-id="ef7f8-102">正在请求数据...</span><span class="sxs-lookup"><span data-stu-id="ef7f8-102">Requesting Data</span></span>
<span data-ttu-id="ef7f8-103">开发在如今 Internet 的分布式操作环境中运行的应用程序需要使用高效易用的方法从所有类型的资源中检索数据。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-103">Developing applications that run in the distributed operating environment of today's Internet requires an efficient, easy-to-use method for retrieving data from resources of all types.</span></span> <span data-ttu-id="ef7f8-104">可以通过可插入协议开发使用单一接口从多个 Internet 协议检索数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-104">Pluggable protocols let you develop applications that use a single interface to retrieve data from multiple Internet protocols.</span></span>  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a><span data-ttu-id="ef7f8-105">从 Internet 服务器上传和下载数据</span><span class="sxs-lookup"><span data-stu-id="ef7f8-105">Uploading and Downloading Data from an Internet Server</span></span>  
 <span data-ttu-id="ef7f8-106">对于简单的请求和响应事务，<xref:System.Net.WebClient> 类提供最简单的方法来将数据上传到 Internet 服务器或从 Internet 服务器下载数据。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-106">For simple request and response transactions, the <xref:System.Net.WebClient> class provides the easiest method for uploading data to or downloading data from an Internet server.</span></span> <span data-ttu-id="ef7f8-107">WebClient 提供用于上传和下载文件、发送和接收数据流和将数据缓冲区发送到服务器并接收响应的方法。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-107">**WebClient** provides methods for uploading and downloading files, sending and receiving streams, and sending a data buffer to the server and receiving a response.</span></span> <span data-ttu-id="ef7f8-108">WebClient 使用 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 类来实现与 Internet 资源的实际连接，因此可以使用任何已注册的可插入协议。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-108">**WebClient** uses the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes to make the actual connections to the Internet resource, so any registered pluggable protocol is available for use.</span></span>  
  
 <span data-ttu-id="ef7f8-109">需要执行更复杂事务的客户端应用程序使用 WebRequest 类及其后代从服务器请求数据。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-109">Client applications that need to make more complex transactions request data from servers using the **WebRequest** class and its descendants.</span></span> <span data-ttu-id="ef7f8-110">WebRequest 封装连接到服务器、发送请求和接收响应的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-110">**WebRequest** encapsulates the details of connecting to the server, sending the request, and receiving the response.</span></span> <span data-ttu-id="ef7f8-111">WebRequest 是一个抽象类，它定义一组使用可插入协议的所有应用程序均可使用的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-111">**WebRequest** is an abstract class that defines a set of properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="ef7f8-112">WebRequest 的后代（如 <xref:System.Net.HttpWebRequest>）通过与基础协议一致的方法实现由 WebRequest 定义的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-112">Descendants of **WebRequest**, such as <xref:System.Net.HttpWebRequest>, implement the properties and methods defined by **WebRequest** in a way that is consistent with the underlying protocol.</span></span>  
  
 <span data-ttu-id="ef7f8-113">WebRequest 类使用传递到 <xref:System.Net.WebRequest.Create%2A> 方法的 URI 值确定要创建的特定派生类实例，创建 WebRequest 后代特定于协议的实例。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-113">The **WebRequest** class creates protocol-specific instances of **WebRequest** descendants, using the value of the URI passed to its <xref:System.Net.WebRequest.Create%2A> method to determine the specific derived-class instance to create.</span></span> <span data-ttu-id="ef7f8-114">应用程序通过 <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> 方法注册 WebRequest 后代的构造函数，指示将用于处理请求的后代。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-114">Applications indicate which **WebRequest** descendant should be used to handle a request by registering the descendant's constructor with the <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ef7f8-115">通过调用 WebRequest 上的 <xref:System.Net.WebRequest.GetResponse%2A> 方法，向 Internet 资源发送请求。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-115">A request is made to the Internet resource by calling the <xref:System.Net.WebRequest.GetResponse%2A> method on the **WebRequest**.</span></span> <span data-ttu-id="ef7f8-116">GetResponse 方法从 WebRequest 的属性构造特定于协议的请求、将 TCP 或 UDP 套接字连接到服务器并发送请求。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-116">The **GetResponse** method constructs the protocol-specific request from the properties of the **WebRequest**, makes the TCP or UDP socket connection to the server, and sends the request.</span></span> <span data-ttu-id="ef7f8-117">对于将数据发送到服务器的请求（如 HTTP Post 或 FTP Put 请求），<xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> 方法提供要向其发送数据的网络数据流。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-117">For requests that send data to the server, such as HTTP **Post** or FTP **Put** requests, the <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> method provides a network stream in which to send the data.</span></span>  
  
 <span data-ttu-id="ef7f8-118">GetResponse 方法返回特定于协议的 WebResponse，后者与 WebRequest 匹配。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-118">The **GetResponse** method returns a protocol-specific **WebResponse** that matches the **WebRequest.**</span></span>  
  
 <span data-ttu-id="ef7f8-119">WebResponse 类也是一个抽象类，它定义使用可插入协议的所有应用程序均可使用的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-119">The **WebResponse** class is also an abstract class that defines properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="ef7f8-120">WebResponse 后代为基础协议实现这些属性和方法。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-120">**WebResponse** descendants implement these properties and methods for the underlying protocol.</span></span> <span data-ttu-id="ef7f8-121">例如，<xref:System.Net.HttpWebResponse> 类为 HTTP 实现 WebResponse 类。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-121">The <xref:System.Net.HttpWebResponse> class, for example, implements the **WebResponse** class for HTTP.</span></span>  
  
 <span data-ttu-id="ef7f8-122">向由 <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> 方法返回的数据流中的应用程序提供服务器返回的数据。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-122">The data returned by the server is presented to the application in the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ef7f8-123">此数据流的用法与任何其他数据流相似，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="ef7f8-123">You can use this stream like any other, as shown in the following example.</span></span>  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef7f8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef7f8-124">See Also</span></span>  
 [<span data-ttu-id="ef7f8-125">.NET Framework 中的网络编程</span><span class="sxs-lookup"><span data-stu-id="ef7f8-125">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)  
 [<span data-ttu-id="ef7f8-126">如何：请求网页并以数据流的形式检索结果</span><span class="sxs-lookup"><span data-stu-id="ef7f8-126">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>](../../../docs/framework/network-programming/how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)  
 [<span data-ttu-id="ef7f8-127">如何：检索与 WebRequest 匹配的特定于协议的 WebResponse</span><span class="sxs-lookup"><span data-stu-id="ef7f8-127">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>](../../../docs/framework/network-programming/how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
