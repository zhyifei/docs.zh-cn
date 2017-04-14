---
title: "使用同步服务器套接字 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "应用程序协议，套接字"
  - "同步服务器套接字"
  - "发送数据，套接字"
  - "数据请求，套接字"
  - "从 Internet 请求数据，套接字"
  - "服务器套接字"
  - "接收数据，套接字"
  - "Socket 类，同步服务器套接字"
  - "协议，套接字"
  - "套接字，同步服务器套接字"
  - "Internet，套接字"
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 使用同步服务器套接字
同步服务器套接字挂起应用程序的执行，直到连接请求在套接字接收。  同步服务器套接字不适用于大量使用在其操作的网络的应用程序，但是，它们可以适用于简单的web应用程序。  
  
 使用 <xref:System.Net.Sockets.Socket.Bind%2A> 和 <xref:System.Net.Sockets.Socket.Listen%2A> 方法后，在 <xref:System.Net.Sockets.Socket> 在终结点设置侦听，使用 <xref:System.Net.Sockets.Socket.Accept%2A> 方法，准备好接受传入连接请求。  应用程序挂起，直到连接收到请求时， **接受** 调用方法时。  
  
 在连接收到请求时， **接受** 返回与连接的客户端的新 **套接字** 实例。  下面的示例读取客户端的数据，将其显示在控制台，然后回显数据返回到客户端。  **套接字** 未指定任何消息协议，因此字符串“\<EOF\>”标记消息数据的末尾。  假定，名为 `listener`的 **套接字** 初始化并绑定到终点。  
  
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
  
## 请参阅  
 [使用异步服务器套接字](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [同步服务器套接字示例](../../../docs/framework/network-programming/synchronous-server-socket-example.md)   
 [使用套接字侦听](../../../docs/framework/network-programming/listening-with-sockets.md)