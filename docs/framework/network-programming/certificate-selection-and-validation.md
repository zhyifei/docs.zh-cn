---
title: "证书选择和验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: c933aca2-4cd0-4ff1-9df9-267143f25a6f
caps.latest.revision: 15
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6c926968b9cc5e5b0bf8db0c6bac88e676f45375
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="certificate-selection-and-validation"></a><span data-ttu-id="66b83-102">证书选择和验证</span><span class="sxs-lookup"><span data-stu-id="66b83-102">Certificate Selection and Validation</span></span>
<span data-ttu-id="66b83-103"><xref:System.Net> 类支持多种针对安全套接字层 (SSL) 连接选择和验证 <xref:System.Security.Cryptography.X509Certificates> 的方法。</span><span class="sxs-lookup"><span data-stu-id="66b83-103">The <xref:System.Net> classes support several ways to select and validate <xref:System.Security.Cryptography.X509Certificates> for Secure Socket Layer (SSL) connections.</span></span> <span data-ttu-id="66b83-104">客户端可以选择一个或多个证书对服务器自身的客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="66b83-104">A client can select one or more certificates to authenticate itself to a server.</span></span> <span data-ttu-id="66b83-105">服务器可以要求客户端证书具有一个或多个用于身份验证的特定属性。</span><span class="sxs-lookup"><span data-stu-id="66b83-105">A server can require that a client certificate have one or more specific attributes for authentication.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="66b83-106">定义</span><span class="sxs-lookup"><span data-stu-id="66b83-106">Definition</span></span>  
 <span data-ttu-id="66b83-107">证书是 ASCII 字节流，包含公钥、属性（如版本号、序列号和到期日期）以及来自证书颁发机构的数字签名。</span><span class="sxs-lookup"><span data-stu-id="66b83-107">A certificate is an ASCII byte stream that contains a public key, attributes (such as version number, serial number, and expiration date) and a digital signature from a Certificate Authority.</span></span> <span data-ttu-id="66b83-108">证书用于建立加密连接，或对服务器的客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="66b83-108">Certificates are used to establish an encrypted connection or to authenticate a client to a server.</span></span>  
  
## <a name="client-certificate-selection-and-validation"></a><span data-ttu-id="66b83-109">客户端证书选择和验证</span><span class="sxs-lookup"><span data-stu-id="66b83-109">Client Certificate Selection and Validation</span></span>  
 <span data-ttu-id="66b83-110">客户端可以选择一个或多个用于特定 SSL 连接的证书。</span><span class="sxs-lookup"><span data-stu-id="66b83-110">A client can select one or more certificates for a specific SSL connection.</span></span> <span data-ttu-id="66b83-111">客户端证书可以与 Web 服务器或 SMTP 邮件服务器的 SSL 连接相关联。</span><span class="sxs-lookup"><span data-stu-id="66b83-111">Client certificates can be associated with the SSL connection to a web server or an SMTP mail server.</span></span> <span data-ttu-id="66b83-112">客户端将证书添加到 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 或 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 类对象集合。</span><span class="sxs-lookup"><span data-stu-id="66b83-112">A client adds certificates to a collection of <xref:System.Security.Cryptography.X509Certificates.X509Certificate> or <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class objects.</span></span> <span data-ttu-id="66b83-113">以电子邮件为例，证书集合是一个与 <xref:System.Net.Mail.SmtpClient> 类的 <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A> 属性相关联的 <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection> 实例。</span><span class="sxs-lookup"><span data-stu-id="66b83-113">Using email as an example, the certificate collection is an instance of a <xref:System.Security.Cryptography.X509Certificates.X509CertificateCollection>) associated with the <xref:System.Net.Mail.SmtpClient.ClientCertificates%2A> property of the <xref:System.Net.Mail.SmtpClient> class.</span></span> <span data-ttu-id="66b83-114"><xref:System.Net.HttpWebRequest> 类具有类似的 <xref:System.Net.HttpWebRequest.ClientCertificates%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="66b83-114">The <xref:System.Net.HttpWebRequest> class has a similar <xref:System.Net.HttpWebRequest.ClientCertificates%2A> property.</span></span>  
  
 <span data-ttu-id="66b83-115"><xref:System.Security.Cryptography.X509Certificates.X509Certificate> 和 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 类的主要区别是私钥需要保存在 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 类的证书存储中。</span><span class="sxs-lookup"><span data-stu-id="66b83-115">The primary difference between the <xref:System.Security.Cryptography.X509Certificates.X509Certificate> and the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class is that the private key must reside in the certificate store for the <xref:System.Security.Cryptography.X509Certificates.X509Certificate> class.</span></span>  
  
 <span data-ttu-id="66b83-116">即使证书添加到集合并与特定 SSL 连接相关联，也不会向服务器发送任何证书，除非服务器作出请求。</span><span class="sxs-lookup"><span data-stu-id="66b83-116">Even if certificates are added to a collection and associated with a specific SSL connection, no certificates will be sent to the server unless the server requests them.</span></span> <span data-ttu-id="66b83-117">如果某个连接上设置了多个客户端证书，则将根据算法使用连接性能最好的一个，该算法会考虑由服务器提供的证书颁发者列表与客户端证书颁发者名称之间的匹配。</span><span class="sxs-lookup"><span data-stu-id="66b83-117">If multiple client certificates are set on a connection, the best one will be used based on an algorithm that considers the match between the list of certificate issuers provided by the server and the client certificate issuer name.</span></span>  
  
 <span data-ttu-id="66b83-118"><xref:System.Net.Security.SslStream> 类甚至对 SSL 握手提供了更多控制。</span><span class="sxs-lookup"><span data-stu-id="66b83-118">The <xref:System.Net.Security.SslStream> class provides even more control over the SSL handshake.</span></span> <span data-ttu-id="66b83-119">客户端可以指定委托选取要使用的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="66b83-119">A client can specify a delegate to pick which client certificate to use.</span></span>  
  
 <span data-ttu-id="66b83-120">远程服务器可以验证客户端证书是否有效、是否为最新，以及是否由适当的证书颁发机构签名。</span><span class="sxs-lookup"><span data-stu-id="66b83-120">A remote server can verify that a client certificate is valid, current, and signed by the appropriate Certificate Authority.</span></span> <span data-ttu-id="66b83-121">委托可以添加到 <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> 以强制执行证书验证。</span><span class="sxs-lookup"><span data-stu-id="66b83-121">A delegate can be added to the <xref:System.Net.ServicePointManager.ServerCertificateValidationCallback%2A> to enforce certificate validation.</span></span>  
  
