---
title: 如何：使用 WebRequest 类请求数据
ms.date: 03/21/2019
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
ms.openlocfilehash: 1b71327d007e66cc217f6d69e11122c481e5118f
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634032"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a><span data-ttu-id="01fde-102">如何：使用 WebRequest 类请求数据</span><span class="sxs-lookup"><span data-stu-id="01fde-102">How to: Request data by using the WebRequest class</span></span>
<span data-ttu-id="01fde-103">以下过程描述从服务器请求资源（如网页或文件）的步骤。</span><span class="sxs-lookup"><span data-stu-id="01fde-103">The following procedure describes the steps to request a resource, such as a Web page or a file, from a server.</span></span> <span data-ttu-id="01fde-104">资源必须由 URI 标识。</span><span class="sxs-lookup"><span data-stu-id="01fde-104">The resource must be identified by a URI.</span></span>  
  
## <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="01fde-105">从主机服务器请求数据</span><span class="sxs-lookup"><span data-stu-id="01fde-105">To request data from a host server</span></span>  
  
1.  <span data-ttu-id="01fde-106">通过使用资源 URI 调用 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 来创建 <xref:System.Net.WebRequest> 实例。</span><span class="sxs-lookup"><span data-stu-id="01fde-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource.</span></span> <span data-ttu-id="01fde-107">例如:</span><span class="sxs-lookup"><span data-stu-id="01fde-107">For example:</span></span> 
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/default.html");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/default.html")  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="01fde-108">.NET Framework 为以“http:”、“https:”、“ftp:”和“file:”开头的 URI 提供派生自 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 类的特定于协议的类。</span><span class="sxs-lookup"><span data-stu-id="01fde-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>
    <span data-ttu-id="01fde-109">如果需要设置或读取特定于协议的属性，必须将 <xref:System.Net.WebRequest> 或 <xref:System.Net.WebResponse> 转换为特定于协议的对象类型。</span><span class="sxs-lookup"><span data-stu-id="01fde-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="01fde-110">有关详细信息，请参阅[对可插入协议进行编程](programming-pluggable-protocols.md)。</span><span class="sxs-lookup"><span data-stu-id="01fde-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span> 
  
2.  <span data-ttu-id="01fde-111">设置 `WebRequest` 对象中任何所需的属性值。</span><span class="sxs-lookup"><span data-stu-id="01fde-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="01fde-112">例如，若要启用身份验证，则将 <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Net.NetworkCredential> 类的实例：</span><span class="sxs-lookup"><span data-stu-id="01fde-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
3.  <span data-ttu-id="01fde-113">通过调用 <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> 向服务器发送请求。</span><span class="sxs-lookup"><span data-stu-id="01fde-113">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="01fde-114">此方法返回包含服务器响应的对象。</span><span class="sxs-lookup"><span data-stu-id="01fde-114">This method returns an object containing the server's response.</span></span> <span data-ttu-id="01fde-115">返回的 <xref:System.Net.WebResponse> 对象的类型由请求的 URI 的方案决定。</span><span class="sxs-lookup"><span data-stu-id="01fde-115">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="01fde-116">例如:</span><span class="sxs-lookup"><span data-stu-id="01fde-116">For example:</span></span>
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
4.  <span data-ttu-id="01fde-117">可以访问 `WebResponse` 对象的属性或将其强制转换为特定于协议的实例，以读取特定于协议的属性。</span><span class="sxs-lookup"><span data-stu-id="01fde-117">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span> 

    <span data-ttu-id="01fde-118">例如，要访问 <xref:System.Net.HttpWebResponse> 特定于 HTTP 的属性，请将 `WebResponse` 对象强制转换为 `HttpWebResponse` 引用。</span><span class="sxs-lookup"><span data-stu-id="01fde-118">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an `HttpWebResponse` reference.</span></span> <span data-ttu-id="01fde-119">以下代码示例演示如何显示与响应一起发送的特定于 HTTP 的 <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> 属性：</span><span class="sxs-lookup"><span data-stu-id="01fde-119">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  <span data-ttu-id="01fde-120">要获取包含由服务器发送的响应数据的流，请调用 <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="01fde-120">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="01fde-121">例如:</span><span class="sxs-lookup"><span data-stu-id="01fde-121">For example:</span></span>  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  <span data-ttu-id="01fde-122">从响应对象读取数据后，可以使用 <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> 方法关闭它，也可以使用 <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 方法关闭响应流。</span><span class="sxs-lookup"><span data-stu-id="01fde-122">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="01fde-123">如果不关闭响应对象或流，则应用程序可能会耗尽服务器连接，并且无法处理其他请求。</span><span class="sxs-lookup"><span data-stu-id="01fde-123">If you don't close either the response object or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="01fde-124">因为 `WebResponse.Close` 方法在其关闭响应时调用 `Stream.Close`，所以不必在响应和流对象上调用 `Close`，尽管这样做没有坏处。</span><span class="sxs-lookup"><span data-stu-id="01fde-124">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="01fde-125">例如:</span><span class="sxs-lookup"><span data-stu-id="01fde-125">For example:</span></span>
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="01fde-126">示例</span><span class="sxs-lookup"><span data-stu-id="01fde-126">Example</span></span>  

<span data-ttu-id="01fde-127">以下代码示例演示如何创建对 Web 服务器的请求并读取其响应中的数据：</span><span class="sxs-lookup"><span data-stu-id="01fde-127">The following code example shows how to create a request to a web server and read the data in its response:</span></span>  
  
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
            // Open the stream by using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  

            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  

            // Clean up the response.  
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
            ' Open the stream by using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  

            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  

            ' Clean up the response.  
            reader.Close()  
            response.Close() 

        End Sub   

    End Class  
 
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="01fde-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="01fde-128">See also</span></span>
- [<span data-ttu-id="01fde-129">创建 Internet 请求</span><span class="sxs-lookup"><span data-stu-id="01fde-129">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="01fde-130">在网络上使用流</span><span class="sxs-lookup"><span data-stu-id="01fde-130">Using Streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="01fde-131">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="01fde-131">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="01fde-132">请求数据</span><span class="sxs-lookup"><span data-stu-id="01fde-132">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="01fde-133">如何：使用 WebRequest 类发送数据</span><span class="sxs-lookup"><span data-stu-id="01fde-133">How to: Send data by using the WebRequest class</span></span>](how-to-send-data-using-the-webrequest-class.md)
