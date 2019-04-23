---
title: HTTP
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
ms.openlocfilehash: abbb02b7bd22c4b301c5565037f55aa1019fc3ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170594"
---
# <a name="http"></a><span data-ttu-id="46945-102">HTTP</span><span class="sxs-lookup"><span data-stu-id="46945-102">HTTP</span></span>
<span data-ttu-id="46945-103">.NET Framework 使用 <xref:System.Net.HttpWebRequest> 和 <xref:System.Net.HttpWebResponse> 类提供对 HTTP 协议的全面支持，这构成所有 Internet 通信的主体。</span><span class="sxs-lookup"><span data-stu-id="46945-103">The .NET Framework provides comprehensive support for the HTTP protocol, which makes up the majority of all Internet traffic, with the <xref:System.Net.HttpWebRequest> and <xref:System.Net.HttpWebResponse> classes.</span></span> <span data-ttu-id="46945-104">这些类派生自 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse>，默认情况下将被返回，无论静态方法 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 遇到以“http”还是“https”开头的 URI。</span><span class="sxs-lookup"><span data-stu-id="46945-104">These classes, derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, are returned by default whenever the static method <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> encounters a URI beginning with "http" or "https".</span></span> <span data-ttu-id="46945-105">大多数情况下，WebRequest 和 WebResponse 类提供发出请求的所有必需项，但如果需要访问作为属性公开的特定于 HTTP 的功能，可以将这些类转换为 HttpWebRequest 或 HttpWebResponse 类型。</span><span class="sxs-lookup"><span data-stu-id="46945-105">In most cases, the **WebRequest** and **WebResponse** classes provide all that is necessary to make the request, but if you need access to the HTTP-specific features exposed as properties, you can typecast these classes to **HttpWebRequest** or **HttpWebResponse**.</span></span>  
  
 <span data-ttu-id="46945-106">HttpWebRequest 和 HttpWebResponse 封装标准 HTTP 请求和响应事务，并提供对通用 HTTP 标头的访问。</span><span class="sxs-lookup"><span data-stu-id="46945-106">**HttpWebRequest** and **HttpWebResponse** encapsulate a standard HTTP request-and-response transaction and provide access to common HTTP headers.</span></span> <span data-ttu-id="46945-107">这些类还支持大多数 HTTP 1.1 功能，包括管道、在区块中发送和接收数据、身份验证、预身份验证、加密、代理支持、服务器证书验证和连接管理。</span><span class="sxs-lookup"><span data-stu-id="46945-107">These classes also support most HTTP 1.1 features, including pipelining, sending and receiving data in chunks, authentication, preauthentication, encryption, proxy support, server certificate validation, and connection management.</span></span> <span data-ttu-id="46945-108">自定义标头和未通过属性提供的标头可以存储在 Headers 属性并通过该属性进行访问。</span><span class="sxs-lookup"><span data-stu-id="46945-108">Custom headers and headers not provided through properties can be stored in and accessed through the **Headers** property.</span></span>  
  
 <span data-ttu-id="46945-109">HttpWebRequest 是 WebRequest 使用的默认类，并且无需注册即可将 URI 传递到 WebRequest.Create 方法。</span><span class="sxs-lookup"><span data-stu-id="46945-109">**HttpWebRequest** is the default class used by **WebRequest** and does not need to be registered before you can pass a URI to the **WebRequest.Create** method.</span></span>  
  
 <span data-ttu-id="46945-110">可以通过将 <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> 属性设置为 true（默认值）来使应用程序自动遵循 HTTP 重定向。</span><span class="sxs-lookup"><span data-stu-id="46945-110">You can make your application follow HTTP redirects automatically by setting the <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> property to **true** (the default).</span></span> <span data-ttu-id="46945-111">应用程序将重定向请求，并且 HttpWebResponse 的 <xref:System.Net.HttpWebResponse.ResponseUri%2A> 属性将包含响应请求的实际 Web 资源。</span><span class="sxs-lookup"><span data-stu-id="46945-111">The application will redirect requests, and the <xref:System.Net.HttpWebResponse.ResponseUri%2A> property of **HttpWebResponse** will contain the actual Web resource that responded to the request.</span></span> <span data-ttu-id="46945-112">如果将 AllowAutoRedirect 设置为 false，则需要应用程序能将重定向处理为 HTTP 协议错误。</span><span class="sxs-lookup"><span data-stu-id="46945-112">If you set **AllowAutoRedirect** to **false**, your application must be able to handle redirects as HTTP protocol errors.</span></span>  
  
 <span data-ttu-id="46945-113">应用程序通过捕获 <xref:System.Net.WebException>（其中 <xref:System.Net.WebException.Status%2A> 设置为 <xref:System.Net.WebExceptionStatus>）来接收 HTTP 协议错误。</span><span class="sxs-lookup"><span data-stu-id="46945-113">Applications receive HTTP protocol errors by catching a <xref:System.Net.WebException> with the <xref:System.Net.WebException.Status%2A> set to <xref:System.Net.WebExceptionStatus>.</span></span> <span data-ttu-id="46945-114"><xref:System.Net.WebException.Response%2A> 属性包含由服务器发送的 WebResponse，并指示遇到的实际 HTTP 错误。</span><span class="sxs-lookup"><span data-stu-id="46945-114">The <xref:System.Net.WebException.Response%2A> property contains the **WebResponse** sent by the server and indicates the actual HTTP error encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46945-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="46945-115">See also</span></span>

- [<span data-ttu-id="46945-116">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="46945-116">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="46945-117">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="46945-117">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="46945-118">如何：访问 HTTP 特定的属性</span><span class="sxs-lookup"><span data-stu-id="46945-118">How to: Access HTTP-Specific Properties</span></span>](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)