## <a name="client-certificate-selection"></a><span data-ttu-id="66b83-122">客户端证书选择</span><span class="sxs-lookup"><span data-stu-id="66b83-122">Client Certificate Selection</span></span>  
 <span data-ttu-id="66b83-123">NET Framework 按以下方式选择将提供给服务器的客户端证书：</span><span class="sxs-lookup"><span data-stu-id="66b83-123">The .NET Framework selects the client certificate to present to the server in the following manner:</span></span>  
  
1.  <span data-ttu-id="66b83-124">如果之前已向服务器提供客户端证书，首次提供时，证书将被缓存，并且重复用于后续客户端证书请求。</span><span class="sxs-lookup"><span data-stu-id="66b83-124">If a client certificate was presented previously to the server, the certificate is cached when first presented and is reused for subsequent client certificate requests.</span></span>  
  
2.  <span data-ttu-id="66b83-125">如果存在委托，请始终使用委托的结果作为客户端证书的选择。</span><span class="sxs-lookup"><span data-stu-id="66b83-125">If a delegate is present, always use the result from the delegate as the client certificate to select.</span></span> <span data-ttu-id="66b83-126">若可能，请尝试使用已缓存的证书，但如果委托已返回 NULL，且证书集合不为空，请勿使用已缓存的匿名凭据。</span><span class="sxs-lookup"><span data-stu-id="66b83-126">Try to use a cached certificate when possible, but do not use cached anonymous credentials if the delegate has returned null and the certificate collection is not empty.</span></span>  
  
3.  <span data-ttu-id="66b83-127">如果这是对客户端证书的第一次质询，Framework 将枚举与连接关联的 <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 或 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 类对象中的证书，查找由服务器提供的证书颁布者列表与客户端证书颁布者名称之间的匹配。</span><span class="sxs-lookup"><span data-stu-id="66b83-127">If this is the first challenge for a client certificate, the Framework enumerates the certificates in <xref:System.Security.Cryptography.X509Certificates.X509Certificate> or the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class objects associated with the connection, looking for a match between the list of certificate issuers provided by the server and the client certificate issuer name.</span></span> <span data-ttu-id="66b83-128">匹配的第一个证书将被发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="66b83-128">The first certificate that matches is sent to the server.</span></span> <span data-ttu-id="66b83-129">如果没有证书匹配或证书集合为空，则向服务器发送匿名凭据。</span><span class="sxs-lookup"><span data-stu-id="66b83-129">If no certificate matches or the certificate collection is empty, then an anonymous credential is sent to the server.</span></span>  
  
