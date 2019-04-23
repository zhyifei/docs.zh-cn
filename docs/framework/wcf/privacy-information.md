---
title: Windows Communication Foundation 隐私信息
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: e506908299109f94be6d190017b381fe7b4ee044
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151497"
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="432b9-102">Windows Communication Foundation 隐私信息</span><span class="sxs-lookup"><span data-stu-id="432b9-102">Windows Communication Foundation Privacy Information</span></span>
<span data-ttu-id="432b9-103">Microsoft 承诺保护最终用户的隐私。</span><span class="sxs-lookup"><span data-stu-id="432b9-103">Microsoft is committed to protecting end-users' privacy.</span></span> <span data-ttu-id="432b9-104">生成使用 Windows Communication Foundation (WCF) 3.0 版，它的应用程序时你的应用程序可能会影响最终用户的隐私。</span><span class="sxs-lookup"><span data-stu-id="432b9-104">When you build an application using Windows Communication Foundation (WCF), version 3.0, your application may impact your end-users' privacy.</span></span> <span data-ttu-id="432b9-105">例如，应用程序可能显式收集用户联系信息，或者通过 Internet 向您的网站请求或发送信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="432b9-106">如果您在应用程序中嵌入了 Microsoft 技术，则该技术可能具有可能会影响隐私的自己的行为。</span><span class="sxs-lookup"><span data-stu-id="432b9-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> <span data-ttu-id="432b9-107">WCF 不发送任何信息向 Microsoft 从你的应用程序除非你或最终用户选择将其发送给我们。</span><span class="sxs-lookup"><span data-stu-id="432b9-107">WCF does not send any information to Microsoft from your application unless you or the end-user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="432b9-108">WCF 概述</span><span class="sxs-lookup"><span data-stu-id="432b9-108">WCF in Brief</span></span>  
 <span data-ttu-id="432b9-109">WCF 是使用 Microsoft.NET Framework，开发人员可以构建分布式应用程序的分布式消息传递框架。</span><span class="sxs-lookup"><span data-stu-id="432b9-109">WCF is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="432b9-110">在两个应用程序之间交换的消息包含标头和正文信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="432b9-111">标头可能包含消息路由、安全信息、事务和其他信息，具体取决于应用程序所使用的服务。</span><span class="sxs-lookup"><span data-stu-id="432b9-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="432b9-112">默认情况下，消息通常要进行加密。</span><span class="sxs-lookup"><span data-stu-id="432b9-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="432b9-113">一个例外的情况是使用 `BasicHttpBinding`（它适用于不受保护的旧式 Web 服务）。</span><span class="sxs-lookup"><span data-stu-id="432b9-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="432b9-114">作为应用程序设计人员，您负责进行最终设计。</span><span class="sxs-lookup"><span data-stu-id="432b9-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="432b9-115">SOAP 正文中的消息包含特定于应用程序的数据;但是，可以使用 WCF 加密或保密性功能来保护此数据，如应用程序定义的个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using WCF encryption or confidentiality features.</span></span> <span data-ttu-id="432b9-116">以下几节将描述可能对隐私造成影响的功能。</span><span class="sxs-lookup"><span data-stu-id="432b9-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="432b9-117">消息</span><span class="sxs-lookup"><span data-stu-id="432b9-117">Messaging</span></span>  
 <span data-ttu-id="432b9-118">每个 WCF 消息具有指定的消息目标的地址标头和答复应发送到何处。</span><span class="sxs-lookup"><span data-stu-id="432b9-118">Each WCF message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="432b9-119">终结点地址的地址部分是一个标识该终结点的统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="432b9-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="432b9-120">该地址可以是网络地址，也可以是逻辑地址。</span><span class="sxs-lookup"><span data-stu-id="432b9-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="432b9-121">该地址可能包含计算机名称（主机名、完全限定域名）和一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="432b9-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="432b9-122">终结点地址还可能包含一个用于进行临时寻址的全局唯一标识符 (GUID) 或 GUID 集合，以便辨别每个地址。</span><span class="sxs-lookup"><span data-stu-id="432b9-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="432b9-123">每个消息都包含一个消息 ID，该消息 ID 是 GUID。</span><span class="sxs-lookup"><span data-stu-id="432b9-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="432b9-124">此功能遵循 WS-Addressing 引用标准。</span><span class="sxs-lookup"><span data-stu-id="432b9-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="432b9-125">WCF 消息传递层不会写入本地计算机的任何个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-125">The WCF messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="432b9-126">但是，如果服务开发人员创建了公开此类信息的服务（例如，通过在终结点名称中使用个人姓名，或者将个人信息包含在终结点的 Web 服务描述语言中，但不要求客户端使用 https 来访问 WSDL），则消息传递层可能会在网络级传播个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="432b9-127">此外，如果开发人员在运行[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)针对公开个人信息，该工具的输出的终结点的工具可能包含该信息，并且输出文件写入到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="432b9-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="432b9-128">宿主</span><span class="sxs-lookup"><span data-stu-id="432b9-128">Hosting</span></span>  
 <span data-ttu-id="432b9-129">WCF 中的承载功能允许应用程序来启动按需或多个应用程序之间启用端口共享。</span><span class="sxs-lookup"><span data-stu-id="432b9-129">The hosting feature in WCF allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="432b9-130">可以承载的 WCF 应用程序在 Internet 信息服务 (IIS)，类似于[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="432b9-130">An WCF application can be hosted in Internet Information Services (IIS), similar to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="432b9-131">承载功能不会在网路上公开任何特定信息，也不会在计算机上保留数据。</span><span class="sxs-lookup"><span data-stu-id="432b9-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="432b9-132">消息安全</span><span class="sxs-lookup"><span data-stu-id="432b9-132">Message Security</span></span>  
 <span data-ttu-id="432b9-133">WCF 安全提供了消息传送应用程序的安全功能。</span><span class="sxs-lookup"><span data-stu-id="432b9-133">WCF security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="432b9-134">所提供的安全功能包括身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="432b9-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="432b9-135">身份验证通过在客户端和服务之间传递凭据来执行。</span><span class="sxs-lookup"><span data-stu-id="432b9-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="432b9-136">身份验证可以通过传输级安全实现，也可以通过 SOAP 消息级安全实现，如下所述：</span><span class="sxs-lookup"><span data-stu-id="432b9-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
-   <span data-ttu-id="432b9-137">在 SOAP 消息安全中，身份验证通过诸如用户名/密码、X.509 证书、Kerberos 票证以及 SAML 令牌等凭据来执行，所有这些凭据都可能包含个人信息（根据颁发机构的情况而定）。</span><span class="sxs-lookup"><span data-stu-id="432b9-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
-   <span data-ttu-id="432b9-138">使用传输安全时，身份验证通过传统的传输身份验证机制来实现，如 HTTP 身份验证方案（基本、摘要式、协商、集成 Windows 身份验证、NTLM、无身份验证和匿名）和窗体身份验证。</span><span class="sxs-lookup"><span data-stu-id="432b9-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="432b9-139">身份验证可以导致在相互通信的终结点之间建立安全会话。</span><span class="sxs-lookup"><span data-stu-id="432b9-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="432b9-140">会话由 GUID 标识，而 GUID 能够在安全会话的整个生存期保持有效。</span><span class="sxs-lookup"><span data-stu-id="432b9-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="432b9-141">下表显示保留的内容和保留位置。</span><span class="sxs-lookup"><span data-stu-id="432b9-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="432b9-142">数据</span><span class="sxs-lookup"><span data-stu-id="432b9-142">Data</span></span>|<span data-ttu-id="432b9-143">存储</span><span class="sxs-lookup"><span data-stu-id="432b9-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="432b9-144">表示凭据，例如用户名、X.509 证书、Kerberos 令牌和对凭据的引用。</span><span class="sxs-lookup"><span data-stu-id="432b9-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="432b9-145">标准 Windows 凭据管理机制，例如 Windows 证书存储区。</span><span class="sxs-lookup"><span data-stu-id="432b9-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="432b9-146">用户成员资格信息，例如用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="432b9-146">User membership information, such as usernames and passwords.</span></span>|[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] <span data-ttu-id="432b9-147">成员资格提供程序。</span><span class="sxs-lookup"><span data-stu-id="432b9-147">membership providers.</span></span>|  
|<span data-ttu-id="432b9-148">用于向客户端证明服务身份的有关服务的标识信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="432b9-149">服务的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="432b9-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="432b9-150">调用方信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-150">Caller information.</span></span>|<span data-ttu-id="432b9-151">审核日志。</span><span class="sxs-lookup"><span data-stu-id="432b9-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="432b9-152">审核</span><span class="sxs-lookup"><span data-stu-id="432b9-152">Auditing</span></span>  
 <span data-ttu-id="432b9-153">审核功能用于记录身份验证和授权事件的成功和失败。</span><span class="sxs-lookup"><span data-stu-id="432b9-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="432b9-154">审核记录包含以下数据：服务 URI、操作 URI 和调用方的标识。</span><span class="sxs-lookup"><span data-stu-id="432b9-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="432b9-155">审核功能还记录管理员修改消息日志记录的配置（启用或禁用）的时间，因为消息日志记录可能记录标头或正文中特定于应用程序的数据。</span><span class="sxs-lookup"><span data-stu-id="432b9-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="432b9-156">对于 [!INCLUDE[wxp](../../../includes/wxp-md.md)]，记录将写入应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="432b9-156">For [!INCLUDE[wxp](../../../includes/wxp-md.md)], a record is logged in the application event log.</span></span> <span data-ttu-id="432b9-157">对于 [!INCLUDE[wv](../../../includes/wv-md.md)] 和 [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]，记录将写入安全事件日志。</span><span class="sxs-lookup"><span data-stu-id="432b9-157">For [!INCLUDE[wv](../../../includes/wv-md.md)] and [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="432b9-158">事务</span><span class="sxs-lookup"><span data-stu-id="432b9-158">Transactions</span></span>  
 <span data-ttu-id="432b9-159">事务功能提供事务性服务添加到 WCF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="432b9-159">The transactions feature provides transactional services to a WCF application.</span></span>  
  
 <span data-ttu-id="432b9-160">事务传播中使用的事物标头可能包含事务 ID 或登记 ID（这些 ID 都是 GUID）。</span><span class="sxs-lookup"><span data-stu-id="432b9-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="432b9-161">事务功能使用 Microsoft 分布式事务协调器 (MSDTC) 事务管理器（一个 Windows 组件）来管理事务状态。</span><span class="sxs-lookup"><span data-stu-id="432b9-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="432b9-162">默认情况下，事务管理器之间的通信进行加密。</span><span class="sxs-lookup"><span data-stu-id="432b9-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="432b9-163">事务管理器会将终结点引用、事务 ID 和登记 ID 作为其持久状态的一部分进行记录。</span><span class="sxs-lookup"><span data-stu-id="432b9-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="432b9-164">此状态的生存期由事务管理器的日志文件的生存期确定。</span><span class="sxs-lookup"><span data-stu-id="432b9-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="432b9-165">MSDTC 服务拥有并维护此日志。</span><span class="sxs-lookup"><span data-stu-id="432b9-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="432b9-166">事务功能实现了 WS-Coordination 和 WS-Atomic 事务标准。</span><span class="sxs-lookup"><span data-stu-id="432b9-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="432b9-167">可靠会话</span><span class="sxs-lookup"><span data-stu-id="432b9-167">Reliable Sessions</span></span>  
 <span data-ttu-id="432b9-168">WCF 中的可靠会话传输或中间故障发生时提供消息的传输。</span><span class="sxs-lookup"><span data-stu-id="432b9-168">Reliable sessions in WCF provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="432b9-169">甚至在基础传输断开（例如，无线网络上的 TCP 连接断开）或丢失消息（HTTP 代理丢弃传出消息或传入消息）时，它们也会提供“一次性”消息传送。</span><span class="sxs-lookup"><span data-stu-id="432b9-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="432b9-170">可靠会话还可以恢复消息重新排序（这可能在多路径路由的情况下发生），从而保留消息的发送顺序。</span><span class="sxs-lookup"><span data-stu-id="432b9-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="432b9-171">可靠会话是使用 WS-ReliableMessaging (WS-RM) 协议来实现的。</span><span class="sxs-lookup"><span data-stu-id="432b9-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="432b9-172">可靠会话添加包含会话信息的 WS-RM 标头，这些会话信息用于标识与特定可靠会话关联的所有消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="432b9-173">每个 WS-RM 会话都有一个 GUID 标识符。</span><span class="sxs-lookup"><span data-stu-id="432b9-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="432b9-174">最终用户的计算机上不会保留任何个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-174">No personal information is retained on the end-user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="432b9-175">排队通道</span><span class="sxs-lookup"><span data-stu-id="432b9-175">Queued Channels</span></span>  
 <span data-ttu-id="432b9-176">队列代表接收应用程序存储来自发送应用程序的消息，之后再将这些消息转发给接收应用程序。</span><span class="sxs-lookup"><span data-stu-id="432b9-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="432b9-177">队列有助于在某些情况下（例如，接收应用程序是瞬态应用程序）确保消息从发送应用程序传送到接收应用程序。</span><span class="sxs-lookup"><span data-stu-id="432b9-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> <span data-ttu-id="432b9-178">WCF 提供通过使用 Microsoft 消息队列 (MSMQ) 作为传输协议队列的支持。</span><span class="sxs-lookup"><span data-stu-id="432b9-178">WCF provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="432b9-179">排队通道功能不会向消息中添加标头。</span><span class="sxs-lookup"><span data-stu-id="432b9-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="432b9-180">相反，它会创建一个具有适当的消息队列消息属性集的消息队列消息，并调用消息队列方法来将消息放入“消息队列”队列中。</span><span class="sxs-lookup"><span data-stu-id="432b9-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="432b9-181">消息队列是一个可选组件，它随 Windows 一起提供。</span><span class="sxs-lookup"><span data-stu-id="432b9-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="432b9-182">排队通道功能不会在最终用户的计算机上保留任何信息，因为它使用消息队列作为队列基础结构。</span><span class="sxs-lookup"><span data-stu-id="432b9-182">No information is retained on the end-user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="432b9-183">COM+ 集成</span><span class="sxs-lookup"><span data-stu-id="432b9-183">COM+ Integration</span></span>  
 <span data-ttu-id="432b9-184">此功能包装现有的 COM 和 COM + 功能，以创建与 WCF 服务兼容的服务。</span><span class="sxs-lookup"><span data-stu-id="432b9-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with WCF services.</span></span> <span data-ttu-id="432b9-185">此功能不使用特定的标头，并且不会在最终用户的计算机上保留数据。</span><span class="sxs-lookup"><span data-stu-id="432b9-185">This feature does not use specific headers and it does not retain data on the end-user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="432b9-186">COM 服务标记</span><span class="sxs-lookup"><span data-stu-id="432b9-186">COM Service Moniker</span></span>  
 <span data-ttu-id="432b9-187">这为标准 WCF 客户端提供的非托管的包装器。</span><span class="sxs-lookup"><span data-stu-id="432b9-187">This provides an unmanaged wrapper to a standard WCF client.</span></span> <span data-ttu-id="432b9-188">此功能在网络上没有特定的标头，也不会在计算机上持久保留数据。</span><span class="sxs-lookup"><span data-stu-id="432b9-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="432b9-189">对等通道</span><span class="sxs-lookup"><span data-stu-id="432b9-189">Peer Channel</span></span>  
 <span data-ttu-id="432b9-190">对等通道支持的多方应用程序使用 WCF 的开发。</span><span class="sxs-lookup"><span data-stu-id="432b9-190">A peer channel enables development of multiparty applications using WCF.</span></span> <span data-ttu-id="432b9-191">多方消息传递发生在网格环境中。</span><span class="sxs-lookup"><span data-stu-id="432b9-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="432b9-192">网格由节点可以加入的名称来标识。</span><span class="sxs-lookup"><span data-stu-id="432b9-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="432b9-193">对等通道中的每个节点都在用户指定的端口创建一个 TCP 侦听器，并与网格中的其他节点建立连接以确保连接的弹性。</span><span class="sxs-lookup"><span data-stu-id="432b9-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="432b9-194">为了与网格中的其他节点进行连接，节点还会与网格中的其他节点交换一些数据，包括侦听器地址和计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="432b9-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="432b9-195">在网格中四处发送的消息可能包含与发送方相关的安全信息，以防止发生消息欺骗和篡改。</span><span class="sxs-lookup"><span data-stu-id="432b9-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="432b9-196">最终用户的计算机上不会存储任何个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-196">No personal information is stored on the end-user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="432b9-197">IT 专业经验</span><span class="sxs-lookup"><span data-stu-id="432b9-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="432b9-198">跟踪</span><span class="sxs-lookup"><span data-stu-id="432b9-198">Tracing</span></span>  
 <span data-ttu-id="432b9-199">WCF 基础结构的诊断功能记录通过传输和服务模型层的活动和与这些消息关联的事件传递的消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-199">The diagnostics feature of the WCF infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="432b9-200">默认情况下，此功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="432b9-200">This feature is turned off by default.</span></span> <span data-ttu-id="432b9-201">启用使用应用程序的配置文件，并可以在运行时使用的 WCF WMI 提供程序来修改跟踪行为。</span><span class="sxs-lookup"><span data-stu-id="432b9-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the WCF WMI provider at run time.</span></span> <span data-ttu-id="432b9-202">在启用此功能后，跟踪基础结构会向已配置的侦听器发出包含消息、活动和处理事件的诊断跟踪。</span><span class="sxs-lookup"><span data-stu-id="432b9-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="432b9-203">输出的格式和位置由管理员的侦听器配置选择确定，但通常是 XML 格式化文件。</span><span class="sxs-lookup"><span data-stu-id="432b9-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="432b9-204">管理员负责设置跟踪文件上的访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="432b9-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="432b9-205">具体而言，在由 Windows 激活系统 (WAS) 进行承载时，管理员应确保不是从公共虚拟根目录提供这些文件（如果不需要）。</span><span class="sxs-lookup"><span data-stu-id="432b9-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="432b9-206">有两种类型的跟踪：消息日志记录和诊断服务模型跟踪下, 一节中描述。</span><span class="sxs-lookup"><span data-stu-id="432b9-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="432b9-207">每种类型都通过其自身的跟踪源进行配置，它们分别是 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> 和 <xref:System.ServiceModel>。</span><span class="sxs-lookup"><span data-stu-id="432b9-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="432b9-208">这两种日志记录跟踪源都捕获应用程序本地的数据。</span><span class="sxs-lookup"><span data-stu-id="432b9-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="432b9-209">消息日志记录</span><span class="sxs-lookup"><span data-stu-id="432b9-209">Message Logging</span></span>  
 <span data-ttu-id="432b9-210">消息日志记录跟踪源（<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>）使管理员可以记录流经系统的消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="432b9-211">通过配置，用户可以决定是记录完整的消息还是仅记录消息头、是否在传输和/或服务模型层记录以及是否包括格式不正确的消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="432b9-212">另外，用户可以配置筛选来限制要记录的消息范围。</span><span class="sxs-lookup"><span data-stu-id="432b9-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="432b9-213">默认情况下，消息日志记录被禁用。</span><span class="sxs-lookup"><span data-stu-id="432b9-213">By default, message logging is disabled.</span></span> <span data-ttu-id="432b9-214">本地计算机管理员可以阻止应用程序级管理员启用消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="432b9-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="432b9-215">加密和解密消息日志记录</span><span class="sxs-lookup"><span data-stu-id="432b9-215">Encrypted and Decrypted Message Logging</span></span>  
 <span data-ttu-id="432b9-216">消息按下列术语所描述的方式进行记录、加密或解密。</span><span class="sxs-lookup"><span data-stu-id="432b9-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="432b9-217">传输日志记录</span><span class="sxs-lookup"><span data-stu-id="432b9-217">Transport Logging</span></span>  
 <span data-ttu-id="432b9-218">记录在传输级接收和发送的消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="432b9-219">这些消息包含所有标头，并且在网络上发送之前以及在接收时可能进行加密。</span><span class="sxs-lookup"><span data-stu-id="432b9-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="432b9-220">如果消息在网络上发送之前以及在接收时进行加密，那么还会记录加密后的消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="432b9-221">一个例外的情况是使用安全协议 (https)：尽管消息在网络上进行了加密，但是在发送之前以及接收之后会记录解密的消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="432b9-222">服务日志记录</span><span class="sxs-lookup"><span data-stu-id="432b9-222">Service Logging</span></span>  
 <span data-ttu-id="432b9-223">在通道标头处理已经发生后，刚好在进入用户代码之前和之后记录在服务模型层接收或发送的消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="432b9-224">即使消息在网络上进行了保护和加密，在此层记录的消息也是解密消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="432b9-225">格式不正确的消息日志记录</span><span class="sxs-lookup"><span data-stu-id="432b9-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="432b9-226">WCF 基础结构无法理解或处理的日志消息。</span><span class="sxs-lookup"><span data-stu-id="432b9-226">Logs messages that the WCF infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="432b9-227">消息按原样（即，加密或不加密）进行记录。</span><span class="sxs-lookup"><span data-stu-id="432b9-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="432b9-228">在中记录消息时解密或加密表单中，默认情况下，WCF 之前会删除安全密钥和潜在的个人信息的消息并记录这些。</span><span class="sxs-lookup"><span data-stu-id="432b9-228">When messages are logged in decrypted or unencrypted form, by default WCF removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="432b9-229">下面几节将描述要删除的消息以及删除时间。</span><span class="sxs-lookup"><span data-stu-id="432b9-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="432b9-230">计算机管理员和应用程序部署人员都必须执行一定的配置操作来更改默认行为，以便记录密钥和潜在的个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="432b9-231">在记录解密/未加密消息时从消息头中删除的信息</span><span class="sxs-lookup"><span data-stu-id="432b9-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="432b9-232">在以解密/未加密形式记录消息时，默认情况下，将在记录消息之前从消息头和消息正文中删除安全密钥和潜在的个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="432b9-233">以下列表显示了 WCF 视为密钥和潜在的个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-233">The following list shows what WCF considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="432b9-234">被删除的密钥：</span><span class="sxs-lookup"><span data-stu-id="432b9-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="432b9-235">\- 对于 xmlns:wst ="http://schemas.xmlsoap.org/ws/2004/04/trust"和 xmlns:wst ="http://schemas.xmlsoap.org/ws/2005/02/trust"</span><span class="sxs-lookup"><span data-stu-id="432b9-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="432b9-236">wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="432b9-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="432b9-237">wst:Entropy</span><span class="sxs-lookup"><span data-stu-id="432b9-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="432b9-238">\- 对于 xmlns:wsse ="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd"和 xmlns:wsse ="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="432b9-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="432b9-239">wsse:Password</span><span class="sxs-lookup"><span data-stu-id="432b9-239">wsse:Password</span></span>  
  
 <span data-ttu-id="432b9-240">wsse:Nonce</span><span class="sxs-lookup"><span data-stu-id="432b9-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="432b9-241">被删除的潜在个人信息：</span><span class="sxs-lookup"><span data-stu-id="432b9-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="432b9-242">\- 对于 xmlns:wsse ="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd"和 xmlns:wsse ="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="432b9-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="432b9-243">wsse:Username</span><span class="sxs-lookup"><span data-stu-id="432b9-243">wsse:Username</span></span>  
  
 <span data-ttu-id="432b9-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="432b9-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="432b9-245">\- 有关 xmlns:saml ="urn: oasis： 名称： tc: SAML:1.0:assertion"删除以下各项以粗体显示 （）：</span><span class="sxs-lookup"><span data-stu-id="432b9-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="432b9-246">\<断言</span><span class="sxs-lookup"><span data-stu-id="432b9-246">\<Assertion</span></span>  
  
 <span data-ttu-id="432b9-247">MajorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="432b9-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="432b9-248">MinorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="432b9-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="432b9-249">AssertionId="[ID]"</span><span class="sxs-lookup"><span data-stu-id="432b9-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="432b9-250">Issuer="[string]"</span><span class="sxs-lookup"><span data-stu-id="432b9-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="432b9-251">IssueInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="432b9-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="432b9-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span><span class="sxs-lookup"><span data-stu-id="432b9-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span></span>  
  
 <span data-ttu-id="432b9-253">\<AudienceRestrictionCondition></span><span class="sxs-lookup"><span data-stu-id="432b9-253">\<AudienceRestrictionCondition></span></span>  
  
 <span data-ttu-id="432b9-254">\<Audience>[uri]\</Audience>+</span><span class="sxs-lookup"><span data-stu-id="432b9-254">\<Audience>[uri]\</Audience>+</span></span>  
  
 <span data-ttu-id="432b9-255">\</AudienceRestrictionCondition>\*</span><span class="sxs-lookup"><span data-stu-id="432b9-255">\</AudienceRestrictionCondition>\*</span></span>  
  
 <span data-ttu-id="432b9-256">\<DoNotCacheCondition />\*</span><span class="sxs-lookup"><span data-stu-id="432b9-256">\<DoNotCacheCondition />\*</span></span>  
  
 <span data-ttu-id="432b9-257"><\!-抽象基类型</span><span class="sxs-lookup"><span data-stu-id="432b9-257"><\!-- abstract base type</span></span>  
  
 <span data-ttu-id="432b9-258">\<条件 / > \*</span><span class="sxs-lookup"><span data-stu-id="432b9-258">\<Condition />\*</span></span>  
  
 -->  
  
 <span data-ttu-id="432b9-259">\</ 条件 >？</span><span class="sxs-lookup"><span data-stu-id="432b9-259">\</Conditions>?</span></span>  
  
 <span data-ttu-id="432b9-260">\<建议 ></span><span class="sxs-lookup"><span data-stu-id="432b9-260">\<Advice></span></span>  
  
 <span data-ttu-id="432b9-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span><span class="sxs-lookup"><span data-stu-id="432b9-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span></span>  
  
 <span data-ttu-id="432b9-262">\<Assertion>[assertion]\</Assertion>\*</span><span class="sxs-lookup"><span data-stu-id="432b9-262">\<Assertion>[assertion]\</Assertion>\*</span></span>  
  
 <span data-ttu-id="432b9-263">[any]\*</span><span class="sxs-lookup"><span data-stu-id="432b9-263">[any]\*</span></span>  
  
 <span data-ttu-id="432b9-264">\</ 通知 >？</span><span class="sxs-lookup"><span data-stu-id="432b9-264">\</Advice>?</span></span>  
  
 <span data-ttu-id="432b9-265"><\!-抽象基类型</span><span class="sxs-lookup"><span data-stu-id="432b9-265"><\!-- Abstract base types</span></span>  
  
 <span data-ttu-id="432b9-266">\<语句 / > \*</span><span class="sxs-lookup"><span data-stu-id="432b9-266">\<Statement />\*</span></span>  
  
 <span data-ttu-id="432b9-267">\<SubjectStatement></span><span class="sxs-lookup"><span data-stu-id="432b9-267">\<SubjectStatement></span></span>  
  
 <span data-ttu-id="432b9-268">\<Subject></span><span class="sxs-lookup"><span data-stu-id="432b9-268">\<Subject></span></span>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 <span data-ttu-id="432b9-269">\<SubjectConfirmation></span><span class="sxs-lookup"><span data-stu-id="432b9-269">\<SubjectConfirmation></span></span>  
  
 <span data-ttu-id="432b9-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span><span class="sxs-lookup"><span data-stu-id="432b9-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="432b9-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span><span class="sxs-lookup"><span data-stu-id="432b9-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="432b9-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span><span class="sxs-lookup"><span data-stu-id="432b9-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="432b9-273">\</SubjectConfirmation>?</span><span class="sxs-lookup"><span data-stu-id="432b9-273">\</SubjectConfirmation>?</span></span>  
  
 <span data-ttu-id="432b9-274">\</Subject></span><span class="sxs-lookup"><span data-stu-id="432b9-274">\</Subject></span></span>  
  
 <span data-ttu-id="432b9-275">\</SubjectStatement>\*</span><span class="sxs-lookup"><span data-stu-id="432b9-275">\</SubjectStatement>\*</span></span>  
  
 -->  
  
 <span data-ttu-id="432b9-276">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="432b9-276">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="432b9-277">AuthenticationMethod="[uri]"</span><span class="sxs-lookup"><span data-stu-id="432b9-277">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="432b9-278">AuthenticationInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="432b9-278">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="432b9-279">[Subject]</span><span class="sxs-lookup"><span data-stu-id="432b9-279">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="432b9-280"><AuthorityBinding</span><span class="sxs-lookup"><span data-stu-id="432b9-280"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="432b9-281">AuthorityKind="[QName]"</span><span class="sxs-lookup"><span data-stu-id="432b9-281">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="432b9-282">Location="[uri]"</span><span class="sxs-lookup"><span data-stu-id="432b9-282">Location="[uri]"</span></span>  
  
 <span data-ttu-id="432b9-283">Binding="[uri]"</span><span class="sxs-lookup"><span data-stu-id="432b9-283">Binding="[uri]"</span></span>  
  
 />*  
  
 <span data-ttu-id="432b9-284">\</AuthenticationStatement>\*</span><span class="sxs-lookup"><span data-stu-id="432b9-284">\</AuthenticationStatement>\*</span></span>  
  
 <span data-ttu-id="432b9-285">\<AttributeStatement></span><span class="sxs-lookup"><span data-stu-id="432b9-285">\<AttributeStatement></span></span>  
  
 <span data-ttu-id="432b9-286">[Subject]</span><span class="sxs-lookup"><span data-stu-id="432b9-286">[Subject]</span></span>  
  
 <span data-ttu-id="432b9-287">\<属性</span><span class="sxs-lookup"><span data-stu-id="432b9-287">\<Attribute</span></span>  
  
 <span data-ttu-id="432b9-288">AttributeName="[string]"</span><span class="sxs-lookup"><span data-stu-id="432b9-288">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="432b9-289">AttributeNamespace="[uri]"</span><span class="sxs-lookup"><span data-stu-id="432b9-289">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 <span data-ttu-id="432b9-290">\</ 属性 > +</span><span class="sxs-lookup"><span data-stu-id="432b9-290">\</Attribute>+</span></span>  
  
 <span data-ttu-id="432b9-291">\</AttributeStatement>\*</span><span class="sxs-lookup"><span data-stu-id="432b9-291">\</AttributeStatement>\*</span></span>  
  
 <span data-ttu-id="432b9-292">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="432b9-292">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="432b9-293">Resource="[uri]"</span><span class="sxs-lookup"><span data-stu-id="432b9-293">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="432b9-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span><span class="sxs-lookup"><span data-stu-id="432b9-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="432b9-295">[Subject]</span><span class="sxs-lookup"><span data-stu-id="432b9-295">[Subject]</span></span>  
  
 <span data-ttu-id="432b9-296">\<操作 Namespace ="[uri]"> [string]\</Action > +</span><span class="sxs-lookup"><span data-stu-id="432b9-296">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 <span data-ttu-id="432b9-297">\<证据 ></span><span class="sxs-lookup"><span data-stu-id="432b9-297">\<Evidence></span></span>  
  
 <span data-ttu-id="432b9-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span><span class="sxs-lookup"><span data-stu-id="432b9-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="432b9-299">\<Assertion>[assertion]\</Assertion>+</span><span class="sxs-lookup"><span data-stu-id="432b9-299">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="432b9-300">\</ 证据 >？</span><span class="sxs-lookup"><span data-stu-id="432b9-300">\</Evidence>?</span></span>  
  
 <span data-ttu-id="432b9-301">\</AuthorizationDecisionStatement>\*</span><span class="sxs-lookup"><span data-stu-id="432b9-301">\</AuthorizationDecisionStatement>\*</span></span>  
  
 <span data-ttu-id="432b9-302">\</Assertion></span><span class="sxs-lookup"><span data-stu-id="432b9-302">\</Assertion></span></span>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="432b9-303">在记录解密/未加密消息时从消息正文中删除的信息</span><span class="sxs-lookup"><span data-stu-id="432b9-303">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="432b9-304">如上文所述，WCF 会删除密钥和已知的潜在个人信息的记录解密/未加密的消息的消息标头中。</span><span class="sxs-lookup"><span data-stu-id="432b9-304">As previously described, WCF removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="432b9-305">此外，WCF 从中删除密钥和已知的潜在个人信息的正文元素和以下列表中，用于描述密钥交换中涉及的安全消息的操作的消息正文。</span><span class="sxs-lookup"><span data-stu-id="432b9-305">In addition, WCF removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="432b9-306">对于下列命名空间：</span><span class="sxs-lookup"><span data-stu-id="432b9-306">For the following namespaces:</span></span>  
  
 <span data-ttu-id="432b9-307">xmlns:wst ="http://schemas.xmlsoap.org/ws/2004/04/trust"和 xmlns:wst ="http://schemas.xmlsoap.org/ws/2005/02/trust"（例如，如果无可用的操作）</span><span class="sxs-lookup"><span data-stu-id="432b9-307">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="432b9-308">删除那些涉及密钥交换的正文元素的信息：</span><span class="sxs-lookup"><span data-stu-id="432b9-308">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="432b9-309">wst:RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="432b9-309">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="432b9-310">wst:RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="432b9-310">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="432b9-311">wst:RequestSecurityTokenResponseCollection</span><span class="sxs-lookup"><span data-stu-id="432b9-311">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="432b9-312">还要删除下列每个操作的信息：</span><span class="sxs-lookup"><span data-stu-id="432b9-312">Information is also removed for each of the following Actions:</span></span>  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="432b9-313">不会从特定于应用程序的标头和正文数据中删除任何信息</span><span class="sxs-lookup"><span data-stu-id="432b9-313">No Information Is Removed from Application-specific Headers and Body Data</span></span>  
 <span data-ttu-id="432b9-314">WCF 不跟踪特定于应用程序的标头 （例如，查询字符串） 或正文数据 （例如，信用卡号） 中的个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-314">WCF does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="432b9-315">启用消息日志记录后，特定于应用程序的标头中的个人信息和正文信息在日志中可见。</span><span class="sxs-lookup"><span data-stu-id="432b9-315">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="432b9-316">同样，应用程序部署人员负责设置配置和日志文件上的 ACL。</span><span class="sxs-lookup"><span data-stu-id="432b9-316">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="432b9-317">如果他不希望让这些信息可见，他还可以禁用日志记录，或者在记录这些信息之后将其从日志文件中筛选掉。</span><span class="sxs-lookup"><span data-stu-id="432b9-317">He also can turn off logging if he does not want this information to be visible, or he may filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="432b9-318">服务模型跟踪</span><span class="sxs-lookup"><span data-stu-id="432b9-318">Service Model Tracing</span></span>  
 <span data-ttu-id="432b9-319">使用服务模型跟踪源（<xref:System.ServiceModel>）可以对与消息处理相关的活动和事件进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="432b9-319">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="432b9-320">此功能使用 <xref:System.Diagnostics> 中的 .NET Framework 诊断功能。</span><span class="sxs-lookup"><span data-stu-id="432b9-320">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="432b9-321">就像 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> 属性一样，用户可以使用 .NET Framework 应用程序配置文件对其位置和 ACL 进行配置。</span><span class="sxs-lookup"><span data-stu-id="432b9-321">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="432b9-322">与消息日志记录一样，文件位置总是在管理员启用跟踪时进行配置，这样，管理员便可以控制 ACL。</span><span class="sxs-lookup"><span data-stu-id="432b9-322">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="432b9-323">当消息在范围内时，跟踪包含消息头。</span><span class="sxs-lookup"><span data-stu-id="432b9-323">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="432b9-324">上一节中描述的有关隐藏消息头中的潜在个人信息的相同规则同样适用：默认情况下，将先前标识的个人信息从跟踪中包含的标头中删除。</span><span class="sxs-lookup"><span data-stu-id="432b9-324">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="432b9-325">计算机管理员和应用程序部署人员都必须修改配置，以便记录潜在的个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-325">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="432b9-326">但是，跟踪中会记录特定于应用程序的标头中包含的个人信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-326">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="432b9-327">应用程序部署人员负责设置配置和跟踪文件上的 ACL。</span><span class="sxs-lookup"><span data-stu-id="432b9-327">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="432b9-328">如果他不希望让这些信息可见，他还可以禁用跟踪记录，或者在记录这些信息之后将其从跟踪文件中筛选掉。</span><span class="sxs-lookup"><span data-stu-id="432b9-328">He also can turn off tracing if he does not want this information to be visible, or he can filter out this information from the trace files after it is logged.</span></span>  
  
 <span data-ttu-id="432b9-329">作为服务模型跟踪的一部分，当消息流经基础结构的不同部分时，由唯一的 ID（称为活动 ID，通常是 GUID）将不同的活动链接到一起。</span><span class="sxs-lookup"><span data-stu-id="432b9-329">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="432b9-330">自定义跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="432b9-330">Custom Trace Listeners</span></span>  
 <span data-ttu-id="432b9-331">对于消息日志记录和跟踪记录，可以配置一个自定义跟踪侦听器，该侦听器可以在网络上发送跟踪和消息（例如，向远程数据库发送）。</span><span class="sxs-lookup"><span data-stu-id="432b9-331">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="432b9-332">应用程序部署人员负责配置自定义侦听器或授权用户执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="432b9-332">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="432b9-333">他还对在远程位置公开的所有个人信息负有责任，并负责将 ACL 正确应用到此位置。</span><span class="sxs-lookup"><span data-stu-id="432b9-333">He is also responsible for any personal information exposed at the remote location, and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="432b9-334">IT 专业人员的其他作用</span><span class="sxs-lookup"><span data-stu-id="432b9-334">Other features for IT Professionals</span></span>  
 <span data-ttu-id="432b9-335">WCF 具有公开通过 WMI （随 Windows） 的 WCF 基础结构配置信息的 WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="432b9-335">WCF has a WMI provider that exposes the WCF infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="432b9-336">默认情况下，WMI 接口可供管理员使用。</span><span class="sxs-lookup"><span data-stu-id="432b9-336">By default, the WMI interface is available to administrators.</span></span>  
  
 <span data-ttu-id="432b9-337">WCF 配置使用.NET Framework 配置机制。</span><span class="sxs-lookup"><span data-stu-id="432b9-337">WCF configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="432b9-338">配置文件存储在计算机上。</span><span class="sxs-lookup"><span data-stu-id="432b9-338">The configuration files are stored on the machine.</span></span> <span data-ttu-id="432b9-339">应用程序开发人员和管理员为应用程序的每个需求创建配置文件和 ACL。</span><span class="sxs-lookup"><span data-stu-id="432b9-339">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="432b9-340">配置文件可以包含终结点地址和指向证书存储区中的证书的链接。</span><span class="sxs-lookup"><span data-stu-id="432b9-340">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="432b9-341">证书可用于提供应用程序数据，以配置应用程序所使用的功能的各种属性。</span><span class="sxs-lookup"><span data-stu-id="432b9-341">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 <span data-ttu-id="432b9-342">WCF 还通过调用使用.NET Framework 进程转储功能<xref:System.Environment.FailFast%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="432b9-342">WCF also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="432b9-343">IT 专业工具</span><span class="sxs-lookup"><span data-stu-id="432b9-343">IT Pro Tools</span></span>  
 <span data-ttu-id="432b9-344">WCF 还提供了以下的 IT 专业工具，这在 Windows SDK 中提供。</span><span class="sxs-lookup"><span data-stu-id="432b9-344">WCF also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="432b9-345">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="432b9-345">SvcTraceViewer.exe</span></span>  
 <span data-ttu-id="432b9-346">在查看器显示 WCF 跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="432b9-346">The viewer displays WCF trace files.</span></span> <span data-ttu-id="432b9-347">该查看器显示跟踪中包含的所有信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-347">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="432b9-348">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="432b9-348">SvcConfigEditor.exe</span></span>  
 <span data-ttu-id="432b9-349">编辑器允许用户创建和编辑 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="432b9-349">The editor allows the user to create and edit WCF configuration files.</span></span> <span data-ttu-id="432b9-350">该编辑器显示配置文件中包含的所有信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-350">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="432b9-351">使用文本编辑器可以完成同样的任务。</span><span class="sxs-lookup"><span data-stu-id="432b9-351">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodelreg"></a><span data-ttu-id="432b9-352">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="432b9-352">ServiceModel_Reg</span></span>  
 <span data-ttu-id="432b9-353">此工具使用户可以管理计算机上的 ServiceModel 安装。</span><span class="sxs-lookup"><span data-stu-id="432b9-353">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="432b9-354">该工具在控制台窗口中显示状态消息后，它在运行，在此过程中，可能会显示有关 WCF 安装的配置信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-354">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the WCF installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="432b9-355">WSATConfig.exe 和 WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="432b9-355">WSATConfig.exe and WSATUI.dll</span></span>  
 <span data-ttu-id="432b9-356">这些工具，IT 专业人员在 WCF 中配置可互操作的 WS-AtomicTransaction 网络支持。</span><span class="sxs-lookup"><span data-stu-id="432b9-356">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in WCF.</span></span> <span data-ttu-id="432b9-357">这两种工具显示并使用户可以更改存储在注册表中的最常用 WS-AtomicTransaction 设置的值。</span><span class="sxs-lookup"><span data-stu-id="432b9-357">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="432b9-358">横切功能</span><span class="sxs-lookup"><span data-stu-id="432b9-358">Cross-cutting Features</span></span>  
 <span data-ttu-id="432b9-359">下列功能是横切功能。</span><span class="sxs-lookup"><span data-stu-id="432b9-359">The following features are cross-cutting.</span></span> <span data-ttu-id="432b9-360">即，它们可以用前面的任何功能构成。</span><span class="sxs-lookup"><span data-stu-id="432b9-360">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="432b9-361">服务框架</span><span class="sxs-lookup"><span data-stu-id="432b9-361">Service Framework</span></span>  
 <span data-ttu-id="432b9-362">标头可以包含一个实例 ID，该 ID 是一个将消息与 CLR 类的一个实例相关联的 GUID。</span><span class="sxs-lookup"><span data-stu-id="432b9-362">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="432b9-363">Web 服务描述语言 (WSDL) 包含端口的定义。</span><span class="sxs-lookup"><span data-stu-id="432b9-363">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="432b9-364">每个端口都具有一个终结点地址和一个表示应用程序所使用的服务的绑定。</span><span class="sxs-lookup"><span data-stu-id="432b9-364">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="432b9-365">可以使用配置禁用公开 WSDL。</span><span class="sxs-lookup"><span data-stu-id="432b9-365">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="432b9-366">计算机上不会保留任何信息。</span><span class="sxs-lookup"><span data-stu-id="432b9-366">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="432b9-367">请参阅</span><span class="sxs-lookup"><span data-stu-id="432b9-367">See also</span></span>

- [<span data-ttu-id="432b9-368">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="432b9-368">Windows Communication Foundation</span></span>](index.md)
- [<span data-ttu-id="432b9-369">安全性</span><span class="sxs-lookup"><span data-stu-id="432b9-369">Security</span></span>](../../../docs/framework/wcf/feature-details/security.md)
