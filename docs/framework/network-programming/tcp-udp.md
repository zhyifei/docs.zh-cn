---
title: TCP-UDP
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
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: 8
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f067d24b59fbb5b49803605a625cef52d12fdbea
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="tcp-udp"></a><span data-ttu-id="b3dd7-102">TCP-UDP</span><span class="sxs-lookup"><span data-stu-id="b3dd7-102">TCP-UDP</span></span>
<span data-ttu-id="b3dd7-103">应用程序可将传输控制协议 (TCP) 及用户数据报协议 (UDP) 服务用于 <xref:System.Net.Sockets.TcpClient>、<xref:System.Net.Sockets.TcpListener> 以及 <xref:System.Net.Sockets.UdpClient> 类。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-103">Applications can use Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) services with the <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes.</span></span> <span data-ttu-id="b3dd7-104">这些协议类是在 <xref:System.Net.Sockets.Socket?displayProperty=fullName> 类的基础上建立的，并照管数据传输的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-104">These protocol classes are built on top of the <xref:System.Net.Sockets.Socket?displayProperty=fullName> class and take care of the details of transferring data.</span></span>  
  
 <span data-ttu-id="b3dd7-105">协议类使用 Socket 类的同步方法提供简单直接的网络服务访问，没有维护状态信息的开销，也无需了解设定协议特定的套接字的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-105">The protocol classes use the synchronous methods of the **Socket** class to provide simple and straightforward access to network services without the overhead of maintaining state information or knowing the details of setting up protocol-specific sockets.</span></span> <span data-ttu-id="b3dd7-106">若要使用异步 Socket 方法，可以使用 <xref:System.Net.Sockets.NetworkStream> 类提供的异步法。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-106">To use asynchronous **Socket** methods, you can use the asynchronous methods supplied by the <xref:System.Net.Sockets.NetworkStream> class.</span></span> <span data-ttu-id="b3dd7-107">若要访问未被协议类公开的 Socket 类功能，必须使用 Socket 类。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-107">To access features of the **Socket** class not exposed by the protocol classes, you must use the **Socket** class.</span></span>  
  
 <span data-ttu-id="b3dd7-108">TcpClient 和 TcpListener 代表使用 NetworkStream 类的网络。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-108">**TcpClient** and **TcpListener** represent the network using the **NetworkStream** class.</span></span> <span data-ttu-id="b3dd7-109">使用 <xref:System.Net.Sockets.TcpClient.GetStream%2A> 方法返回网络流，然后调用此流的 <xref:System.Net.Sockets.NetworkStream.Read%2A> 和 <xref:System.Net.Sockets.NetworkStream.Write%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-109">You use the <xref:System.Net.Sockets.TcpClient.GetStream%2A> method to return the network stream, and then call the stream's <xref:System.Net.Sockets.NetworkStream.Read%2A> and <xref:System.Net.Sockets.NetworkStream.Write%2A> methods.</span></span> <span data-ttu-id="b3dd7-110">NetworkStream 不拥有协议类的基础套接字，因此关闭它不会影响套接字。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-110">The **NetworkStream** does not own the protocol classes' underlying socket, so closing it does not affect the socket.</span></span>  
  
 <span data-ttu-id="b3dd7-111">UdpClient 类使用字节数组来保存 UDP 数据报。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-111">The **UdpClient** class uses an array of bytes to hold the UDP datagram.</span></span> <span data-ttu-id="b3dd7-112">使用 <xref:System.Net.Sockets.UdpClient.Send%2A> 方法向网络发送数据，并使用 <xref:System.Net.Sockets.UdpClient.Receive%2A> 方法来接收传入的数据报。</span><span class="sxs-lookup"><span data-stu-id="b3dd7-112">You use the <xref:System.Net.Sockets.UdpClient.Send%2A> method to send the data to the network and the <xref:System.Net.Sockets.UdpClient.Receive%2A> method to receive an incoming datagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3dd7-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3dd7-113">See Also</span></span>  
 <span data-ttu-id="b3dd7-114">[使用 TCP 服务](../../../docs/framework/network-programming/using-tcp-services.md) </span><span class="sxs-lookup"><span data-stu-id="b3dd7-114">[Using TCP Services](../../../docs/framework/network-programming/using-tcp-services.md) </span></span>  
 <span data-ttu-id="b3dd7-115">[使用 UDP 服务](../../../docs/framework/network-programming/using-udp-services.md) </span><span class="sxs-lookup"><span data-stu-id="b3dd7-115">[Using UDP Services](../../../docs/framework/network-programming/using-udp-services.md) </span></span>  
 <span data-ttu-id="b3dd7-116">[在网络上使用流](../../../docs/framework/network-programming/using-streams-on-the-network.md) </span><span class="sxs-lookup"><span data-stu-id="b3dd7-116">[Using Streams on the Network](../../../docs/framework/network-programming/using-streams-on-the-network.md) </span></span>  
 <span data-ttu-id="b3dd7-117">[使用异步服务器套接字](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md) </span><span class="sxs-lookup"><span data-stu-id="b3dd7-117">[Using an Asynchronous Server Socket](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md) </span></span>  
 <span data-ttu-id="b3dd7-118">[使用异步客户端套接字](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md) </span><span class="sxs-lookup"><span data-stu-id="b3dd7-118">[Using an Asynchronous Client Socket](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md) </span></span>  
 [<span data-ttu-id="b3dd7-119">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="b3dd7-119">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)

