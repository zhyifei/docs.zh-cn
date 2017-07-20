---
title: "使用同步客户端套接字 | Microsoft Docs"
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
  - "发送数据，套接字"
  - "数据请求，套接字"
  - "从 Internet 请求数据，套接字"
  - "同步客户端套接字"
  - "套接字类，同步客户端套接字"
  - "接收数据，套接字"
  - "套接字，同步客户端套接字"
  - "协议，套接字"
  - "Internet，套接字"
  - "客户端套接字"
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 使用同步客户端套接字
，当网络操作完成时，一个同步客户端套接字挂起应用程序。  同步套接字不适用于大量使用它们的操作的网络的应用程序，但是，它们可以启用对web服务的简单访问其他应用程序中。  
  
 若要将数据发送，请将该字节数组到某个 <xref:System.Net.Sockets.Socket> 选件类的数据发送方法\(<xref:System.Net.Sockets.Socket.Send%2A> 和 <xref:System.Net.Sockets.Socket.SendTo%2A>\)。  使用 **发送** 方法，下面的示例输入一个字符串到字节数组缓冲区 <xref:System.Text.Encoding.ASCII%2A?displayProperty=fullName> 使用属性来传达缓冲区传递给网络设备。  **发送** 方法返回字节数发送到网络设备。  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 **发送** 方法从缓冲区移除字节并排入队列。与要发送的网络接口到网络设备。  网络接口可能无法立即发送数据，但是，它将最终将其发送，因此，只要连接通常会关闭与 <xref:System.Net.Sockets.Socket.Shutdown%2A> 方法。  
  
 若要接收来自网络设备的数据，请将缓冲区某个 **套接字** 选件类接收数据方法\(<xref:System.Net.Sockets.Socket.Receive%2A> 和 <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>\)。  同步套接字将挂起应用程序，直至字节从网络接收或，直到套接字已关闭。  下面的示例接收来自网络的数据然后将其显示在控制台。  此示例假定，来自网络的数据是ASCII编码文本。  **Receive** 方法返回从网络接收字节数。  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 当套接字不再需要时，需要通过调用 <xref:System.Net.Sockets.Socket.Shutdown%2A> 然后调用方法 **关闭** 方法释放。  下面的示例释放 **套接字**。  <xref:System.Net.Sockets.SocketShutdown> 枚举定义的常数指示套接字是否应关闭的用于发送，来接收，也有两个。  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## 请参阅  
 [使用异步客户端套接字](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [使用套接字侦听](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [同步客户端套接字示例](../../../docs/framework/network-programming/synchronous-client-socket-example.md)