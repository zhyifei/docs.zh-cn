---
title: 使用安全套接字层
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Networking
- SSL
- Secure Sockets Layer
- requesting data from Internet, Secure Sockets Layer
- sending data, Secure Sockets Layer
- Network Resources
- data requests, Secure Sockets Layer
- receiving data, Secure Sockets Layer
- Internet, Secure Sockets Layer
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
ms.openlocfilehash: a0af2fa8bbe2efb2dc4fb3d1177c4950dcec87cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135794"
---
# <a name="using-secure-sockets-layer"></a><span data-ttu-id="c7dc2-102">使用安全套接字层</span><span class="sxs-lookup"><span data-stu-id="c7dc2-102">Using Secure Sockets Layer</span></span>
<span data-ttu-id="c7dc2-103"><xref:System.Net> 类使用安全套接字层 (SSL) 为若干网络协议加密连接。</span><span class="sxs-lookup"><span data-stu-id="c7dc2-103">The <xref:System.Net> classes use the Secure Sockets Layer (SSL) to encrypt the connection for several network protocols.</span></span>  
  
 <span data-ttu-id="c7dc2-104">对于 HTTP 连接，<xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 类使用 SSL 与支持 SSL 的 Web 主机进行通信。</span><span class="sxs-lookup"><span data-stu-id="c7dc2-104">For http connections, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes use SSL to communicate with web hosts that support SSL.</span></span> <span data-ttu-id="c7dc2-105">根据为其给定的 URI，<xref:System.Net.WebRequest> 类决定是否使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="c7dc2-105">The decision to use SSL is made by the <xref:System.Net.WebRequest> class, based on the URI it is given.</span></span> <span data-ttu-id="c7dc2-106">如果 URI 以“https:”开头，则使用 SSL；如果 URI 以“http:”开头，则使用未加密的连接。</span><span class="sxs-lookup"><span data-stu-id="c7dc2-106">If the URI begins with "https:", SSL is used; if the URI begins with "http:", an unencrypted connection is used.</span></span>  
  
 <span data-ttu-id="c7dc2-107">若要将 SSL 用于文件传输协议 (FTP)，请在调用 <xref:System.Net.FtpWebRequest.GetResponse> 前将 <xref:System.Net.FtpWebRequest.EnableSsl> 属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="c7dc2-107">To use SSL with File Transfer Protocol (FTP), set the <xref:System.Net.FtpWebRequest.EnableSsl> property to true prior to calling <xref:System.Net.FtpWebRequest.GetResponse>.</span></span> <span data-ttu-id="c7dc2-108">同样，要将 SSL 用于简单邮件传输协议 (SMTP)，请在发送电子邮件前将 <xref:System.Net.Mail.SmtpClient.EnableSsl> 属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="c7dc2-108">Similarly, to use SSL with Simple Mail Transport Protocol (SMTP), set the <xref:System.Net.Mail.SmtpClient.EnableSsl> property to true prior to sending the email.</span></span>  
  
 <span data-ttu-id="c7dc2-109"><xref:System.Net.Security.SslStream> 类为 SSL 提供基于流的抽象，并且提供多种配置 SSL 握手的方法。</span><span class="sxs-lookup"><span data-stu-id="c7dc2-109">The <xref:System.Net.Security.SslStream> class provides a stream-based abstraction for SSL, and offers many ways to configure the SSL handshake.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7dc2-110">示例</span><span class="sxs-lookup"><span data-stu-id="c7dc2-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="c7dc2-111">代码</span><span class="sxs-lookup"><span data-stu-id="c7dc2-111">Code</span></span>  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7dc2-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="c7dc2-112">Compiling the Code</span></span>  
 <span data-ttu-id="c7dc2-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="c7dc2-113">This example requires:</span></span>  
  
-   <span data-ttu-id="c7dc2-114">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c7dc2-114">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7dc2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7dc2-115">See also</span></span>

- [<span data-ttu-id="c7dc2-116">网络编程中的安全性</span><span class="sxs-lookup"><span data-stu-id="c7dc2-116">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)
- [<span data-ttu-id="c7dc2-117">.NET Framework 中的网络编程</span><span class="sxs-lookup"><span data-stu-id="c7dc2-117">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)
- [<span data-ttu-id="c7dc2-118">证书选择和验证</span><span class="sxs-lookup"><span data-stu-id="c7dc2-118">Certificate Selection and Validation</span></span>](../../../docs/framework/network-programming/certificate-selection-and-validation.md)
