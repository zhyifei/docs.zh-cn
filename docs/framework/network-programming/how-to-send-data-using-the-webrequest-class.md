---
title: 如何：使用 WebRequest 类发送数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: dac372ce4f9da99b91b6f8d140d69ce9f1238f30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562890"
---
# <a name="how-to-send-data-using-the-webrequest-class"></a><span data-ttu-id="93bbc-102">如何：使用 WebRequest 类发送数据</span><span class="sxs-lookup"><span data-stu-id="93bbc-102">How to: Send Data Using the WebRequest Class</span></span>
<span data-ttu-id="93bbc-103">以下过程描述将数据发送到服务器的步骤。</span><span class="sxs-lookup"><span data-stu-id="93bbc-103">The following procedure describes the steps used to send data to a server.</span></span> <span data-ttu-id="93bbc-104">此过程通常用于将数据发布到 Web 页。</span><span class="sxs-lookup"><span data-stu-id="93bbc-104">This procedure is commonly used to post data to a Web page.</span></span>  
  
### <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="93bbc-105">将数据发送到主机服务器</span><span class="sxs-lookup"><span data-stu-id="93bbc-105">To send data to a host server</span></span>  
  
1.  <span data-ttu-id="93bbc-106">通过使用接受数据的资源的 URI（如脚本或 ASP.NET 页）来调用 <xref:System.Net.WebRequest.Create%2A> 以创建 <xref:System.Net.WebRequest> 实例。</span><span class="sxs-lookup"><span data-stu-id="93bbc-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource that accepts data, for example, a script or ASP.NET page.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="93bbc-107">.NET Framework 为以“http:”、“https:”、“ftp:”和“file:”开头的 URI 提供派生自 WebRequest 和 WebResponse 的特定于协议的类。</span><span class="sxs-lookup"><span data-stu-id="93bbc-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="93bbc-108">若要访问使用其他协议的资源，则必须实现派生自 WebRequest 和 WebResponse 的特定于协议的类。</span><span class="sxs-lookup"><span data-stu-id="93bbc-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="93bbc-109">有关详细信息，请参阅[对可插入协议进行编程](../../../docs/framework/network-programming/programming-pluggable-protocols.md)。</span><span class="sxs-lookup"><span data-stu-id="93bbc-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="93bbc-110">设置 WebRequest 中任何所需的属性值。</span><span class="sxs-lookup"><span data-stu-id="93bbc-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="93bbc-111">例如，若要启用身份验证，将 Credentials 属性设置为 <xref:System.Net.NetworkCredential> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="93bbc-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="93bbc-112">在大多数情况下，WebRequest 实例自身就足以发送数据。</span><span class="sxs-lookup"><span data-stu-id="93bbc-112">In most cases, the **WebRequest** instance itself is sufficient to send data.</span></span> <span data-ttu-id="93bbc-113">但是，如果需要设置特定于协议的属性，必须将 WebRequest 转换为特定于协议的类型。</span><span class="sxs-lookup"><span data-stu-id="93bbc-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="93bbc-114">例如，要访问 <xref:System.Net.HttpWebRequest> 特定于 HTTP 的属性，请将 WebRequest 转换为 HttpWebRequest 引用。</span><span class="sxs-lookup"><span data-stu-id="93bbc-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="93bbc-115">以下代码示例演示如何设置特定于 HTTP 的 <xref:System.Net.HttpWebRequest.UserAgent%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="93bbc-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="93bbc-116">指定允许使用请求发送数据的协议方法，如 HTTP POST 方法。</span><span class="sxs-lookup"><span data-stu-id="93bbc-116">Specify a protocol method that permits data to be sent with a request, such as the HTTP **POST** method.</span></span>  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  <span data-ttu-id="93bbc-117">设置 ContentLength 属性。</span><span class="sxs-lookup"><span data-stu-id="93bbc-117">Set the **ContentLength** property.</span></span>  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  <span data-ttu-id="93bbc-118">将 ContentType 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="93bbc-118">Set the **ContentType** property to an appropriate value.</span></span>  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  <span data-ttu-id="93bbc-119">通过调用 <xref:System.Net.WebRequest.GetRequestStream%2A> 方法获取包含请求数据的流。</span><span class="sxs-lookup"><span data-stu-id="93bbc-119">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span>  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  <span data-ttu-id="93bbc-120">将数据写入到通过此方法返回的 <xref:System.IO.Stream> 对象。</span><span class="sxs-lookup"><span data-stu-id="93bbc-120">Write the data to the <xref:System.IO.Stream> object returned by this method.</span></span>  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  <span data-ttu-id="93bbc-121">通过调用 Stream.Close 方法关闭请求流。</span><span class="sxs-lookup"><span data-stu-id="93bbc-121">Close the request stream by calling the **Stream.Close** method.</span></span>  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. <span data-ttu-id="93bbc-122">通过调用 <xref:System.Net.WebRequest.GetResponse%2A> 向服务器发送请求。</span><span class="sxs-lookup"><span data-stu-id="93bbc-122">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="93bbc-123">此方法返回包含服务器响应的对象。</span><span class="sxs-lookup"><span data-stu-id="93bbc-123">This method returns an object containing the server's response.</span></span> <span data-ttu-id="93bbc-124">返回的 <xref:System.Net.WebResponse> 对象的类型由请求的 URI 的方案决定。</span><span class="sxs-lookup"><span data-stu-id="93bbc-124">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="93bbc-125">使用完 <xref:System.Net.WebResponse> 对象后，必须通过调用 <xref:System.Net.WebResponse.Close%2A> 方法将其关闭。</span><span class="sxs-lookup"><span data-stu-id="93bbc-125">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="93bbc-126">或者，如果已从响应对象获取响应流，可以通过调用 <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 方法关闭流。</span><span class="sxs-lookup"><span data-stu-id="93bbc-126">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="93bbc-127">如果不关闭响应或流，应用程序会耗尽与服务器的连接，并无法处理其他请求。</span><span class="sxs-lookup"><span data-stu-id="93bbc-127">If you do not close the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
10. <span data-ttu-id="93bbc-128">可以访问 WebResponse 的属性或将 WebResponse 转换为特定于协议的实例来读取特定于协议的属性。</span><span class="sxs-lookup"><span data-stu-id="93bbc-128">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="93bbc-129">例如，要访问 <xref:System.Net.HttpWebResponse> 特定于 HTTP 的属性，请将 WebResponse 转换为 HttpWebResponse 引用。</span><span class="sxs-lookup"><span data-stu-id="93bbc-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to an **HttpWebResponse** reference.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. <span data-ttu-id="93bbc-130">若要获取包含由服务器发送的响应数据的流，调用 WebResponse 的 <xref:System.Net.WebResponse.GetResponseStream%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="93bbc-130">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. <span data-ttu-id="93bbc-131">从响应中读取数据之后，必须使用 Stream.Close 方法关闭响应流或使用 WebResponse.Close 方法关闭响应。</span><span class="sxs-lookup"><span data-stu-id="93bbc-131">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="93bbc-132">没必要在响应流和 WebResponse 上调用 Close 方法，但此操作是无害的。</span><span class="sxs-lookup"><span data-stu-id="93bbc-132">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="93bbc-133">示例</span><span class="sxs-lookup"><span data-stu-id="93bbc-133">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main ()  
        {  
            // Create a request using a URL that can receive a post.   
            WebRequest request = WebRequest.Create ("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  
            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes (postData);  
            // Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length;  
            // Get the request stream.  
            Stream dataStream = request.GetRequestStream ();  
            // Write the data to the request stream.  
            dataStream.Write (byteArray, 0, byteArray.Length);  
            // Close the Stream object.  
            dataStream.Close ();  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams.  
            reader.Close ();  
            dataStream.Close ();  
            response.Close ();  
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
    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  
            ' Create a request using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  
            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  
            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  
            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the Stream object.  
            dataStream.Close()  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams.  
            reader.Close()  
            dataStream.Close()  
            response.Close()  
        End Sub  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="93bbc-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="93bbc-134">See also</span></span>
- [<span data-ttu-id="93bbc-135">创建 Internet 请求</span><span class="sxs-lookup"><span data-stu-id="93bbc-135">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)
- [<span data-ttu-id="93bbc-136">在网络上使用流</span><span class="sxs-lookup"><span data-stu-id="93bbc-136">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)
- [<span data-ttu-id="93bbc-137">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="93bbc-137">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="93bbc-138">请求数据</span><span class="sxs-lookup"><span data-stu-id="93bbc-138">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
- [<span data-ttu-id="93bbc-139">如何：使用 WebRequest 类请求数据</span><span class="sxs-lookup"><span data-stu-id="93bbc-139">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
