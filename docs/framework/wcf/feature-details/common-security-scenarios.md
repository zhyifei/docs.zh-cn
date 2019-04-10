---
title: 常用安全方案
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: af58d6b529fba32380bedb9a892a2b1fd4807d96
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199266"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="3bb56-102">常用安全方案</span><span class="sxs-lookup"><span data-stu-id="3bb56-102">Common Security Scenarios</span></span>
<span data-ttu-id="3bb56-103">本节中的主题对众多可能的客户端和服务安全配置进行分类。</span><span class="sxs-lookup"><span data-stu-id="3bb56-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="3bb56-104">配置会随多种因素而变化。</span><span class="sxs-lookup"><span data-stu-id="3bb56-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="3bb56-105">例如，服务或客户端是否位于 Intranet 上，或者安全性是由 Windows 提供还是由传输（如 HTTPS）提供。</span><span class="sxs-lookup"><span data-stu-id="3bb56-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bb56-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="3bb56-106">In This Section</span></span>  
 [<span data-ttu-id="3bb56-107">不安全的 Internet 客户端和服务</span><span class="sxs-lookup"><span data-stu-id="3bb56-107">Internet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 <span data-ttu-id="3bb56-108">一个公共的、不安全的客户端和服务的示例。</span><span class="sxs-lookup"><span data-stu-id="3bb56-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="3bb56-109">不安全的 Intranet 客户端和服务</span><span class="sxs-lookup"><span data-stu-id="3bb56-109">Intranet Unsecured Client and Service</span></span>](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="3bb56-110">一个基本的 Windows Communication Foundation (WCF) 服务开发提供到 WCF 应用程序安全的专用网络上的信息。</span><span class="sxs-lookup"><span data-stu-id="3bb56-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="3bb56-111">通过基本身份验证确保的传输安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-111">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 <span data-ttu-id="3bb56-112">应用程序允许客户端使用自定义身份验证进行登录。</span><span class="sxs-lookup"><span data-stu-id="3bb56-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="3bb56-113">通过 Windows 身份验证确保的传输安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-113">Transport Security with Windows Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 <span data-ttu-id="3bb56-114">显示由 Windows 安全保护的客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="3bb56-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="3bb56-115">匿名客户端的传输安全性</span><span class="sxs-lookup"><span data-stu-id="3bb56-115">Transport Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="3bb56-116">此方案使用传输安全（如 HTTPS）确保保密性和完整性。</span><span class="sxs-lookup"><span data-stu-id="3bb56-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="3bb56-117">利用证书身份验证的传输安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-117">Transport Security with Certificate Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="3bb56-118">显示由证书保护的客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="3bb56-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="3bb56-119">匿名客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-119">Message Security with an Anonymous Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="3bb56-120">显示客户端和受保护的 WCF 消息安全的服务。</span><span class="sxs-lookup"><span data-stu-id="3bb56-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="3bb56-121">用户名客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-121">Message Security with a User Name Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 <span data-ttu-id="3bb56-122">客户端是一个 Windows 窗体应用程序，允许客户端使用域用户名和密码登录。</span><span class="sxs-lookup"><span data-stu-id="3bb56-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="3bb56-123">使用证书客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-123">Message Security with a Certificate Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 <span data-ttu-id="3bb56-124">服务器有多个证书，每个客户端各有一个证书。</span><span class="sxs-lookup"><span data-stu-id="3bb56-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="3bb56-125">通过传输层安全 (TLS) 协商建立安全上下文。</span><span class="sxs-lookup"><span data-stu-id="3bb56-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="3bb56-126">Windows 客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-126">Message Security with a Windows Client</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 <span data-ttu-id="3bb56-127">证书客户端的变体。</span><span class="sxs-lookup"><span data-stu-id="3bb56-127">A variation of the certificate client.</span></span> <span data-ttu-id="3bb56-128">服务器有多个证书，每个客户端各有一个证书。</span><span class="sxs-lookup"><span data-stu-id="3bb56-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="3bb56-129">通过 TLS 协商建立安全上下文。</span><span class="sxs-lookup"><span data-stu-id="3bb56-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="3bb56-130">没有凭据协商的 Windows 客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-130">Message Security with a Windows Client without Credential Negotiation</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="3bb56-131">显示由 Kerberos 域保护的客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="3bb56-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="3bb56-132">使用相互证书的消息安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-132">Message Security with Mutual Certificates</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 <span data-ttu-id="3bb56-133">服务器有多个证书，每个客户端各有一个证书。</span><span class="sxs-lookup"><span data-stu-id="3bb56-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="3bb56-134">服务器证书随应用程序一起分发，而可在带外使用。</span><span class="sxs-lookup"><span data-stu-id="3bb56-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="3bb56-135">使用已颁发令牌的消息安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-135">Message Security with Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 <span data-ttu-id="3bb56-136">允许在独立域间建立信任的联合安全。</span><span class="sxs-lookup"><span data-stu-id="3bb56-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="3bb56-137">受信任的子系统</span><span class="sxs-lookup"><span data-stu-id="3bb56-137">Trusted Subsystem</span></span>](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 <span data-ttu-id="3bb56-138">客户端访问分布在网络上的一个或多个 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="3bb56-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="3bb56-139">Web 服务访问必须加以保护的其他资源（如数据库或其他 Web 服务）。</span><span class="sxs-lookup"><span data-stu-id="3bb56-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3bb56-140">参考</span><span class="sxs-lookup"><span data-stu-id="3bb56-140">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="3bb56-141">相关章节</span><span class="sxs-lookup"><span data-stu-id="3bb56-141">Related Sections</span></span>  
 [<span data-ttu-id="3bb56-142">授权</span><span class="sxs-lookup"><span data-stu-id="3bb56-142">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="3bb56-143">安全性概述</span><span class="sxs-lookup"><span data-stu-id="3bb56-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [<span data-ttu-id="3bb56-144">安全性</span><span class="sxs-lookup"><span data-stu-id="3bb56-144">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="3bb56-145">绑定与安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-145">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="3bb56-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="3bb56-146">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [<span data-ttu-id="3bb56-147">身份验证</span><span class="sxs-lookup"><span data-stu-id="3bb56-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="3bb56-148">授权</span><span class="sxs-lookup"><span data-stu-id="3bb56-148">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [<span data-ttu-id="3bb56-149">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="3bb56-149">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="3bb56-150">审核</span><span class="sxs-lookup"><span data-stu-id="3bb56-150">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="3bb56-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bb56-151">See also</span></span>

- [<span data-ttu-id="3bb56-152">安全指导和最佳做法</span><span class="sxs-lookup"><span data-stu-id="3bb56-152">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [<span data-ttu-id="3bb56-153">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="3bb56-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
