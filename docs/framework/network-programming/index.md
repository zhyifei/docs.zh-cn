---
title: ".NET Framework 中的网络编程"
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
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
caps.latest.revision: 24
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4b63aeadb795e5457266bd75d1f2bf0e695eac7f
ms.contentlocale: zh-cn
ms.lasthandoff: 09/07/2017

---
# <a name="network-programming-in-the-net-framework"></a><span data-ttu-id="255b2-102">.NET Framework 中的网络编程</span><span class="sxs-lookup"><span data-stu-id="255b2-102">Network Programming in the .NET Framework</span></span>
<span data-ttu-id="255b2-103">Microsoft .NET Framework 为 Internet 服务提供了一种分层、可扩展且托管的实现，可以快速、轻松地将其集成到你的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="255b2-103">The Microsoft .NET Framework provides a layered, extensible, and managed implementation of Internet services that can be quickly and easily integrated into your applications.</span></span> <span data-ttu-id="255b2-104">你的网络应用程序可以基于可插入协议而构建，以便自动利用新的 Internet 协议，或者，它们可以使用 Windows 套接字接口的托管实现在套接字级别上使用网络。</span><span class="sxs-lookup"><span data-stu-id="255b2-104">Your network applications can build on pluggable protocols to automatically take advantage of new Internet protocols, or they can use a managed implementation of the Windows socket interface to work with the network on the socket level.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="255b2-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="255b2-105">In This Section</span></span>  
 [<span data-ttu-id="255b2-106">可插入协议简介</span><span class="sxs-lookup"><span data-stu-id="255b2-106">Introducing Pluggable Protocols</span></span>](../../../docs/framework/network-programming/introducing-pluggable-protocols.md)  
 <span data-ttu-id="255b2-107">描述如何访问 Internet 资源而不考虑它所需的访问协议。</span><span class="sxs-lookup"><span data-stu-id="255b2-107">Describes how to access an Internet resource without regard to the access protocol that it requires.</span></span>  
  
 [<span data-ttu-id="255b2-108">请求数据</span><span class="sxs-lookup"><span data-stu-id="255b2-108">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 <span data-ttu-id="255b2-109">说明如何使用可插入协议上载数据和从 Internet 资源下载数据。</span><span class="sxs-lookup"><span data-stu-id="255b2-109">Explains how to use pluggable protocols to upload and download data from Internet resources.</span></span>  
  
 [<span data-ttu-id="255b2-110">对可插入协议进行编程</span><span class="sxs-lookup"><span data-stu-id="255b2-110">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)  
 <span data-ttu-id="255b2-111">说明如何派生协议特定的类以实现可插入协议。</span><span class="sxs-lookup"><span data-stu-id="255b2-111">Explains how to derive protocol-specific classes to implement pluggable protocols.</span></span>  
  
 [<span data-ttu-id="255b2-112">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="255b2-112">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 <span data-ttu-id="255b2-113">描述利用 TCP、UDP 和 HTTP 等网络协议的编程应用程序。</span><span class="sxs-lookup"><span data-stu-id="255b2-113">Describes programming applications that take advantage of network protocols such as TCP, UDP, and HTTP.</span></span>  
  
 [<span data-ttu-id="255b2-114">Internet 协议版本 6</span><span class="sxs-lookup"><span data-stu-id="255b2-114">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 <span data-ttu-id="255b2-115">描述 Internet 协议版本 6 (IPv6) 相对于当前的 Internet 协议套件版本 (IPv4) 的优势，描述 IPv6 寻址、路由和自动配置，以及如何启用和禁用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="255b2-115">Describes the advantages of Internet Protocol version 6 (IPv6) over the current version of the Internet Protocol suite (IPv4), describes IPv6 addressing, routing and auto-configuration, and how to enable and disable IPv6.</span></span>  
  
 [<span data-ttu-id="255b2-116">配置 Internet 应用程序</span><span class="sxs-lookup"><span data-stu-id="255b2-116">Configuring Internet Applications</span></span>](../../../docs/framework/network-programming/configuring-internet-applications.md)  
 <span data-ttu-id="255b2-117">说明如何使用 .NET Framework 配置文件来配置 Internet 应用程序。</span><span class="sxs-lookup"><span data-stu-id="255b2-117">Explains how to use the .NET Framework configuration files to configure Internet applications.</span></span>  
  
 [<span data-ttu-id="255b2-118">.NET Framework 中的网络跟踪</span><span class="sxs-lookup"><span data-stu-id="255b2-118">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 <span data-ttu-id="255b2-119">说明如何使用网络跟踪来获取有关方法调用的信息，以及有关托管应用程序所生成网络流量的信息。</span><span class="sxs-lookup"><span data-stu-id="255b2-119">Explains how to use network tracing to get information about method invocations and network traffic generated by a managed application.</span></span>  
  
 [<span data-ttu-id="255b2-120">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="255b2-120">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 <span data-ttu-id="255b2-121">描述如何使用应用程序（采用 <xref:System.Net.WebClient?displayProperty=fullName>、 <xref:System.Net.WebRequest?displayProperty=fullName>和 <xref:System.Net.HttpWebRequest?displayProperty=fullName> 类）的缓存。</span><span class="sxs-lookup"><span data-stu-id="255b2-121">Describes how to use caching for applications that use the <xref:System.Net.WebClient?displayProperty=fullName>, <xref:System.Net.WebRequest?displayProperty=fullName>, and <xref:System.Net.HttpWebRequest?displayProperty=fullName> classes.</span></span>  
  
 [<span data-ttu-id="255b2-122">网络编程中的安全性</span><span class="sxs-lookup"><span data-stu-id="255b2-122">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)  
 <span data-ttu-id="255b2-123">描述如何使用 Internet 标准安全性和身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="255b2-123">Describes how to use standard Internet security and authentication techniques.</span></span>  
  
 [<span data-ttu-id="255b2-124">System.Net 类的最佳实践</span><span class="sxs-lookup"><span data-stu-id="255b2-124">Best Practices for System.Net Classes</span></span>](../../../docs/framework/network-programming/best-practices-for-system-net-classes.md)  
 <span data-ttu-id="255b2-125">提供关于如何充分利用 Internet 应用程序的提示和技巧。</span><span class="sxs-lookup"><span data-stu-id="255b2-125">Provides tips and tricks for getting the most out of your Internet applications.</span></span>  
  
 [<span data-ttu-id="255b2-126">通过代理访问 Internet</span><span class="sxs-lookup"><span data-stu-id="255b2-126">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 <span data-ttu-id="255b2-127">描述如何配置代理。</span><span class="sxs-lookup"><span data-stu-id="255b2-127">Describes how to configure proxies.</span></span>  
  
 [<span data-ttu-id="255b2-128">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="255b2-128">NetworkInformation</span></span>](../../../docs/framework/network-programming/networkinformation.md)  
 <span data-ttu-id="255b2-129">描述如何收集有关网络事件、更改、统计信息和属性的信息，并说明如何使用 <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName> 类确定远程主机是否可到达。</span><span class="sxs-lookup"><span data-stu-id="255b2-129">Describes how to gather information about network events, changes, statistics, and properties and also explains how to determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName> class.</span></span>  
  
 [<span data-ttu-id="255b2-130">对 2.0 版中的 System.Uri 命名空间的更改</span><span class="sxs-lookup"><span data-stu-id="255b2-130">Changes to the System.Uri namespace in Version 2.0</span></span>](../../../docs/framework/network-programming/changes-to-the-system-uri-namespace-in-version-2-0.md)  
 <span data-ttu-id="255b2-131">描述在版本 2.0 中对 <xref:System.Uri?displayProperty=fullName> 类做出的一些更改，这些更改用于修复错误行为、增强可用性和安全性。</span><span class="sxs-lookup"><span data-stu-id="255b2-131">Describes several changes made to the <xref:System.Uri?displayProperty=fullName> class in Version 2.0 to fixed incorrect behavior, enhance usability, and enhance security.</span></span>  
  
 [<span data-ttu-id="255b2-132">System.Uri 中的国际资源标识符支持</span><span class="sxs-lookup"><span data-stu-id="255b2-132">International Resource Identifier Support in System.Uri</span></span>](../../../docs/framework/network-programming/international-resource-identifier-support-in-system-uri.md)  
 <span data-ttu-id="255b2-133">描述在版本 3.5、3.0 SP1 和 2.0 SP1 中对 <xref:System.Uri?displayProperty=fullName> 类进行的增强，这些增强用于提供国际资源标识符 (IRI) 和国际化域名 (IDN) 支持。</span><span class="sxs-lookup"><span data-stu-id="255b2-133">Describes enhancements to the <xref:System.Uri?displayProperty=fullName> class in Version 3.5, 3.0 SP1, and 2.0 SP1 for International Resource Identifier (IRI) and Internationalized Domain Name (IDN) support.</span></span>  
  
 [<span data-ttu-id="255b2-134">版本 3.5 中的套接字性能增强</span><span class="sxs-lookup"><span data-stu-id="255b2-134">Socket Performance Enhancements in Version 3.5</span></span>](../../../docs/framework/network-programming/socket-performance-enhancements-in-version-3-5.md)  
 <span data-ttu-id="255b2-135">描述在版本 3.5、3.0 SP1 和 2.0 SP1 中对 <xref:System.Net.Sockets.Socket?displayProperty=fullName> 类做出的一系列增强，这些增强提供了一种可供专用高性能套接字应用程序使用的替代异步模式。</span><span class="sxs-lookup"><span data-stu-id="255b2-135">Describes a set of enhancements to the <xref:System.Net.Sockets.Socket?displayProperty=fullName> class in Version 3.5, 3.0 SP1, and 2.0 SP1 that provide an alternative asynchronous pattern that can be used by specialized high-performance socket applications.</span></span>  
  
 [<span data-ttu-id="255b2-136">对等名称解析协议</span><span class="sxs-lookup"><span data-stu-id="255b2-136">Peer Name Resolution Protocol</span></span>](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)  
 <span data-ttu-id="255b2-137">描述在版本 3.5 中添加的支持，它们用于支持对等名称解析协议 (PNRP)、一种无服务器和动态名称注册及名称解析协议。</span><span class="sxs-lookup"><span data-stu-id="255b2-137">Describes support added in Version 3.5 to support the Peer Name Resolution Protocol (PNRP), a serverless and dynamic name registration and name resolution protocol.</span></span> <span data-ttu-id="255b2-138">这些新功能由 <xref:System.Net.PeerToPeer?displayProperty=fullName> 命名空间提供支持。</span><span class="sxs-lookup"><span data-stu-id="255b2-138">These new features are supported by the <xref:System.Net.PeerToPeer?displayProperty=fullName> namespace.</span></span>  
  
 [<span data-ttu-id="255b2-139">对等协作</span><span class="sxs-lookup"><span data-stu-id="255b2-139">Peer-to-Peer Collaboration</span></span>](../../../docs/framework/network-programming/peer-to-peer-collaboration.md)  
 <span data-ttu-id="255b2-140">描述在版本 3.5 中添加的支持，它们用于支持基于 PNRP 而构建的对等协作。</span><span class="sxs-lookup"><span data-stu-id="255b2-140">Describes support added in Version 3.5 to support the Peer-to-Peer Collaboration that builds on PNRP.</span></span> <span data-ttu-id="255b2-141">这些新功能由 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName> 命名空间提供支持。</span><span class="sxs-lookup"><span data-stu-id="255b2-141">These new features are supported by the <xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName> namespace.</span></span>  
  
 [<span data-ttu-id="255b2-142">3.5 SP1 版本中对 HttpWebRequest 的 NTLM 身份验证的更改</span><span class="sxs-lookup"><span data-stu-id="255b2-142">Changes to NTLM authentication for HttpWebRequest in Version 3.5 SP1</span></span>](../../../docs/framework/network-programming/changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 <span data-ttu-id="255b2-143">描述在版本 3.5 SP1 中做出的安全性更改，这些更改可影响以下类处理集成式 Windows 身份验证的方式： <xref:System.Net.HttpWebRequest?displayProperty=fullName>、 <xref:System.Net.HttpListener?displayProperty=fullName>、 <xref:System.Net.Security.NegotiateStream?displayProperty=fullName>，以及 System.Net 命名空间中的相关类。</span><span class="sxs-lookup"><span data-stu-id="255b2-143">Describes security changes made in Version 3.5 SP1 that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=fullName>, <xref:System.Net.HttpListener?displayProperty=fullName>, <xref:System.Net.Security.NegotiateStream?displayProperty=fullName>, and related classes in the System.Net namespace.</span></span>  
  
 [<span data-ttu-id="255b2-144">带有扩展保护的集成 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="255b2-144">Integrated Windows Authentication with Extended Protection</span></span>](../../../docs/framework/network-programming/integrated-windows-authentication-with-extended-protection.md)  
 <span data-ttu-id="255b2-145">描述扩展保护方面的增强，这些增强可影响以下类处理集成式 Windows 身份验证的方式： <xref:System.Net.HttpWebRequest?displayProperty=fullName>、 <xref:System.Net.HttpListener?displayProperty=fullName>、 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>、 <xref:System.Net.Security.SslStream?displayProperty=fullName>、 <xref:System.Net.Security.NegotiateStream?displayProperty=fullName>以及 <xref:System.Net?displayProperty=fullName> 和相关命名空间中的相关类。</span><span class="sxs-lookup"><span data-stu-id="255b2-145">Describes enhancements for extended protection that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=fullName>, <xref:System.Net.HttpListener?displayProperty=fullName>, <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>, <xref:System.Net.Security.SslStream?displayProperty=fullName>, <xref:System.Net.Security.NegotiateStream?displayProperty=fullName>, and related classes in the <xref:System.Net?displayProperty=fullName> and related namespaces.</span></span>  
  
 [<span data-ttu-id="255b2-146">使用 IPv6 和 Teredo 的 NAT 遍历</span><span class="sxs-lookup"><span data-stu-id="255b2-146">NAT Traversal using IPv6 and Teredo</span></span>](../../../docs/framework/network-programming/nat-traversal-using-ipv6-and-teredo.md)  
 <span data-ttu-id="255b2-147">描述添加到 <xref:System.Net?displayProperty=fullName>、 <xref:System.Net.NetworkInformation?displayProperty=fullName>和 <xref:System.Net.Sockets?displayProperty=fullName> 命名空间的增强，这些增强用于支持使用 IPv6 和 Teredo 进行 NAT 遍历。</span><span class="sxs-lookup"><span data-stu-id="255b2-147">Describes enhancements added to the <xref:System.Net?displayProperty=fullName>, <xref:System.Net.NetworkInformation?displayProperty=fullName>, and <xref:System.Net.Sockets?displayProperty=fullName> namespaces to support NAT traversal using IPv6 and Teredo.</span></span>  
  
 [<span data-ttu-id="255b2-148">Windows 应用商店应用的网络隔离</span><span class="sxs-lookup"><span data-stu-id="255b2-148">Network Isolation for Windows Store Apps</span></span>](../../../docs/framework/network-programming/network-isolation-for-windows-store-apps.md)  
 <span data-ttu-id="255b2-149">描述当在 <xref:System.Net>应用中使用 <xref:System.Net.Http>、 <xref:System.Net.Http.Headers> 和 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 命名空间中的类时，网络隔离所产生的影响。</span><span class="sxs-lookup"><span data-stu-id="255b2-149">Describes the impact of network isolation when classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces are used in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [<span data-ttu-id="255b2-150">网络编程示例</span><span class="sxs-lookup"><span data-stu-id="255b2-150">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 <span data-ttu-id="255b2-151">可下载网络编程示例的链接，这些示例使用 <xref:System.Net>、 <xref:System.Net.Cache>、 <xref:System.Net.Configuration>、 <xref:System.Net.Mail>、 <xref:System.Net.Mime>、 <xref:System.Net.NetworkInformation>、 <xref:System.Net.PeerToPeer>、 <xref:System.Net.Security>、 <xref:System.Net.Sockets> 命名空间中的类。</span><span class="sxs-lookup"><span data-stu-id="255b2-151">Links to downloadable network programming samples that use classes in the <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> namespaces.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="255b2-152">参考</span><span class="sxs-lookup"><span data-stu-id="255b2-152">Reference</span></span>  
 <xref:System.Net?displayProperty=fullName>  
 <span data-ttu-id="255b2-153">为当前网络采用的多种协议提供简单的编程接口。</span><span class="sxs-lookup"><span data-stu-id="255b2-153">Provides a simple programming interface for many of the protocols used on networks today.</span></span> <span data-ttu-id="255b2-154">此命名空间中的 <xref:System.Net.WebRequest?displayProperty=fullName> 和 <xref:System.Net.WebResponse?displayProperty=fullName> 类是可插入协议的基础。</span><span class="sxs-lookup"><span data-stu-id="255b2-154">The <xref:System.Net.WebRequest?displayProperty=fullName> and <xref:System.Net.WebResponse?displayProperty=fullName> classes in this namespace are the basis for pluggable protocols.</span></span>  
  
 <xref:System.Net.Cache?displayProperty=fullName>  
 <span data-ttu-id="255b2-155">定义一些类型和枚举，这些类型和枚举用于为通过 <xref:System.Net.WebRequest?displayProperty=fullName> 和 <xref:System.Net.HttpWebRequest?displayProperty=fullName> 类获取的资源制定缓存策略。</span><span class="sxs-lookup"><span data-stu-id="255b2-155">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest?displayProperty=fullName> and <xref:System.Net.HttpWebRequest?displayProperty=fullName> classes.</span></span>  
  
 <xref:System.Net.Configuration?displayProperty=fullName>  
 <span data-ttu-id="255b2-156">应用程序以编程方式访问和更新 System.Net 命名空间的配置设置时所使用的类。</span><span class="sxs-lookup"><span data-stu-id="255b2-156">Classes that applications use to programmatically access and update configuration settings for the System.Net namespaces.</span></span>  
  
 <xref:System.Net.Http?displayProperty=fullName>  
 <span data-ttu-id="255b2-157">用于为现代 HTTP 应用程序提供编程接口的类。</span><span class="sxs-lookup"><span data-stu-id="255b2-157">Classes that provides a programming interface for modern HTTP applications.</span></span>  
  
 <xref:System.Net.Http.Headers?displayProperty=fullName>  
 <span data-ttu-id="255b2-158">为 <xref:System.Net.Http?displayProperty=fullName> 命名空间使用的 HTTP 标头集合提供支持。</span><span class="sxs-lookup"><span data-stu-id="255b2-158">Provides support for collections of HTTP headers used by the <xref:System.Net.Http?displayProperty=fullName> namespace</span></span>  
  
 <xref:System.Net.Mail?displayProperty=fullName>  
 <span data-ttu-id="255b2-159">使用 SMTP 协议撰写和发送邮件时所使用的类。</span><span class="sxs-lookup"><span data-stu-id="255b2-159">Classes to compose and send mail using the SMTP protocol.</span></span>  
  
 <xref:System.Net.Mime?displayProperty=fullName>  
 <span data-ttu-id="255b2-160">定义一些类型，这些类型用于表示供 <xref:System.Net.Mail?displayProperty=fullName> 命名空间中的类所使用的多用途 Internet 邮件交换 (MIME) 标头。</span><span class="sxs-lookup"><span data-stu-id="255b2-160">Defines types that are used to represent Multipurpose Internet Mail Exchange (MIME) headers used by classes in the <xref:System.Net.Mail?displayProperty=fullName> namespace.</span></span>  
  
 <xref:System.Net.NetworkInformation?displayProperty=fullName>  
 <span data-ttu-id="255b2-161">用于以编程方式收集有关网络事件、更改、统计信息和属性的信息的类。</span><span class="sxs-lookup"><span data-stu-id="255b2-161">Classes to programmatically gather information about network events, changes, statistics, and properties.</span></span>  
  
 <xref:System.Net.PeerToPeer?displayProperty=fullName>  
 <span data-ttu-id="255b2-162">为开发人员提供对等名称解析协议 (PNRP) 的一种托管实现。</span><span class="sxs-lookup"><span data-stu-id="255b2-162">Provides a managed implementation of the Peer Name Resolution Protocol (PNRP) for developers.</span></span>  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>  
 <span data-ttu-id="255b2-163">为开发人员提供对接协作接口的一种托管实现。</span><span class="sxs-lookup"><span data-stu-id="255b2-163">Provides a managed implementation of the Peer-to-Peer Collaboration interface for developers.</span></span>  
  
 <xref:System.Net.Security?displayProperty=fullName>  
 <span data-ttu-id="255b2-164">用于为主机间的安全通信提供网络流的类。</span><span class="sxs-lookup"><span data-stu-id="255b2-164">Classes to provide network streams for secure communications between hosts.</span></span>  
  
 <xref:System.Net.Sockets?displayProperty=fullName>  
 <span data-ttu-id="255b2-165">为需要帮助控制网络访问的开发人员提供 Windows 套接字 (Winsock) 接口的一种托管实现。</span><span class="sxs-lookup"><span data-stu-id="255b2-165">Provides a managed implementation of the Windows Sockets (Winsock) interface for developers who need to help control access to the network.</span></span>  
  
 <xref:System.Net.WebSockets?displayProperty=fullName>  
 <span data-ttu-id="255b2-166">为开发人员提供 WebSocket 接口的一种托管实现。</span><span class="sxs-lookup"><span data-stu-id="255b2-166">Provides a managed implementation of the WebSocket interface for developers.</span></span>  
  
 <xref:System.Uri?displayProperty=fullName>  
 <span data-ttu-id="255b2-167">提供统一资源标识符 (URI) 的对象表示形式和对 URI 各部分的轻松访问。</span><span class="sxs-lookup"><span data-stu-id="255b2-167">Provides an object representation of a uniform resource identifier (URI) and easy access to the parts of the URI.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=fullName>  
 <span data-ttu-id="255b2-168">为采用应用程序扩展保护的身份验证提供支持。</span><span class="sxs-lookup"><span data-stu-id="255b2-168">Provides support for authentication using extended protection for applications.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=fullName>  
 <span data-ttu-id="255b2-169">为配置采用应用程序扩展保护的身份验证提供支持。</span><span class="sxs-lookup"><span data-stu-id="255b2-169">Provides support for configuration of authentication using extended protection for applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="255b2-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="255b2-170">See Also</span></span>  
 <span data-ttu-id="255b2-171">[网络编程操作说明主题](../../../docs/framework/network-programming/network-programming-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="255b2-171">[Network Programming How-to Topics](../../../docs/framework/network-programming/network-programming-how-to-topics.md) </span></span>  
 <span data-ttu-id="255b2-172">[网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md) </span><span class="sxs-lookup"><span data-stu-id="255b2-172">[Network Programming Samples](../../../docs/framework/network-programming/network-programming-samples.md) </span></span>  
 <span data-ttu-id="255b2-173">[MSDN 代码库中的 .NET 联网示例](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples) </span><span class="sxs-lookup"><span data-stu-id="255b2-173">[Networking Samples for .NET on MSDN Code Gallery](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples) </span></span>  
 [<span data-ttu-id="255b2-174">HttpClient 示例</span><span class="sxs-lookup"><span data-stu-id="255b2-174">HttpClient Sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=242550)

