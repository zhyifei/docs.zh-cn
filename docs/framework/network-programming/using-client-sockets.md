---
title: "使用客户端套接字 | Microsoft Docs"
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
  - "接收数据，套接字"
  - "Socket 类，客户端套接字"
  - "协议，套接字"
  - "Internet，套接字"
  - "套接字，客户端套接字"
  - "客户端套接字"
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 使用客户端套接字
在可以通过 <xref:System.Net.Sockets.Socket>之前开始会话，必须在应用程序中创建和远程计算机之间的数据管道。  尽管其他网络地址族和协议存在，本示例演示如何创建具有远程服务的TCP\/IP连接。  
  
 TCP\/IP使用一个网络地址和一个服务端口号唯一地标识服务。  网络地址标识网络上的特定设备;端口号标识在该计算机上特定服务连接。  网络地址和端口组合调用服务的终结点，在.NET Framework由 <xref:System.Net.EndPoint> 选件类。  **EndPoint** 后代所支持的每个地址族定义;对于IP地址族，选件类是 <xref:System.Net.IPEndPoint>。  
  
 <xref:System.Net.Dns> 选件类用于TCP\/IP Internet服务的应用程序提供域名服务。  <xref:System.Net.Dns.Resolve%2A> 方法查询DNS服务器映射到用户友好的域名\(例如“host.contoso.com”\)转换为数字、internet地址\(例如192.168.1.1\)。  **解决** 返回包含地址和别名列表请求的名称的 [IPHostEnty](frlrfsystemnetiphostentryclasstopic) 。  在许多情况下，可以在 <xref:System.Net.IPHostEntry.AddressList%2A> 数组可以使用返回的第一个地址。  下面的代码获取包含服务器的host.contoso.com <xref:System.Net.IPAddress> IP地址。  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 internet指定号码适当\(Iana\)定义常用的服务的端口号\(有关更多信息，请参见www.iana.org\/assignments\/port\-numbers\)。  其他服务可以注册了在1,024到65,535范围内的端口号。  下面的代码包含host.contoso.com的IP地址和端口号创建连接的远程终结点。  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 在确定远程计算机的地址和端口选择后为连接使用，应用程序可以尝试建立与远程计算机的连接。  下面的示例使用现有 **IPEndPoint** 连接到远程计算机并捕捉引发的所有异常。  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## 请参阅  
 [使用同步客户端套接字](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [使用异步客户端套接字](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [如何：创建套接字](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [套接字](../../../docs/framework/network-programming/sockets.md)