---
title: 处理错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, WebRequest and WebResponse classes exceptions
- Status property
- WebExceptions class, about WebExceptions class
- Timeout enumeration member
- ConnectFailure enumeration member
- TrustFailure enumeration member
- WebRequest class, exceptions
- requesting data from Internet, error handling
- Success enumeration member
- receiving data, errors
- ProtocolError enumeration member
- downloading Internet resources, error handling
- WebResponse class, exceptions
- SendFailure enumeration member
- errors [.NET Framework], WebRequest and WebResponse classes exceptions
- sending data, errors
- response to Internet request, error handling
- NameResolutionFailure enumeration member
- KeepAliveFailure enumeration member
- network resources, WebRequest and WebResponse classes exceptions
- RequestCanceled enumeration member
- ReceiveFailure enumeration member
- ServerProtocolViolation enumeration member
- ConnectionClosed enumeration member
- SecureChannelFailure enumeration member
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 776e0a728b56aa2acfb7a033c2a7244b2cc824f9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2018
ms.locfileid: "47237184"
---
# <a name="handling-errors"></a><span data-ttu-id="cc781-102">处理错误</span><span class="sxs-lookup"><span data-stu-id="cc781-102">Handling Errors</span></span>
<span data-ttu-id="cc781-103"><xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 类都会引发系统异常（如 <xref:System.ArgumentException>）和特定于 Web 的异常（为 <xref:System.Net.WebRequest.GetResponse%2A> 方法所引发的 <xref:System.Net.WebException>）。</span><span class="sxs-lookup"><span data-stu-id="cc781-103">The <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes throw both system exceptions (such as <xref:System.ArgumentException>) and Web-specific exceptions (which are <xref:System.Net.WebException> thrown by the <xref:System.Net.WebRequest.GetResponse%2A> method).</span></span>  
  
 <span data-ttu-id="cc781-104">每个 WebException 包括一个 <xref:System.Net.WebException.Status%2A> 属性，它包含来自 <xref:System.Net.WebExceptionStatus> 枚举的一个值。</span><span class="sxs-lookup"><span data-stu-id="cc781-104">Each **WebException** includes a <xref:System.Net.WebException.Status%2A> property that contains a value from the <xref:System.Net.WebExceptionStatus> enumeration.</span></span> <span data-ttu-id="cc781-105">可以检查“状态”属性以确定发生的错误并采取适当的步骤解决该错误。</span><span class="sxs-lookup"><span data-stu-id="cc781-105">You can examine the **Status** property to determine the error that occurred and take the proper steps to resolve the error.</span></span>  
  
 <span data-ttu-id="cc781-106">下表描述了“状态”属性可能的值。</span><span class="sxs-lookup"><span data-stu-id="cc781-106">The following table describes the possible values for the **Status** property.</span></span>  
  
