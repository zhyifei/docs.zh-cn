---
title: "在网络上使用流 | Microsoft Docs"
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
  - "从 Internet 请求数据，流"
  - "网络"
  - "响应 Internet 请求，流"
  - "网络资源，流功能"
  - "接收数据，流功能"
  - "网络资源"
  - "发送数据，流功能"
  - "下载 Internet 资源，流"
  - "流，功能"
  - "Internet，流"
  - "流"
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 在网络上使用流
网络资源。.NET Framework表示为流。  通过将被视为流泛型， .NET Framework提供以下功能:  
  
-   一种常用方法发送和接收Web数据。  哪些文件\(HTML， XML或另一个的实际内容—应用程序中使用 <xref:System.IO.Stream.Write%2A?displayProperty=fullName> 和 <xref:System.IO.Stream.Read%2A?displayProperty=fullName> 发送和接收数据。  
  
-   与流的兼容性在.NET Framework中。  流使用在.NET Framework中，已处理的它们丰富的基础结构。  例如，您可以修改读取 <xref:System.IO.FileStream> 的XML数据通过更改代码仅几行读取 <xref:System.Net.Sockets.NetworkStream> 的数据初始化流的应用程序。  **NetworkStream** 选件类和其他流之间的主要差异在于 **NetworkStream** 不seekable， <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> 属性始终返回 **false**，并且， <xref:System.Net.Sockets.NetworkStream.Seek%2A> 和 <xref:System.Net.Sockets.NetworkStream.Position%2A> 方法引发 <xref:System.NotSupportedException>。  
  
-   处理数据，到达。  流提供对数据，当从网络到达，而不是强制您的应用程序等待设置的整个数据下载。  
  
 <xref:System.Net.Sockets> 命名空间包含具体实现 <xref:System.IO.Stream> 选件类用于网络资源的 **NetworkStream** 选件类。  在 <xref:System.Net.Sockets> 命名空间的选件类使用 **NetworkStream** 选件类表示流。  
  
 使用返回的流，若要将数据发送到网络，调用您的 <xref:System.Net.WebRequest>的 <xref:System.Net.WebRequest.GetRequestStream%2A> 。  **WebRequest** 将发送请求标头到服务器，然后可以将数据发送到网络资源通过调用 <xref:System.IO.Stream.BeginWrite%2A>、 <xref:System.IO.Stream.EndWrite%2A>或 <xref:System.IO.Stream.Write%2A> 方法在返回的流。  这些协议，如HTTP，可能要求您在发送数据之前设置协议特殊化属性。  下面的代码示例演示如何设置发送的数据HTTP特定特性。  假定，可变 `sendData` 包含数据发送，而变量的 `sendLength` 是字节数发送的数据。  
  
```csharp  
HttpWebRequest request =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
request.Method = "POST";  
request.ContentLength = sendLength;  
try  
{  
   Stream sendStream = request.GetRequestStream();  
   sendStream.Write(sendData,0,sendLength);  
   sendStream.Close();  
}  
catch  
{  
   // Handle errors . . .  
}  
  
```  
  
```vb  
Dim request As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
request.Method = "POST"  
request.ContentLength = sendLength  
Try  
   Dim sendStream As Stream = request.GetRequestStream()  
   sendStream.Write(sendData, 0, sendLength)  
   sendStream.Close()  
Catch  
   ' Handle errors . . .  
End Try  
```  
  
 若要接收来自网络的数据，请调用您的 <xref:System.Net.WebResponse>的 <xref:System.Net.WebResponse.GetResponseStream%2A> 。  通过调用 <xref:System.IO.Stream.BeginRead%2A>、 <xref:System.IO.Stream.EndRead%2A>或 <xref:System.IO.Stream.Read%2A> 方法随后读取网络资源的数据返回到中的流。  
  
 在使用从网络资源的流，请注意以下几点:  
  
-   ，因为 **NetworkStream** 选件类不能更改在流，的位置 **CanSeek** 属性始终返回 **false** 。  **Seek** 和 **位置** 方法引发 **NotSupportedException**。  
  
-   当您使用 **WebRequest** 和 **WebResponse**时，调用创建的流实例 **GetResponseStream** 只读，并调用创建的流实例 **GetRequestStream** 只读。  
  
-   使用 <xref:System.IO.StreamReader> 选件类使编码更加轻松。  下面的代码示例使用 **StreamReader** 读取 **WebResponse** 的ASCII编码流\(此示例不显示创建该请求\)。  
  
-   ，如果网络资源不可用，对 **GetResponse** 的调用会阻塞。  应考虑使用 <xref:System.Net.WebRequest.BeginGetResponse%2A> 和 <xref:System.Net.WebRequest.EndGetResponse%2A> 方法的异步请求。  
  
-   ，当与服务器的连接之后，对 **GetRequestStream** 的调用会阻塞。  应考虑使用异步请求与 <xref:System.Net.WebRequest.BeginGetRequestStream%2A> 和 <xref:System.Net.WebRequest.EndGetRequestStream%2A> 方法的流。  
  
```csharp  
// Create a response object.  
WebResponse response = request.GetResponse();  
// Get a readable stream from the server.  
StreamReader sr =   
   new StreamReader(response.GetResponseStream(), Encoding.ASCII);  
// Use the stream. Remember when you are through with the stream to close it.  
sr.Close();  
```  
  
```vb  
' Create a response object.  
Dim response As WebResponse = request.GetResponse()  
' Get a readable stream from the server.  
Dim sr As _   
   New StreamReader(response.GetResponseStream(), Encoding.ASCII)  
' Use the stream. Remember when you are through with the stream to close it.  
sr.Close()  
```  
  
## 请参阅  
 [如何使用 WebRequest 类请求数据](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [正在请求数据...](../../../docs/framework/network-programming/requesting-data.md)