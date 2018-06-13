---
title: 如何使用 WebRequest 类请求数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e02ad4772d3ba84a2735a2e146a9979862d75989
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397710"
---
# <a name="how-to-request-data-using-the-webrequest-class"></a><span data-ttu-id="5e3e5-102">如何使用 WebRequest 类请求数据</span><span class="sxs-lookup"><span data-stu-id="5e3e5-102">How to: Request Data Using the WebRequest Class</span></span>
<span data-ttu-id="5e3e5-103">以下过程描述从服务器请求资源（如 Web 页或文件）所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-103">The following procedure describes the steps used to request a resource from a server, for example, a Web page or file.</span></span> <span data-ttu-id="5e3e5-104">资源必须由 URI 标识。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-104">The resource must be identified by a URI.</span></span>  
  
### <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="5e3e5-105">从主机服务器请求数据</span><span class="sxs-lookup"><span data-stu-id="5e3e5-105">To request data from a host server</span></span>  
  
1.  <span data-ttu-id="5e3e5-106">通过使用资源 URI 调用 <xref:System.Net.WebRequest.Create%2A> 来创建 <xref:System.Net.WebRequest> 实例。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5e3e5-107">.NET Framework 为以“http:”、“https:”、“ftp:”和“file:”开头的 URI 提供派生自 WebRequest 和 WebResponse 的特定于协议的类。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="5e3e5-108">若要访问使用其他协议的资源，则必须实现派生自 WebRequest 和 WebResponse 的特定于协议的类。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="5e3e5-109">有关详细信息，请参阅[对可插入协议进行编程](../../../docs/framework/network-programming/programming-pluggable-protocols.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="5e3e5-110">设置 WebRequest 中任何所需的属性值。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="5e3e5-111">例如，若要启用身份验证，将 Credentials 属性设置为 <xref:System.Net.NetworkCredential> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="5e3e5-112">大多数情况下，WebRequest 类足以接收数据。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-112">In most cases, the **WebRequest** class is sufficient to receive data.</span></span> <span data-ttu-id="5e3e5-113">但是，如果需要设置特定于协议的属性，必须将 WebRequest 转换为特定于协议的类型。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="5e3e5-114">例如，要访问 <xref:System.Net.HttpWebRequest> 特定于 HTTP 的属性，请将 WebRequest 转换为 HttpWebRequest 引用。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="5e3e5-115">以下代码示例演示如何设置特定于 HTTP 的 <xref:System.Net.HttpWebRequest.UserAgent%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="5e3e5-116">若要向服务器发送请求，请调用 <xref:System.Net.HttpWebRequest.GetResponse%2A>。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-116">To send the request to the server, call <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="5e3e5-117">返回的 WebResponse 对象的实际类型由请求的 URI 的架构决定。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-117">The actual type of the returned **WebResponse** object is determined by the scheme of the requested URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5e3e5-118">使用完 <xref:System.Net.WebResponse> 对象后，必须通过调用 <xref:System.Net.WebResponse.Close%2A> 方法将其关闭。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-118">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="5e3e5-119">或者，如果已从响应对象获取响应流，可以通过调用 <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 方法关闭流。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-119">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5e3e5-120">如果不关闭响应或流，应用程序会耗尽与服务器的连接，并变得无法处理其他请求。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-120">If you do not close either the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
4.  <span data-ttu-id="5e3e5-121">可以访问 WebResponse 的属性或将 WebResponse 转换为特定于协议的实例来读取特定于协议的属性。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-121">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="5e3e5-122">例如，要访问 <xref:System.Net.HttpWebResponse> 特定于 HTTP 的属性，请将 WebResponse 转换为 HttpWebResponse 引用。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-122">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to a **HttpWebResponse** reference.</span></span> <span data-ttu-id="5e3e5-123">以下代码示例演示如何显示与响应一起发送的状态信息。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-123">The following code example shows how to display the status information sent with a response.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  <span data-ttu-id="5e3e5-124">若要获取包含服务器发送的响应数据的流，请使用 WebResponse 的 <xref:System.Net.HttpWebResponse.GetResponseStream%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-124">To get the stream containing response data sent by the server, use the <xref:System.Net.HttpWebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  <span data-ttu-id="5e3e5-125">从响应中读取数据之后，必须使用 Stream.Close 方法关闭响应流或使用 WebResponse.Close 方法关闭响应。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-125">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="5e3e5-126">没必要在响应流和 WebResponse 上调用 Close 方法，但此操作是无害的。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-126">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span> <span data-ttu-id="5e3e5-127">关闭响应时，WebResponse.Close 调用 Stream.Close。</span><span class="sxs-lookup"><span data-stu-id="5e3e5-127">**WebResponse.Close** calls **Stream.Close** when closing the response.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="5e3e5-128">示例</span><span class="sxs-lookup"><span data-stu-id="5e3e5-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestGetExample  
    {  
        public static void Main()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create(  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close();  
            response.Close();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestGetExample  
  
        Public Shared Sub Main()  
            ' Create a request for the URL.   
            Dim request As WebRequest = _  
              WebRequest.Create("http://www.contoso.com/default.html")  
            ' If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            Dim dataStream As Stream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams and the response.  
            reader.Close()  
            response.Close()  
        End Sub   
    End Class   
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e3e5-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e3e5-129">See Also</span></span>  
 [<span data-ttu-id="5e3e5-130">创建 Internet 请求</span><span class="sxs-lookup"><span data-stu-id="5e3e5-130">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="5e3e5-131">在网络上使用流</span><span class="sxs-lookup"><span data-stu-id="5e3e5-131">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="5e3e5-132">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="5e3e5-132">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="5e3e5-133">请求数据</span><span class="sxs-lookup"><span data-stu-id="5e3e5-133">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="5e3e5-134">如何：使用 WebRequest 类发送数据</span><span class="sxs-lookup"><span data-stu-id="5e3e5-134">How to: Send Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