|<span data-ttu-id="cc781-107">状态</span><span class="sxs-lookup"><span data-stu-id="cc781-107">Status</span></span>|<span data-ttu-id="cc781-108">描述</span><span class="sxs-lookup"><span data-stu-id="cc781-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cc781-109">ConnectFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-109">ConnectFailure</span></span>|<span data-ttu-id="cc781-110">无法在传输级别联系远程服务。</span><span class="sxs-lookup"><span data-stu-id="cc781-110">The remote service could not be contacted at the transport level.</span></span>|  
|<span data-ttu-id="cc781-111">ConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="cc781-111">ConnectionClosed</span></span>|<span data-ttu-id="cc781-112">连接被提前关闭。</span><span class="sxs-lookup"><span data-stu-id="cc781-112">The connection was closed prematurely.</span></span>|  
|<span data-ttu-id="cc781-113">KeepAliveFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-113">KeepAliveFailure</span></span>|<span data-ttu-id="cc781-114">服务器已关闭与“保持的连接”标头设置建立的连接。</span><span class="sxs-lookup"><span data-stu-id="cc781-114">The server closed a connection made with the Keep-alive header set.</span></span>|  
|<span data-ttu-id="cc781-115">NameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-115">NameResolutionFailure</span></span>|<span data-ttu-id="cc781-116">名称服务无法解析主机名。</span><span class="sxs-lookup"><span data-stu-id="cc781-116">The name service could not resolve the host name.</span></span>|  
|<span data-ttu-id="cc781-117">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="cc781-117">ProtocolError</span></span>|<span data-ttu-id="cc781-118">从服务器接收的响应是完整的，但指示在协议级别出现错误。</span><span class="sxs-lookup"><span data-stu-id="cc781-118">The response received from the server was complete but indicated an error at the protocol level.</span></span>|  
|<span data-ttu-id="cc781-119">ReceiveFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-119">ReceiveFailure</span></span>|<span data-ttu-id="cc781-120">无法从远程服务器接收完整的响应。</span><span class="sxs-lookup"><span data-stu-id="cc781-120">A complete response was not received from the remote server.</span></span>|  
|<span data-ttu-id="cc781-121">RequestCanceled</span><span class="sxs-lookup"><span data-stu-id="cc781-121">RequestCanceled</span></span>|<span data-ttu-id="cc781-122">请求已被取消。</span><span class="sxs-lookup"><span data-stu-id="cc781-122">The request was canceled.</span></span>|  
|<span data-ttu-id="cc781-123">SecureChannelFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-123">SecureChannelFailure</span></span>|<span data-ttu-id="cc781-124">安全通道链接中出现错误。</span><span class="sxs-lookup"><span data-stu-id="cc781-124">An error occurred in a secure channel link.</span></span>|  
|<span data-ttu-id="cc781-125">SendFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-125">SendFailure</span></span>|<span data-ttu-id="cc781-126">无法向远程服务器发送完整的请求。</span><span class="sxs-lookup"><span data-stu-id="cc781-126">A complete request could not be sent to the remote server.</span></span>|  
|<span data-ttu-id="cc781-127">ServerProtocolViolation</span><span class="sxs-lookup"><span data-stu-id="cc781-127">ServerProtocolViolation</span></span>|<span data-ttu-id="cc781-128">服务器响应不是有效的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="cc781-128">The server response was not a valid HTTP response.</span></span>|  
|<span data-ttu-id="cc781-129">成功</span><span class="sxs-lookup"><span data-stu-id="cc781-129">Success</span></span>|<span data-ttu-id="cc781-130">未遇到任何错误。</span><span class="sxs-lookup"><span data-stu-id="cc781-130">No error was encountered.</span></span>|  
|<span data-ttu-id="cc781-131">超时</span><span class="sxs-lookup"><span data-stu-id="cc781-131">Timeout</span></span>|<span data-ttu-id="cc781-132">在请求的超时设置内未接收到任何响应。</span><span class="sxs-lookup"><span data-stu-id="cc781-132">No response was received within the time-out set for the request.</span></span>|  
|<span data-ttu-id="cc781-133">TrustFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-133">TrustFailure</span></span>|<span data-ttu-id="cc781-134">无法验证服务器证书。</span><span class="sxs-lookup"><span data-stu-id="cc781-134">A server certificate could not be validated.</span></span>|  
|<span data-ttu-id="cc781-135">MessageLengthLimitExceeded</span><span class="sxs-lookup"><span data-stu-id="cc781-135">MessageLengthLimitExceeded</span></span>|<span data-ttu-id="cc781-136">从服务器发送请求或接收响应时，接收到的消息超出指定限制。</span><span class="sxs-lookup"><span data-stu-id="cc781-136">A message was received that exceeded the specified limit when sending a request or receiving a response from the server.</span></span>|  
|<span data-ttu-id="cc781-137">挂起</span><span class="sxs-lookup"><span data-stu-id="cc781-137">Pending</span></span>|<span data-ttu-id="cc781-138">内部异步请求处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="cc781-138">An internal asynchronous request is pending.</span></span>|  
|<span data-ttu-id="cc781-139">PipelineFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-139">PipelineFailure</span></span>|<span data-ttu-id="cc781-140">此值支持 .NET Framework 基础结构，不能在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="cc781-140">This value supports the .NET Framework infrastructure and is not intended to be used directly in your code.</span></span>|  
|<span data-ttu-id="cc781-141">ProxyNameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="cc781-141">ProxyNameResolutionFailure</span></span>|<span data-ttu-id="cc781-142">名称解析程序服务无法解析代理主机名。</span><span class="sxs-lookup"><span data-stu-id="cc781-142">The name resolver service could not resolve the proxy host name.</span></span>|  
|<span data-ttu-id="cc781-143">UnknownError</span><span class="sxs-lookup"><span data-stu-id="cc781-143">UnknownError</span></span>|<span data-ttu-id="cc781-144">出现未知类型的异常。</span><span class="sxs-lookup"><span data-stu-id="cc781-144">An exception of unknown type has occurred.</span></span>|  
  
 <span data-ttu-id="cc781-145">当“状态”属性为“WebExceptionStatus.ProtocolError”时，可以使用包含来自服务器的响应的 WebResponse。</span><span class="sxs-lookup"><span data-stu-id="cc781-145">When the **Status** property is **WebExceptionStatus.ProtocolError**, a **WebResponse** that contains the response from the server is available.</span></span> <span data-ttu-id="cc781-146">可以检查此响应以确定协议错误的实际来源。</span><span class="sxs-lookup"><span data-stu-id="cc781-146">You can examine this response to determine the actual source of the protocol error.</span></span>  
  
 <span data-ttu-id="cc781-147">下面的示例演示如何捕获 WebException。</span><span class="sxs-lookup"><span data-stu-id="cc781-147">The following example shows how to catch a **WebException**.</span></span>  
  
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
  
 <span data-ttu-id="cc781-148">当 Windows 套接字上出现错误时，使用 <xref:System.Net.Sockets.Socket> 类的应用程序将引发 <xref:System.Net.Sockets.SocketException>。</span><span class="sxs-lookup"><span data-stu-id="cc781-148">Applications that use the <xref:System.Net.Sockets.Socket> class throw <xref:System.Net.Sockets.SocketException> when errors occur on the Windows socket.</span></span> <span data-ttu-id="cc781-149"><xref:System.Net.Sockets.TcpClient>、<xref:System.Net.Sockets.TcpListener> 和 <xref:System.Net.Sockets.UdpClient> 类在套接字类的顶层生成，并且也会引发 SocketExceptions。</span><span class="sxs-lookup"><span data-stu-id="cc781-149">The <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes are built on top of the **Socket** class and throw **SocketExceptions** as well.</span></span>  
  
 <span data-ttu-id="cc781-150">引发 SocketException 时，SocketException 类将 <xref:System.Net.Sockets.SocketException.ErrorCode%2A> 属性设置为最后一次发生的操作系统套接字错误。</span><span class="sxs-lookup"><span data-stu-id="cc781-150">When a **SocketException** is thrown, the **SocketException** class sets the <xref:System.Net.Sockets.SocketException.ErrorCode%2A> property to the last operating system socket error that occurred.</span></span> <span data-ttu-id="cc781-151">有关套接字错误代码的详细信息，请参阅 MSDN 中的 Winsock 2.0 API 错误代码文档。</span><span class="sxs-lookup"><span data-stu-id="cc781-151">For more information about socket error codes, see the Winsock 2.0 API error code documentation in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc781-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc781-152">See Also</span></span>  
 [<span data-ttu-id="cc781-153">异常处理基础知识</span><span class="sxs-lookup"><span data-stu-id="cc781-153">Exception Handling Fundamentals</span></span>](../../../docs/standard/exceptions/exception-handling-fundamentals.md)  
 [<span data-ttu-id="cc781-154">请求数据</span><span class="sxs-lookup"><span data-stu-id="cc781-154">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
