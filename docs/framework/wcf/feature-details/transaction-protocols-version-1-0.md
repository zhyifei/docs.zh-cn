---
title: "事务协议版本 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 95bf16a4e243d82b9b8fe83b306284335ae0bd16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="a5051-102">事务协议版本 1.0</span><span class="sxs-lookup"><span data-stu-id="a5051-102">Transaction Protocols version 1.0</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="a5051-103"> 版本 1 实现 WS-Atomic Transaction 和 WS-Coordination 协议的版本 1.0。</span><span class="sxs-lookup"><span data-stu-id="a5051-103"> version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a5051-104">1.1 版中，请参阅[事务协议](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)。</span><span class="sxs-lookup"><span data-stu-id="a5051-104"> version 1.1, see [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="a5051-105">规范/文档</span><span class="sxs-lookup"><span data-stu-id="a5051-105">Specification/Document</span></span>|<span data-ttu-id="a5051-106">Link</span><span class="sxs-lookup"><span data-stu-id="a5051-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="a5051-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="a5051-107">WS-Coordination</span></span>|<span data-ttu-id="a5051-108">http://msdn.microsoft.com/ws/2005/08/ws-coordination/</span><span class="sxs-lookup"><span data-stu-id="a5051-108">http://msdn.microsoft.com/ws/2005/08/ws-coordination/</span></span>|  
|<span data-ttu-id="a5051-109">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="a5051-109">WS-AtomicTransaction</span></span>|<span data-ttu-id="a5051-110">http://msdn.microsoft.com/ws/2005/08/ws-atomictransaction/</span><span class="sxs-lookup"><span data-stu-id="a5051-110">http://msdn.microsoft.com/ws/2005/08/ws-atomictransaction/</span></span>|  
  
 <span data-ttu-id="a5051-111">这些协议规范需要在两种级别提供互操作性：在应用程序之间和在事务管理器之间（请参见下图）。</span><span class="sxs-lookup"><span data-stu-id="a5051-111">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="a5051-112">规范详细说明两个互操作性级别的消息格式和消息交换。</span><span class="sxs-lookup"><span data-stu-id="a5051-112">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="a5051-113">用于应用程序间交换的特定安全性、可靠性和编码与常规应用程序交换一样适用。</span><span class="sxs-lookup"><span data-stu-id="a5051-113">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="a5051-114">但是，在事务管理器之间的成功互操作还需要特定绑定的协议，因为它通常不由用户进行配置。</span><span class="sxs-lookup"><span data-stu-id="a5051-114">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="a5051-115">本主题说明 WS-Atomic Transaction (WS-AT) 规范与安全性的组合，并说明用于事务管理器间通信的安全绑定。</span><span class="sxs-lookup"><span data-stu-id="a5051-115">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="a5051-116">本文档中介绍的方法已经使用 WS-AT 和 WS-Coordination 的其他实现（包括 IBM、IONA、Sun Microsystems 等）成功进行了测试。</span><span class="sxs-lookup"><span data-stu-id="a5051-116">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="a5051-117">下图描述了两个事务管理器（事务管理器 1 和事务管理器 2）和两个应用程序（应用程序 1 和应用程序 2）之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="a5051-117">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2.</span></span>  
  
 <span data-ttu-id="a5051-118">![事务协议](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "事务管理器")</span><span class="sxs-lookup"><span data-stu-id="a5051-118">![Transaction Protocols](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "TransactionManagers")</span></span>  
  
 <span data-ttu-id="a5051-119">假设一个典型的 WS-Coordination/WS-Atomic Transaction 方案具有一个发起方 (I) 和一个参与者 (P)。</span><span class="sxs-lookup"><span data-stu-id="a5051-119">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="a5051-120">发起方和参与者都有事务管理器（分别为 ITM 和 PTM）。</span><span class="sxs-lookup"><span data-stu-id="a5051-120">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="a5051-121">两阶段提交在本主题中称为 2PC。</span><span class="sxs-lookup"><span data-stu-id="a5051-121">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5051-122">1.CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="a5051-122">1. CreateCoordinationContext</span></span>|<span data-ttu-id="a5051-123">12.应用程序消息响应</span><span class="sxs-lookup"><span data-stu-id="a5051-123">12. Application Message Response</span></span>|  
|<span data-ttu-id="a5051-124">2.CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="a5051-124">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="a5051-125">13.提交（完成）</span><span class="sxs-lookup"><span data-stu-id="a5051-125">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="a5051-126">3.注册（完成）</span><span class="sxs-lookup"><span data-stu-id="a5051-126">3. Register (Completion)</span></span>|<span data-ttu-id="a5051-127">14.准备 (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5051-127">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="a5051-128">4.RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="a5051-128">4. RegisterResponse</span></span>|<span data-ttu-id="a5051-129">15.准备 (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5051-129">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="a5051-130">5.应用程序消息</span><span class="sxs-lookup"><span data-stu-id="a5051-130">5. Application Message</span></span>|<span data-ttu-id="a5051-131">16.已准备 (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5051-131">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="a5051-132">6.使用上下文的 CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="a5051-132">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="a5051-133">17.已准备 (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5051-133">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="a5051-134">7.注册（持久）</span><span class="sxs-lookup"><span data-stu-id="a5051-134">7. Register (Durable)</span></span>|<span data-ttu-id="a5051-135">18.已提交（完成）</span><span class="sxs-lookup"><span data-stu-id="a5051-135">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="a5051-136">8.RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="a5051-136">8. RegisterResponse</span></span>|<span data-ttu-id="a5051-137">19.提交 (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5051-137">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="a5051-138">9.CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="a5051-138">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="a5051-139">20.提交 (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5051-139">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="a5051-140">10.注册（持久）</span><span class="sxs-lookup"><span data-stu-id="a5051-140">10. Register (Durable)</span></span>|<span data-ttu-id="a5051-141">21.已提交 (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5051-141">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="a5051-142">11.RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="a5051-142">11. RegisterResponse</span></span>|<span data-ttu-id="a5051-143">22.已提交 (2PC)</span><span class="sxs-lookup"><span data-stu-id="a5051-143">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="a5051-144">本文档说明 WS-AtomicTransaction 规范与安全性的组合，并说明用于事务管理器间通信的安全绑定。</span><span class="sxs-lookup"><span data-stu-id="a5051-144">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="a5051-145">本文档中介绍的方法已经使用 WS-AT 和 WS-Coordination 的其他实现成功进行了测试。</span><span class="sxs-lookup"><span data-stu-id="a5051-145">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="a5051-146">图和表从安全性的角度演示了四种消息类：</span><span class="sxs-lookup"><span data-stu-id="a5051-146">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
-   <span data-ttu-id="a5051-147">激活消息（CreateCoordinationContext 和 CreateCoordinationContextResponse）。</span><span class="sxs-lookup"><span data-stu-id="a5051-147">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
-   <span data-ttu-id="a5051-148">注册消息（Register 和 RegisterResponse）</span><span class="sxs-lookup"><span data-stu-id="a5051-148">Registration messages (Register and RegisterResponse)</span></span>  
  
-   <span data-ttu-id="a5051-149">协议消息（Prepare、Rollback、Commit、Aborted 等）。</span><span class="sxs-lookup"><span data-stu-id="a5051-149">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
-   <span data-ttu-id="a5051-150">应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-150">Application messages.</span></span>  
  
 <span data-ttu-id="a5051-151">前三种消息类可视为事务管理器消息，本主题后面的“应用程序消息交换”将说明它们的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="a5051-151">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="a5051-152">第四种消息类是应用程序间消息，本主题后面的“消息示例”一节将对它进行说明。</span><span class="sxs-lookup"><span data-stu-id="a5051-152">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="a5051-153">本节说明 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 对这些类中每个类使用的协议绑定。</span><span class="sxs-lookup"><span data-stu-id="a5051-153">This section describes the protocol bindings used for each of these classes by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="a5051-154">本文档中使用以下 XML 命名空间和关联的前缀。</span><span class="sxs-lookup"><span data-stu-id="a5051-154">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="a5051-155">前缀</span><span class="sxs-lookup"><span data-stu-id="a5051-155">Prefix</span></span>|<span data-ttu-id="a5051-156">命名空间 URI</span><span class="sxs-lookup"><span data-stu-id="a5051-156">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="a5051-157">s11</span><span class="sxs-lookup"><span data-stu-id="a5051-157">s11</span></span>|<span data-ttu-id="a5051-158">http://schemas.xmlsoap.org/soap/envelope</span><span class="sxs-lookup"><span data-stu-id="a5051-158">http://schemas.xmlsoap.org/soap/envelope</span></span>|  
|<span data-ttu-id="a5051-159">wsa</span><span class="sxs-lookup"><span data-stu-id="a5051-159">wsa</span></span>|<span data-ttu-id="a5051-160">http://www.w3.org/2004/08/addressing</span><span class="sxs-lookup"><span data-stu-id="a5051-160">http://www.w3.org/2004/08/addressing</span></span>|  
|<span data-ttu-id="a5051-161">wscoor</span><span class="sxs-lookup"><span data-stu-id="a5051-161">wscoor</span></span>|<span data-ttu-id="a5051-162">http://schemas.xmlsoap.org/ws/2004/10/wscoor</span><span class="sxs-lookup"><span data-stu-id="a5051-162">http://schemas.xmlsoap.org/ws/2004/10/wscoor</span></span>|  
|<span data-ttu-id="a5051-163">wsat</span><span class="sxs-lookup"><span data-stu-id="a5051-163">wsat</span></span>|<span data-ttu-id="a5051-164">http://schemas.xmlsoap.org/ws/2004/10/wsat</span><span class="sxs-lookup"><span data-stu-id="a5051-164">http://schemas.xmlsoap.org/ws/2004/10/wsat</span></span>|  
|<span data-ttu-id="a5051-165">t</span><span class="sxs-lookup"><span data-stu-id="a5051-165">t</span></span>|<span data-ttu-id="a5051-166">http://schemas.xmlsoap.org/ws/2005/02/trust</span><span class="sxs-lookup"><span data-stu-id="a5051-166">http://schemas.xmlsoap.org/ws/2005/02/trust</span></span>|  
|<span data-ttu-id="a5051-167">o</span><span class="sxs-lookup"><span data-stu-id="a5051-167">o</span></span>|<span data-ttu-id="a5051-168">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="a5051-168">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="a5051-169">xsd</span><span class="sxs-lookup"><span data-stu-id="a5051-169">xsd</span></span>|<span data-ttu-id="a5051-170">http://www.w3.org/2001/XMLSchema</span><span class="sxs-lookup"><span data-stu-id="a5051-170">http://www.w3.org/2001/XMLSchema</span></span>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="a5051-171">事务管理器绑定</span><span class="sxs-lookup"><span data-stu-id="a5051-171">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="a5051-172">R1001：事务管理器必须使用 SOAP 1.1 和 WS-Addressing 2004/08 进行 WS-Atomic Transaction 和 WS-Coordination 消息交换。</span><span class="sxs-lookup"><span data-stu-id="a5051-172">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="a5051-173">应用程序消息并不限于这些绑定，将在后面进行说明。</span><span class="sxs-lookup"><span data-stu-id="a5051-173">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="a5051-174">事务管理器 HTTPS 绑定</span><span class="sxs-lookup"><span data-stu-id="a5051-174">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="a5051-175">事务管理器 HTTPS 绑定仅依赖于传输安全以在事务树中的每个发送方-接收方对之间实现安全性和建立信任。</span><span class="sxs-lookup"><span data-stu-id="a5051-175">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="a5051-176">HTTPS 传输配置</span><span class="sxs-lookup"><span data-stu-id="a5051-176">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="a5051-177">X.509 证书用于建立事务管理器标识。</span><span class="sxs-lookup"><span data-stu-id="a5051-177">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="a5051-178">要求对客户端/服务器进行身份验证，客户端/服务器授权作为实现详细信息保留：</span><span class="sxs-lookup"><span data-stu-id="a5051-178">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
-   <span data-ttu-id="a5051-179">R1111：通过网络提供的 X.509 证书必须具有与发起方计算机的完全限定域名 (FQDN) 匹配的主题名称。</span><span class="sxs-lookup"><span data-stu-id="a5051-179">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
-   <span data-ttu-id="a5051-180">B1112：DNS 必须在系统中每个发送方-接收方对之间都有效，才能使 X.509 主题名称检查成功。</span><span class="sxs-lookup"><span data-stu-id="a5051-180">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="a5051-181">激活和注册绑定配置</span><span class="sxs-lookup"><span data-stu-id="a5051-181">Activation and Registration Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a5051-182"> 要求具有通过 HTTPS 关联的请求/答复双工绑定。</span><span class="sxs-lookup"><span data-stu-id="a5051-182"> requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="a5051-183">（有关关联的更多信息和请求/答复消息交换模式的说明，请参见 WS-Atomic Transaction，第 8 节。）</span><span class="sxs-lookup"><span data-stu-id="a5051-183">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="a5051-184">2PC 协议绑定配置</span><span class="sxs-lookup"><span data-stu-id="a5051-184">2PC Protocol Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a5051-185"> 支持通过 HTTPS 发送单向（数据报）消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-185"> supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="a5051-186">消息中的关联作为实现详细信息保留。</span><span class="sxs-lookup"><span data-stu-id="a5051-186">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="a5051-187">B2131: 实现必须支持`wsa:ReferenceParameters`WS 寻址，若要实现的相关中所述[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]的 2PC 消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-187">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="a5051-188">事务管理器混合安全绑定</span><span class="sxs-lookup"><span data-stu-id="a5051-188">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="a5051-189">这是一个备选 （混合模式） 绑定，它使用传输安全和 Ws-coordination 颁发的令牌模型标识建立目的的组合。</span><span class="sxs-lookup"><span data-stu-id="a5051-189">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="a5051-190">激活和注册是在两个绑定间存在差异的仅有元素。</span><span class="sxs-lookup"><span data-stu-id="a5051-190">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="a5051-191">HTTPS 传输配置</span><span class="sxs-lookup"><span data-stu-id="a5051-191">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="a5051-192">X.509 证书用于建立事务管理器标识。</span><span class="sxs-lookup"><span data-stu-id="a5051-192">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="a5051-193">要求对客户端/服务器进行身份验证，客户端/服务器授权作为实现详细信息保留。</span><span class="sxs-lookup"><span data-stu-id="a5051-193">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="a5051-194">激活消息绑定配置</span><span class="sxs-lookup"><span data-stu-id="a5051-194">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="a5051-195">激活消息通常不参与互操作，因为他们一般出现在应用程序及其本地事务管理器之间。</span><span class="sxs-lookup"><span data-stu-id="a5051-195">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="a5051-196">B1221:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]使用双工 HTTPS 绑定 (中所述[消息传送协议](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) 激活消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-196">B1221: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="a5051-197">请求消息和答复消息是使用 WS-Addressing 2004/08 进行关联的。</span><span class="sxs-lookup"><span data-stu-id="a5051-197">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="a5051-198">WS-Atomic Transaction 规范第 8 节更详尽地说明了关联和消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="a5051-198">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
-   <span data-ttu-id="a5051-199">R1222：接收到 `CreateCoordinationContext` 后，协调程序必须颁发与机密 `SecurityContextToken` 关联的 `STx`。</span><span class="sxs-lookup"><span data-stu-id="a5051-199">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="a5051-200">在遵循 WS-Trust 规范的 `t:IssuedTokens` 标头中返回此令牌。</span><span class="sxs-lookup"><span data-stu-id="a5051-200">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
-   <span data-ttu-id="a5051-201">R1223：如果激活出现在现有的协调上下文中，则具有与现有上下文关联的 `t:IssuedTokens` 的 `SecurityContextToken` 标头必须对 `CreateCoordinationContext` 消息进行流处理。</span><span class="sxs-lookup"><span data-stu-id="a5051-201">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="a5051-202">一个新`t:IssuedTokens`标头应为附加到传出生成`wscoor:CreateCoordinationContextResponse`消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-202">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="a5051-203">注册消息绑定配置</span><span class="sxs-lookup"><span data-stu-id="a5051-203">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="a5051-204">B1231:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]使用双工 HTTPS 绑定 (中所述[消息传送协议](../../../../docs/framework/wcf/feature-details/messaging-protocols.md))。</span><span class="sxs-lookup"><span data-stu-id="a5051-204">B1231: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="a5051-205">请求消息和答复消息是使用 WS-Addressing 2004/08 进行关联的。</span><span class="sxs-lookup"><span data-stu-id="a5051-205">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="a5051-206">WS-AtomicTransaction 第 8 节更详尽地说明了关联和消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="a5051-206">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="a5051-207">R1232： 传出`wscoor:Register`的消息必须使用`IssuedTokenOverTransport`身份验证模式中所述[安全协议](../../../../docs/framework/wcf/feature-details/security-protocols.md)。</span><span class="sxs-lookup"><span data-stu-id="a5051-207">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="a5051-208">`wsse:Timestamp`必须使用对元素进行签名`SecurityContextToken``STx`颁发。</span><span class="sxs-lookup"><span data-stu-id="a5051-208">The `wsse:Timestamp` element must be signed using the `SecurityContextToken``STx` issued.</span></span> <span data-ttu-id="a5051-209">此签名是拥有与特定事务关联的令牌的证明，用于对登记事务的参与者进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a5051-209">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="a5051-210">RegistrationResponse 消息通过 HTTPS 发回。</span><span class="sxs-lookup"><span data-stu-id="a5051-210">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="a5051-211">2PC 协议绑定配置</span><span class="sxs-lookup"><span data-stu-id="a5051-211">2PC Protocol Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a5051-212"> 支持通过 HTTPS 发送单向（数据报）消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-212"> supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="a5051-213">消息中的关联作为实现详细信息保留。</span><span class="sxs-lookup"><span data-stu-id="a5051-213">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="a5051-214">B2131: 实现必须支持`wsa:ReferenceParameters`WS 寻址，若要实现的相关中所述[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]的 2PC 消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-214">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="a5051-215">应用程序消息交换</span><span class="sxs-lookup"><span data-stu-id="a5051-215">Application Message Exchange</span></span>  
 <span data-ttu-id="a5051-216">只要绑定满足下面的安全要求，应用程序就可以对应用程序间消息随意使用任何特定的绑定：</span><span class="sxs-lookup"><span data-stu-id="a5051-216">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
-   <span data-ttu-id="a5051-217">R2001：应用程序间消息必须对 `t:IssuedTokens` 标头与消息头中的 `CoordinationContext` 一起进行流处理。</span><span class="sxs-lookup"><span data-stu-id="a5051-217">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
-   <span data-ttu-id="a5051-218">R2002：必须提供 `t:IssuedToken` 的完整性和保密性。</span><span class="sxs-lookup"><span data-stu-id="a5051-218">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="a5051-219">`CoordinationContext` 标头包含 `wscoor:Identifier`。</span><span class="sxs-lookup"><span data-stu-id="a5051-219">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="a5051-220">尽管 `xsd:AnyURI` 的定义允许使用绝对和相对 URI，可是 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 仅支持 `wscoor:Identifiers`（它是绝对 URI）。</span><span class="sxs-lookup"><span data-stu-id="a5051-220">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="a5051-221">如果 `wscoor:Identifier` 的 `wscoor:CoordinationContext` 是相对 URI，则将从事务性 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务返回错误。</span><span class="sxs-lookup"><span data-stu-id="a5051-221">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="a5051-222">消息示例</span><span class="sxs-lookup"><span data-stu-id="a5051-222">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="a5051-223">CreateCoordinationContext 请求/响应消息</span><span class="sxs-lookup"><span data-stu-id="a5051-223">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="a5051-224">下面的消息遵循请求/响应模式。</span><span class="sxs-lookup"><span data-stu-id="a5051-224">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="a5051-225">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="a5051-225">CreateCoordinationContext</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="a5051-226">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="a5051-226">CreateCoordinationContextResponse</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse     
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"   
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>   
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>    
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference   
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference   
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret   
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="a5051-227">注册消息</span><span class="sxs-lookup"><span data-stu-id="a5051-227">Registration Messages</span></span>  
 <span data-ttu-id="a5051-228">下面的消息是注册消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-228">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="a5051-229">寄存器</span><span class="sxs-lookup"><span data-stu-id="a5051-229">Register</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>        
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference   
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response"></a><span data-ttu-id="a5051-230">注册响应</span><span class="sxs-lookup"><span data-stu-id="a5051-230">Register Response</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e        
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="a5051-231">两阶段提交协议消息</span><span class="sxs-lookup"><span data-stu-id="a5051-231">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="a5051-232">下面的消息与两阶段提交 (2PC) 协议相关。</span><span class="sxs-lookup"><span data-stu-id="a5051-232">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="a5051-233">提交</span><span class="sxs-lookup"><span data-stu-id="a5051-233">Commit</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security   
      s:mustUnderstand="1"   
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="a5051-234">应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-234">Application Messages</span></span>  
 <span data-ttu-id="a5051-235">下面的消息是应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="a5051-235">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="a5051-236">应用程序消息请求</span><span class="sxs-lookup"><span data-stu-id="a5051-236">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">   
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken   
          wssu:Id="IA_Certificate"   
          ValueType="...#X509v3"   
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->    
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->      
    <e:EncryptedData Id="encrypted_body"   
           Type="http://www.w3.org/2001/04/xmlenc#Content"   
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
