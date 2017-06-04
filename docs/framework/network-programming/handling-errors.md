---
title: "处理错误 | Microsoft Docs"
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
  - "Internet，WebRequest 和 WebResponse 类异常"
  - "Status 属性"
  - "WebExceptions 类，关于 WebExceptions 类"
  - "Timeout 枚举成员"
  - "ConnectFailure 枚举成员"
  - "TrustFailure 枚举成员"
  - "WebRequest 类，异常"
  - "从 Internet 请求数据，错误处理"
  - "Success 枚举成员"
  - "接收数据，错误"
  - "ProtocolError 枚举成员"
  - "下载 Internet 资源，错误处理"
  - "WebResponse 类，异常"
  - "SendFailure 枚举成员"
  - "错误 [.NET Framework]，WebRequest 和 WebResponse 类异常"
  - "发送错误，数据"
  - "响应 Internet 请求，错误处理"
  - "NameResolutionFailure 枚举成员"
  - "KeepAliveFailure 枚举成员"
  - "网络资源，WebRequest 和 WebResponse 类异常"
  - "RequestCanceled 枚举成员"
  - "ReceiveFailure 枚举成员"
  - "ServerProtocolViolation 枚举成员"
  - "ConnectionClosed 枚举成员"
  - "SecureChannelFailure 枚举成员"
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 处理错误
<xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 选件类引发。 <xref:System.Net.WebRequest.GetResponse%2A> 方法引发的 [WebExceptions](frlrfsystemnetwebexceptionclasstopic) \)的系统异常\(例如 <xref:System.ArgumentException>\)和Web特定异常\(。  
  
 每 **WebException** 包含从 <xref:System.Net.WebExceptionStatus> 枚举的值的一个 <xref:System.Net.WebException.Status%2A> 属性。  您可以检查 **状态** 属性确定生成的错误并执行适当的操作解决此错误。  
  
 下表描述 **状态** 属性的可能值。  
  
|状态|描述|  
|--------|--------|  
|ConnectFailure|会在远程服务无法联系在传输级别。|  
|ConnectionClosed|连接过早地已关闭。|  
|KeepAliveFailure|服务器关闭生成的连接。维弧标头设置。|  
|NameResolutionFailure|名称服务无法解析主机名。|  
|ProtocolError|从服务器收到的响应完成的，但指示错误发生在协议层。|  
|ReceiveFailure|没有从远程服务器接收到完整响应。|  
|RequestCanceled|该请求将被取消。|  
|SecureChannelFailure|错误在安全通道链接错误。|  
|SendFailure|未能将完整请求发送到远程服务器。|  
|ServerProtocolViolation|此服务器响应不是有效的 HTTP 响应。|  
|成功|未遇到任何错误。|  
|超时|无响应在为请求设置的超时时间内接收。|  
|TrustFailure|未能验证服务器证书。|  
|MessageLengthLimitExceeded|当发送请求或从服务器接收响应时，会接收到超出指定限制的消息。|  
|挂起|内部异步请求挂起。|  
|PipelineFailure|此值直接在代码中支持.NET Framework基础结构并且不应使用。|  
|ProxyNameResolutionFailure|名称解析服务未能解析代理主机名。|  
|UnknownError|发生未知类型的异常。|  
  
 当包含来自服务器的响应的 **状态** 属性是 **WebExceptionStatus.ProtocolError**时， **WebResponse** 可用。  您可以检查此响应确定协议错误的物理源。  
  
 下面的示例演示如何捕捉 **WebException**。  
  
```csharp  
try   
{  
    // Create a request instance.  
    WebRequest myRequest =   
    WebRequest.Create("http://www.contoso.com");  
    // Get the response.  
    WebResponse myResponse = myRequest.GetResponse();  
    //Get a readable stream from the server.   
    Stream sr = myResponse.GetResponseStream();  
  
    //Read from the stream and write any data to the console.  
    bytesread = sr.Read( myBuffer, 0, length);  
    while( bytesread > 0 )   
    {  
        for (int i=0; i<bytesread; i++) {  
            Console.Write( "{0}", myBuffer[i]);  
        }  
        Console.WriteLine();  
        bytesread = sr.Read( myBuffer, 0, length);  
    }  
    sr.Close();  
    myResponse.Close();  
}  
catch (WebException webExcp)   
{  
    // If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.");  
    // Write out the WebException message.  
    Console.WriteLine(webExcp.ToString());  
    // Get the WebException status code.  
    WebExceptionStatus status =  webExcp.Status;  
    // If status is WebExceptionStatus.ProtocolError,   
    //   there has been a protocol error and a WebResponse   
    //   should exist. Display the protocol error.  
    if (status == WebExceptionStatus.ProtocolError) {  
        Console.Write("The server returned protocol error ");  
        // Get HttpWebResponse so that you can check the HTTP status code.  
        HttpWebResponse httpResponse = (HttpWebResponse)webExcp.Response;  
        Console.WriteLine((int)httpResponse.StatusCode + " - "  
           + httpResponse.StatusCode);  
    }  
}  
catch (Exception e)   
{  
    // Code to catch other exceptions goes here.  
}  
```  
  
```vb  
Try  
    ' Create a request instance.  
    Dim myRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ' Get the response.  
    Dim myResponse As WebResponse = myRequest.GetResponse()  
    'Get a readable stream from the server.   
    Dim sr As Stream = myResponse.GetResponseStream()  
  
    Dim i As Integer      
    'Read from the stream and write any data to the console.  
    bytesread = sr.Read(myBuffer, 0, length)  
    While bytesread > 0  
        For i = 0 To bytesread - 1  
            Console.Write("{0}", myBuffer(i))  
        Next i  
        Console.WriteLine()  
        bytesread = sr.Read(myBuffer, 0, length)  
    End While  
    sr.Close()  
    myResponse.Close()  
Catch webExcp As WebException  
    ' If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.")  
    ' Write out the WebException message.  
    Console.WriteLine(webExcp.ToString())  
    ' Get the WebException status code.  
    Dim status As WebExceptionStatus = webExcp.Status  
    ' If status is WebExceptionStatus.ProtocolError,   
    '   there has been a protocol error and a WebResponse   
    '   should exist. Display the protocol error.  
    If status = WebExceptionStatus.ProtocolError Then  
        Console.Write("The server returned protocol error ")  
        ' Get HttpWebResponse so that you can check the HTTP status code.  
        Dim httpResponse As HttpWebResponse = _  
           CType(webExcp.Response, HttpWebResponse)  
        Console.WriteLine(CInt(httpResponse.StatusCode).ToString() & _  
           " - " & httpResponse.StatusCode.ToString())  
    End If  
Catch e As Exception  
    ' Code to catch other exceptions goes here.  
End Try  
```  
  
 使用 <xref:System.Net.Sockets.Socket> 选件类引发 [SocketExceptions](frlrfsystemnetsocketssocketexceptionclasstopic) 的应用程序，当错误在Windows套接字生成。  [TCPClient](frlrfsystemnetsocketstcpclientclasstopic)、 [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic)和 [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) 选件类生成。 **套接字** 选件类的顶部并引发 **SocketExceptions** 。  
  
 当 **SocketException** 引发时， **SocketException** 选件类设置 <xref:System.Net.Sockets.SocketException.ErrorCode%2A> 属性设置为最后一次发生的操作系统套接字错误。  有关套接字错误代码的更多信息，请参见MSDN的Winsock 2.0 API错误代码文档。  
  
## 请参阅  
 [异常处理基础知识](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [正在请求数据...](../../../docs/framework/network-programming/requesting-data.md)