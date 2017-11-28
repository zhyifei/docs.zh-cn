---
title: "使用同步服务器套接字"
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
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ce50fa5cf8664f93753312ee5f1db2b3058c3fd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-a-synchronous-server-socket"></a><span data-ttu-id="0193e-102">使用同步服务器套接字</span><span class="sxs-lookup"><span data-stu-id="0193e-102">Using a Synchronous Server Socket</span></span>
<span data-ttu-id="0193e-103">同步服务器套接字会挂起应用程序的执行，直到在套接字上收到连接请求。</span><span class="sxs-lookup"><span data-stu-id="0193e-103">Synchronous server sockets suspend the execution of the application until a connection request is received on the socket.</span></span> <span data-ttu-id="0193e-104">同步服务器套接字不适用于在其操作中大量使用网络的应用程序，但它们可能适用于简单的网络应用程序。</span><span class="sxs-lookup"><span data-stu-id="0193e-104">Synchronous server sockets are not suitable for applications that make heavy use of the network in their operation, but they can be suitable for simple network applications.</span></span>  
  
 <span data-ttu-id="0193e-105">使用 <xref:System.Net.Sockets.Socket.Bind%2A> 和 <xref:System.Net.Sockets.Socket.Listen%2A> 方法将 <xref:System.Net.Sockets.Socket> 设置为侦听终结点之后，便可以开始使用 <xref:System.Net.Sockets.Socket.Accept%2A> 方法接受传入的连接请求。</span><span class="sxs-lookup"><span data-stu-id="0193e-105">After a <xref:System.Net.Sockets.Socket> is set to listen on an endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> and <xref:System.Net.Sockets.Socket.Listen%2A> methods, it is ready to accept incoming connection requests using the <xref:System.Net.Sockets.Socket.Accept%2A> method.</span></span> <span data-ttu-id="0193e-106">调用 Accept 方法时，应用程序将处于挂起状态，直到收到连接请求。</span><span class="sxs-lookup"><span data-stu-id="0193e-106">The application is suspended until a connection request is received when the **Accept** method is called.</span></span>  
  
 <span data-ttu-id="0193e-107">在收到连接请求时，Accept 会返回一个与连接客户端关联的新 Socket 实例。</span><span class="sxs-lookup"><span data-stu-id="0193e-107">When a connection request is received, **Accept** returns a new **Socket** instance that is associated with the connecting client.</span></span> <span data-ttu-id="0193e-108">下面的示例从客户端读取数据，并在控制台上显示该数据，然后将数据回显到客户端。</span><span class="sxs-lookup"><span data-stu-id="0193e-108">The following example reads data from the client, displays it on the console, and echoes the data back to the client.</span></span> <span data-ttu-id="0193e-109">Socket 不指定任何消息协议，因此字符串“\<EOF>”标记消息数据的结尾。</span><span class="sxs-lookup"><span data-stu-id="0193e-109">The **Socket** does not specify any messaging protocol, so the string "\<EOF>" marks the end of the message data.</span></span> <span data-ttu-id="0193e-110">它假定名为 `listener` 的 Socket 已初始化并绑定到终结点。</span><span class="sxs-lookup"><span data-stu-id="0193e-110">It assumes that a **Socket** named `listener` has been initialized and bound to an endpoint.</span></span>  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="0193e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0193e-111">See Also</span></span>  
 [<span data-ttu-id="0193e-112">使用异步服务器套接字</span><span class="sxs-lookup"><span data-stu-id="0193e-112">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [<span data-ttu-id="0193e-113">同步服务器套接字示例</span><span class="sxs-lookup"><span data-stu-id="0193e-113">Synchronous Server Socket Example</span></span>](../../../docs/framework/network-programming/synchronous-server-socket-example.md)  
 [<span data-ttu-id="0193e-114">使用套接字侦听</span><span class="sxs-lookup"><span data-stu-id="0193e-114">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)
