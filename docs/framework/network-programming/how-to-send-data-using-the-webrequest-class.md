---
title: "如何：使用 WebRequest 类发送数据 | Microsoft Docs"
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
  - "WebRequest 类，将数据发送到主机"
  - "将数据发送到主机，使用 WebRequest 类"
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 如何：使用 WebRequest 类发送数据
下面的过程介绍使用的步骤将数据发送到服务器。  此过程是常用的数据发送到网页中。  
  
### 将数据发送到主机服务器  
  
1.  通过调用 <xref:System.Net.WebRequest.Create%2A> 创建 <xref:System.Net.WebRequest> 实例是由接受数据，例如，脚本或ASP.NET页资源的URI。  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
  
    ```  
  
    > [!NOTE]
    >  .NET Framework为URI提供从“HTTP从开始 **WebRequest** 和 **WebResponse** 派生的协议特殊化选件类: ”， “https:'' “， FTP: ”和“file: ”。  对于使用其他协议资源的访问，则必须实现从 **WebRequest** 和 **WebResponse**派生的协议特殊化选件类。  有关更多信息，请参见[对可插入协议进行编程](../../../docs/framework/network-programming/programming-pluggable-protocols.md)。  
  
2.  设置要在 **WebRequest**需要的任何属性值。  例如，启用身份验证，请设置 **凭据** 属性设置为 <xref:System.Net.NetworkCredential> 选件类的实例。  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
  
    ```  
  
     在大多数情况下， **WebRequest** 实例满足发送数据。  但是，因此，如果需要设置协议特殊化属性，必须将 **WebRequest** 到该协议特殊化类型。  例如，访问 <xref:System.Net.HttpWebRequest>HTTP特定的属性，转换为 **WebRequest** 到 **HttpWebRequest** 引用。  下面的代码示例演示如何设置HTTP特定 <xref:System.Net.HttpWebRequest.UserAgent%2A> 属性。  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  指定允许数据发送的请求的一个协议方法，例如HTTP **POST** 方法。  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  设置 **ContentLength** 属性。  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  设置 **ContentType** 属性设置为适当的值。  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  获取通过调用 <xref:System.Net.WebRequest.GetRequestStream%2A> 方法保存请求数据的流。  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  为 <xref:System.IO.Stream> 对象的数据的方法返回的写访问权。  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  通过调用 **Stream.Close** 方法关闭请求流。  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. 请求发送到服务器通过调用 <xref:System.Net.WebRequest.GetResponse%2A>。  此方法返回包含服务器的响应的对象。  返回的 <xref:System.Net.WebResponse> 目标类型取决于请求的URI的模式。  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
  
    ```  
  
    > [!NOTE]
    >  在使用完毕后 <xref:System.Net.WebResponse> 对象后，必须通过调用 <xref:System.Net.WebResponse.Close%2A> 方法将其关闭。  ，或者，如果您从响应对象获取响应流，可以通过调用 <xref:System.IO.Stream.Close%2A?displayProperty=fullName> 方法关闭流。  如果不关闭响应或流，应用程序可能用完所有与服务器的连接和变得无法处理其他的请求。  
  
10. 可以访问 **WebResponse** 的属性或转换 **WebResponse** 到协议特殊化实例读取协议特殊化属性。  例如，访问 <xref:System.Net.HttpWebResponse>HTTP特定的属性，转换为 **WebResponse** 到 **HttpWebResponse** 引用。  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. 获取包含响应数据的流发送由服务器，调用 **WebResponse**的 <xref:System.Net.WebResponse.GetResponseStream%2A> 方法。  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. 在读取响应，您的数据之后必须关闭响应流使用 **Stream.Close** 方法或关闭响应使用 **WebResponse.Close** 方法。  对响应流和 **WebResponse**的 **关闭** 方法并不是必需的，但是，这样做不会损坏的。  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
  
    ```  
  
## 示例  
  
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
  
## 请参阅  
 [创建 Internet 请求](../../../docs/framework/network-programming/creating-internet-requests.md)   
 [在网络上使用流](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [正在请求数据...](../../../docs/framework/network-programming/requesting-data.md)   
 [如何使用 WebRequest 类请求数据](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)