## <a name="tools-for-certificate-configuration"></a><span data-ttu-id="66b83-130">证书配置工具</span><span class="sxs-lookup"><span data-stu-id="66b83-130">Tools for Certificate Configuration</span></span>  
 <span data-ttu-id="66b83-131">许多工具都可用于配置客户端和服务器证书。</span><span class="sxs-lookup"><span data-stu-id="66b83-131">A number of tools are available for client and server certificate configuration.</span></span>  
  
 <span data-ttu-id="66b83-132">Winhttpcertcfg.exe 工具可用于配置客户端证书。</span><span class="sxs-lookup"><span data-stu-id="66b83-132">The *Winhttpcertcfg.exe* tool can be used to configure client certificates.</span></span> <span data-ttu-id="66b83-133">Winhttpcertcfg.exe 工具作为 Windows Server 2003 Resource Kit 的工具之一提供。</span><span class="sxs-lookup"><span data-stu-id="66b83-133">The *Winhttpcertcfg.exe* tool is provided as one of the tools with the Windows Server 2003 Resource Kit.</span></span> <span data-ttu-id="66b83-134">该工具在 www.microsoft.com 上也是作为 Windows Server 2003 Resource Kit 工具的部件可供下载。</span><span class="sxs-lookup"><span data-stu-id="66b83-134">This tool is also available as a download as part of the Windows Server 2003 Resource Kit Tools at www.microsoft.com.</span></span>  
  
 <span data-ttu-id="66b83-135">HttpCfg.exe 工具可用于配置 <xref:System.Net.HttpListener> 类的服务器证书。</span><span class="sxs-lookup"><span data-stu-id="66b83-135">*The HttpCfg.exe* tool can be used to configure server certificates for the <xref:System.Net.HttpListener> class.</span></span> <span data-ttu-id="66b83-136">HttpCfg.exe 工具作为 Windows Server 2003 和 Windows XP Service Pack 2 的支持工具之一提供。</span><span class="sxs-lookup"><span data-stu-id="66b83-136">The *HttpCfg.exe* tool is provided as one of the support tools for Windows Server 2003 and Windows XP Service Pack 2.</span></span> <span data-ttu-id="66b83-137">默认情况下，Windows Server 2003 或 Windows XP 上都未安装 HttpCfg.exe 和其他支持工具。</span><span class="sxs-lookup"><span data-stu-id="66b83-137">*HttpCfg.exe* and the other support tools are not installed by default on either Windows Server 2003 or Windows XP.</span></span> <span data-ttu-id="66b83-138">在 Windows Server 2003 上，</span><span class="sxs-lookup"><span data-stu-id="66b83-138">On Windows Server 2003.</span></span> <span data-ttu-id="66b83-139">支持工具单独安装在 Windows Server 2003 CD-ROM 上的以下文件夹和文件中：</span><span class="sxs-lookup"><span data-stu-id="66b83-139">the support tools are installed separately from the following folder and file on the Windows Server 2003 CD-ROM:</span></span>  
  
 <span data-ttu-id="66b83-140">\Support\Tools\Suptools.msi</span><span class="sxs-lookup"><span data-stu-id="66b83-140">\Support\Tools\Suptools.msi</span></span>  
  
 <span data-ttu-id="66b83-141">若要使用 Windows XP Service Pack 2，可访问 www.microsoft.com 下载 Windows XP 支持工具。</span><span class="sxs-lookup"><span data-stu-id="66b83-141">For use with Windows XP Service Pack 2, the Windows XP Support Tools are available as a download from www.microsoft.com.</span></span>  
  
 <span data-ttu-id="66b83-142">HttpCfg.exe 工具版本的源代码也可用作 Windows Server SDK 的示例。</span><span class="sxs-lookup"><span data-stu-id="66b83-142">The source code to a version of the *HttpCfg.exe* tool is also provided as a sample with the Windows Server SDK.</span></span> <span data-ttu-id="66b83-143">HttpCfg.exe 示例的源代码使用网络示例作为 Windows SDK 的部件在以下文件夹中默认安装：</span><span class="sxs-lookup"><span data-stu-id="66b83-143">The source code to the *HttpCfg.exe* sample is installed by default with the networking samples as part of the Windows SDK under the following folder:</span></span>  
  
 <span data-ttu-id="66b83-144">C:\Program Files\Microsoft SDKs\Windows\v1.0\Samples\NetDS\http\serviceconfig</span><span class="sxs-lookup"><span data-stu-id="66b83-144">*C:\Program Files\Microsoft SDKs\Windows\v1.0\Samples\NetDS\http\serviceconfig*</span></span>  
  
 <span data-ttu-id="66b83-145">除了这些工具， <xref:System.Security.Cryptography.X509Certificates.X509Certificate> 和 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> 类还提供从文件系统加载证书的方法。</span><span class="sxs-lookup"><span data-stu-id="66b83-145">In addition to these tools, the <xref:System.Security.Cryptography.X509Certificates.X509Certificate> and <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> classes provides methods for loading a certificate from the file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66b83-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66b83-146">See Also</span></span>  
 <span data-ttu-id="66b83-147">[网络编程中的安全性](../../../docs/framework/network-programming/security-in-network-programming.md) </span><span class="sxs-lookup"><span data-stu-id="66b83-147">[Security in Network Programming](../../../docs/framework/network-programming/security-in-network-programming.md) </span></span>  
 [<span data-ttu-id="66b83-148">.NET Framework 中的网络编程</span><span class="sxs-lookup"><span data-stu-id="66b83-148">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)

