---
title: "安全协议版本 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f40c79ad1a6eedc2b1de4dffa9de5b48aeb8e6f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="cc955-102">安全协议版本 1.0</span><span class="sxs-lookup"><span data-stu-id="cc955-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="cc955-103">Web 服务安全协议提供 Web 服务安全机制，这些机制可满足所有现有企业的消息传递安全要求。</span><span class="sxs-lookup"><span data-stu-id="cc955-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="cc955-104">本节介绍以下 Web 服务安全协议的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 1.0 版细节（在 <xref:System.ServiceModel.Channels.SecurityBindingElement> 中实现）。</span><span class="sxs-lookup"><span data-stu-id="cc955-104">This section describes the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="cc955-105">规范/文档</span><span class="sxs-lookup"><span data-stu-id="cc955-105">Specification/Document</span></span>|<span data-ttu-id="cc955-106">Link</span><span class="sxs-lookup"><span data-stu-id="cc955-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="cc955-107">WSS：SOAP 消息安全 1.0</span><span class="sxs-lookup"><span data-stu-id="cc955-107">WSS: SOAP Message Security 1.0</span></span>|<span data-ttu-id="cc955-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span></span>|  
|<span data-ttu-id="cc955-109">WSS：用户名令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="cc955-109">WSS: Username Token Profile 1.0</span></span>|<span data-ttu-id="cc955-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="cc955-111">WSS：X509 令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="cc955-111">WSS: X509 Token Profile 1.0</span></span>|<span data-ttu-id="cc955-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="cc955-113">WSS：SAML 1.1 令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="cc955-113">WSS: SAML 1.1 Token Profile 1.0</span></span>|<span data-ttu-id="cc955-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="cc955-115">WSS：SOAP 消息安全 1.1</span><span class="sxs-lookup"><span data-stu-id="cc955-115">WSS: SOAP Message Security 1.1</span></span>|<span data-ttu-id="cc955-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span></span>|  
|<span data-ttu-id="cc955-117">WSS 用户名令牌配置文件 1.1</span><span class="sxs-lookup"><span data-stu-id="cc955-117">WSS Username Token Profile 1.1</span></span>|<span data-ttu-id="cc955-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="cc955-119">WSS：X.509 令牌配置文件 1.1</span><span class="sxs-lookup"><span data-stu-id="cc955-119">WSS: X.509 Token Profile 1.1</span></span>|<span data-ttu-id="cc955-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span></span>|  
|<span data-ttu-id="cc955-121">WSS：Kerberos 令牌配置文件 1.1</span><span class="sxs-lookup"><span data-stu-id="cc955-121">WSS: Kerberos Token Profile 1.1</span></span>|<span data-ttu-id="cc955-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span></span>|  
|<span data-ttu-id="cc955-123">WSS：SAML 1.1 令牌配置文件 1.1</span><span class="sxs-lookup"><span data-stu-id="cc955-123">WSS: SAML 1.1 Token Profile 1.1</span></span>|<span data-ttu-id="cc955-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span><span class="sxs-lookup"><span data-stu-id="cc955-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span></span>|  
|<span data-ttu-id="cc955-125">WS-Secure 对话</span><span class="sxs-lookup"><span data-stu-id="cc955-125">WS-Secure Conversation</span></span>|<span data-ttu-id="cc955-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span><span class="sxs-lookup"><span data-stu-id="cc955-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span></span>|  
|<span data-ttu-id="cc955-127">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="cc955-127">WS-Trust</span></span>|<span data-ttu-id="cc955-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span><span class="sxs-lookup"><span data-stu-id="cc955-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span></span>|  
|<span data-ttu-id="cc955-129">应用说明：</span><span class="sxs-lookup"><span data-stu-id="cc955-129">Application Note:</span></span><br /><br /> <span data-ttu-id="cc955-130">将 WS-Trust 用于 TLS 握手</span><span class="sxs-lookup"><span data-stu-id="cc955-130">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="cc955-131">即将发布</span><span class="sxs-lookup"><span data-stu-id="cc955-131">To be published</span></span>|  
|<span data-ttu-id="cc955-132">应用说明：</span><span class="sxs-lookup"><span data-stu-id="cc955-132">Application Note:</span></span><br /><br /> <span data-ttu-id="cc955-133">将 WS-Trust 用于 SPNEGO</span><span class="sxs-lookup"><span data-stu-id="cc955-133">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="cc955-134">即将发布</span><span class="sxs-lookup"><span data-stu-id="cc955-134">To be published</span></span>|  
|<span data-ttu-id="cc955-135">应用说明：</span><span class="sxs-lookup"><span data-stu-id="cc955-135">Application Note:</span></span><br /><br /> <span data-ttu-id="cc955-136">Web 服务寻址终结点引用和标识</span><span class="sxs-lookup"><span data-stu-id="cc955-136">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="cc955-137">即将发布</span><span class="sxs-lookup"><span data-stu-id="cc955-137">To be published</span></span>|  
|<span data-ttu-id="cc955-138">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="cc955-138">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="cc955-139">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="cc955-139">(2005/07)</span></span>|<span data-ttu-id="cc955-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span><span class="sxs-lookup"><span data-stu-id="cc955-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span></span><br /><br /> <span data-ttu-id="cc955-141">已根据提交到 OASIS WS-SX 技术委员会的勘误表进行了修正 http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span><span class="sxs-lookup"><span data-stu-id="cc955-141">as amended by errata submitted to OASIS WS-SX Technical Committee http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-142"> 版本 1 提供了 17 种身份验证模式，可用作 Web 服务安全配置的基础。</span><span class="sxs-lookup"><span data-stu-id="cc955-142">, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="cc955-143">每一种模式都针对一组常用部署要求进行了优化，如：</span><span class="sxs-lookup"><span data-stu-id="cc955-143">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
-   <span data-ttu-id="cc955-144">用于对客户端和服务进行身份验证的凭据。</span><span class="sxs-lookup"><span data-stu-id="cc955-144">Credentials used to authenticate client and service.</span></span>  
  
-   <span data-ttu-id="cc955-145">消息或传输安全保护机制。</span><span class="sxs-lookup"><span data-stu-id="cc955-145">Message or transport security protection mechanisms.</span></span>  
  
-   <span data-ttu-id="cc955-146">消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="cc955-146">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="cc955-147">身份验证模式</span><span class="sxs-lookup"><span data-stu-id="cc955-147">Authentication Mode</span></span>|<span data-ttu-id="cc955-148">客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="cc955-148">Client Authentication</span></span>|<span data-ttu-id="cc955-149">服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="cc955-149">Server Authentication</span></span>|<span data-ttu-id="cc955-150">模式</span><span class="sxs-lookup"><span data-stu-id="cc955-150">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="cc955-151">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-151">UserNameOverTransport</span></span>|<span data-ttu-id="cc955-152">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="cc955-152">User name/password</span></span>|<span data-ttu-id="cc955-153">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-153">X509</span></span>|<span data-ttu-id="cc955-154">传输</span><span class="sxs-lookup"><span data-stu-id="cc955-154">Transport</span></span>|  
|<span data-ttu-id="cc955-155">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-155">CertificateOverTransport</span></span>|<span data-ttu-id="cc955-156">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-156">X509</span></span>|<span data-ttu-id="cc955-157">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-157">X509</span></span>|<span data-ttu-id="cc955-158">传输</span><span class="sxs-lookup"><span data-stu-id="cc955-158">Transport</span></span>|  
|<span data-ttu-id="cc955-159">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-159">KerberosOverTransport</span></span>|<span data-ttu-id="cc955-160">Windows</span><span class="sxs-lookup"><span data-stu-id="cc955-160">Windows</span></span>|<span data-ttu-id="cc955-161">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-161">X509</span></span>|<span data-ttu-id="cc955-162">传输</span><span class="sxs-lookup"><span data-stu-id="cc955-162">Transport</span></span>|  
|<span data-ttu-id="cc955-163">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-163">IssuedTokenOverTransport</span></span>|<span data-ttu-id="cc955-164">联合</span><span class="sxs-lookup"><span data-stu-id="cc955-164">Federated</span></span>|<span data-ttu-id="cc955-165">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-165">X509</span></span>|<span data-ttu-id="cc955-166">传输</span><span class="sxs-lookup"><span data-stu-id="cc955-166">Transport</span></span>|  
|<span data-ttu-id="cc955-167">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-167">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="cc955-168">协商的 Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="cc955-168">Windows Sspi Negotiated</span></span>|<span data-ttu-id="cc955-169">协商的 Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="cc955-169">Windows Sspi Negotiated</span></span>|<span data-ttu-id="cc955-170">传输</span><span class="sxs-lookup"><span data-stu-id="cc955-170">Transport</span></span>|  
|<span data-ttu-id="cc955-171">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="cc955-171">AnonymousForCertificate</span></span>|<span data-ttu-id="cc955-172">无</span><span class="sxs-lookup"><span data-stu-id="cc955-172">None</span></span>|<span data-ttu-id="cc955-173">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-173">X509</span></span>|<span data-ttu-id="cc955-174">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-174">Message</span></span>|  
|<span data-ttu-id="cc955-175">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="cc955-175">UserNameForCertificate</span></span>|<span data-ttu-id="cc955-176">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="cc955-176">User name/password</span></span>|<span data-ttu-id="cc955-177">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-177">X509</span></span>|<span data-ttu-id="cc955-178">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-178">Message</span></span>|  
|<span data-ttu-id="cc955-179">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="cc955-179">MutualCertificate</span></span>|<span data-ttu-id="cc955-180">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-180">X509</span></span>|<span data-ttu-id="cc955-181">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-181">X509</span></span>|<span data-ttu-id="cc955-182">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-182">Message</span></span>|  
|<span data-ttu-id="cc955-183">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="cc955-183">MutualCertificateDuplex</span></span>|<span data-ttu-id="cc955-184">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-184">X509</span></span>|<span data-ttu-id="cc955-185">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-185">X509</span></span>|<span data-ttu-id="cc955-186">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-186">Message</span></span>|  
|<span data-ttu-id="cc955-187">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="cc955-187">IssuedTokenForCertificate</span></span>|<span data-ttu-id="cc955-188">联合</span><span class="sxs-lookup"><span data-stu-id="cc955-188">Federated</span></span>|<span data-ttu-id="cc955-189">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-189">X509</span></span>|<span data-ttu-id="cc955-190">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-190">Message</span></span>|  
|<span data-ttu-id="cc955-191">Kerberos</span><span class="sxs-lookup"><span data-stu-id="cc955-191">Kerberos</span></span>|<span data-ttu-id="cc955-192">Windows</span><span class="sxs-lookup"><span data-stu-id="cc955-192">Windows</span></span>|<span data-ttu-id="cc955-193">Windows</span><span class="sxs-lookup"><span data-stu-id="cc955-193">Windows</span></span>|<span data-ttu-id="cc955-194">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-194">Message</span></span>|  
|<span data-ttu-id="cc955-195">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="cc955-195">IssuedToken</span></span>|<span data-ttu-id="cc955-196">联合</span><span class="sxs-lookup"><span data-stu-id="cc955-196">Federated</span></span>|<span data-ttu-id="cc955-197">联合</span><span class="sxs-lookup"><span data-stu-id="cc955-197">Federated</span></span>|<span data-ttu-id="cc955-198">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-198">Message</span></span>|  
|<span data-ttu-id="cc955-199">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-199">SspiNegotiated</span></span>|<span data-ttu-id="cc955-200">协商的 Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="cc955-200">Windows Sspi Negotiated</span></span>|<span data-ttu-id="cc955-201">协商的 Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="cc955-201">Windows Sspi Negotiated</span></span>|<span data-ttu-id="cc955-202">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-202">Message</span></span>|  
|<span data-ttu-id="cc955-203">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-203">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="cc955-204">无</span><span class="sxs-lookup"><span data-stu-id="cc955-204">None</span></span>|<span data-ttu-id="cc955-205">X509、TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="cc955-205">X509, TLS-Nego</span></span>|<span data-ttu-id="cc955-206">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-206">Message</span></span>|  
|<span data-ttu-id="cc955-207">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-207">UserNameForSslNegotiated</span></span>|<span data-ttu-id="cc955-208">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="cc955-208">User name/password</span></span>|<span data-ttu-id="cc955-209">X509、TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="cc955-209">X509, TLS-Nego</span></span>|<span data-ttu-id="cc955-210">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-210">Message</span></span>|  
|<span data-ttu-id="cc955-211">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-211">MutualSslNegotiated</span></span>|<span data-ttu-id="cc955-212">X509</span><span class="sxs-lookup"><span data-stu-id="cc955-212">X509</span></span>|<span data-ttu-id="cc955-213">X509、TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="cc955-213">X509, TLS-Nego</span></span>|<span data-ttu-id="cc955-214">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-214">Message</span></span>|  
|<span data-ttu-id="cc955-215">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-215">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="cc955-216">联合</span><span class="sxs-lookup"><span data-stu-id="cc955-216">Federated</span></span>|<span data-ttu-id="cc955-217">X509、TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="cc955-217">X509, TLS-Nego</span></span>|<span data-ttu-id="cc955-218">消息</span><span class="sxs-lookup"><span data-stu-id="cc955-218">Message</span></span>|  
  
 <span data-ttu-id="cc955-219">使用此类身份验证模式的终结点可以使用 WS-SecurityPolicy (WS-SP) 表示其安全要求。</span><span class="sxs-lookup"><span data-stu-id="cc955-219">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="cc955-220">本文档介绍每种身份验证模式的安全标头和基础结构消息的结构，并提供策略和消息的示例。</span><span class="sxs-lookup"><span data-stu-id="cc955-220">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-221"> 利用 WS-SecureConversation 来提供安全会话支持，以保护应用程序之间的多消息交换。</span><span class="sxs-lookup"><span data-stu-id="cc955-221"> leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="cc955-222">请参见下面的“安全会话”了解实现细节。</span><span class="sxs-lookup"><span data-stu-id="cc955-222">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="cc955-223">除了身份验证模式之外，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 还提供一些设置，用以控制应用于大多数基于消息安全的身份验证模式的常见保护机制，例如：签名对加密操作的顺序、算法组、密钥派生和签名确认。</span><span class="sxs-lookup"><span data-stu-id="cc955-223">In addition to authentication modes, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="cc955-224">本文档使用以下前缀和命名空间。</span><span class="sxs-lookup"><span data-stu-id="cc955-224">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="cc955-225">前缀</span><span class="sxs-lookup"><span data-stu-id="cc955-225">Prefix</span></span>|<span data-ttu-id="cc955-226">命名空间</span><span class="sxs-lookup"><span data-stu-id="cc955-226">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="cc955-227">s</span><span class="sxs-lookup"><span data-stu-id="cc955-227">s</span></span>|<span data-ttu-id="cc955-228">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="cc955-228">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="cc955-229">sp</span><span class="sxs-lookup"><span data-stu-id="cc955-229">sp</span></span>|<span data-ttu-id="cc955-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="cc955-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span></span>|  
|<span data-ttu-id="cc955-231">a</span><span class="sxs-lookup"><span data-stu-id="cc955-231">a</span></span>|<span data-ttu-id="cc955-232">http://www.w3.org/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="cc955-232">http://www.w3.org/2005/08/addressing</span></span>|  
|<span data-ttu-id="cc955-233">wsse</span><span class="sxs-lookup"><span data-stu-id="cc955-233">wsse</span></span>|<span data-ttu-id="cc955-234">TBD – OASIS WSS 1.0 URI</span><span class="sxs-lookup"><span data-stu-id="cc955-234">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="cc955-235">wsse11</span><span class="sxs-lookup"><span data-stu-id="cc955-235">wsse11</span></span>|<span data-ttu-id="cc955-236">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="cc955-236">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="cc955-237">wsu</span><span class="sxs-lookup"><span data-stu-id="cc955-237">wsu</span></span>|<span data-ttu-id="cc955-238">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="cc955-238">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="cc955-239">ds</span><span class="sxs-lookup"><span data-stu-id="cc955-239">ds</span></span>|<span data-ttu-id="cc955-240">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="cc955-240">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="cc955-241">wst</span><span class="sxs-lookup"><span data-stu-id="cc955-241">wst</span></span>|<span data-ttu-id="cc955-242">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="cc955-242">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="cc955-243">wssc</span><span class="sxs-lookup"><span data-stu-id="cc955-243">wssc</span></span>|<span data-ttu-id="cc955-244">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="cc955-244">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="cc955-245">wsaw</span><span class="sxs-lookup"><span data-stu-id="cc955-245">wsaw</span></span>|<span data-ttu-id="cc955-246">TBD - WS-Addressing 策略命名空间</span><span class="sxs-lookup"><span data-stu-id="cc955-246">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="cc955-247">wsp</span><span class="sxs-lookup"><span data-stu-id="cc955-247">wsp</span></span>|<span data-ttu-id="cc955-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span><span class="sxs-lookup"><span data-stu-id="cc955-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span></span>|  
|<span data-ttu-id="cc955-249">mssp</span><span class="sxs-lookup"><span data-stu-id="cc955-249">mssp</span></span>|<span data-ttu-id="cc955-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="cc955-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span></span>|  
  
## <a name="1-token-profiles"></a><span data-ttu-id="cc955-251">1.令牌配置文件</span><span class="sxs-lookup"><span data-stu-id="cc955-251">1. Token Profiles</span></span>  
 <span data-ttu-id="cc955-252">Web 服务安全规范将凭据表示为安全令牌。</span><span class="sxs-lookup"><span data-stu-id="cc955-252">Web Services Security specifications represent credential as security tokens.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-253"> 支持以下令牌类型：</span><span class="sxs-lookup"><span data-stu-id="cc955-253"> supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="cc955-254">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="cc955-254">1.1 UsernameToken</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-255"> 遵循 UsernameToken10 和 UsernameToken11 配置文件，且有以下约束：</span><span class="sxs-lookup"><span data-stu-id="cc955-255"> follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="cc955-256">R1101 UsernameToken\Password 元素的 PasswordType 属性必须省略或者值为 #PasswordText（默认值）。</span><span class="sxs-lookup"><span data-stu-id="cc955-256">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="cc955-257">可以使用可扩展性实现 #PasswordDigest。</span><span class="sxs-lookup"><span data-stu-id="cc955-257">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="cc955-258">人们已经发现，#PasswordDigest 经常被误认为是足够安全的密码保护机制。</span><span class="sxs-lookup"><span data-stu-id="cc955-258">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="cc955-259">但实际上，#PasswordDigest 不可取代 UsernameToken 加密。</span><span class="sxs-lookup"><span data-stu-id="cc955-259">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="cc955-260">#PasswordDigest 的主要目的是防止重放攻击。</span><span class="sxs-lookup"><span data-stu-id="cc955-260">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="cc955-261">在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 身份验证模式下，使用消息签名可减轻重放攻击威胁。</span><span class="sxs-lookup"><span data-stu-id="cc955-261">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="cc955-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不会省略 UsernameToken 的 Nonce 和 Created 子元素。</span><span class="sxs-lookup"><span data-stu-id="cc955-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="cc955-263">这些子元素旨在帮助重放检测。</span><span class="sxs-lookup"><span data-stu-id="cc955-263">These sub-elements are intended to help replay detection.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-264"> 改用消息签名。</span><span class="sxs-lookup"><span data-stu-id="cc955-264"> uses message signatures instead.</span></span>  
  
 <span data-ttu-id="cc955-265">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) 引入了从密码派生密钥的功能。</span><span class="sxs-lookup"><span data-stu-id="cc955-265">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="cc955-266">B1103 UsernameToken 密码不得用于密钥派生，因此也不得用于加密操作。</span><span class="sxs-lookup"><span data-stu-id="cc955-266">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="cc955-267">根本原因：密码通常被视为过于脆弱，不适合用于加密操作。</span><span class="sxs-lookup"><span data-stu-id="cc955-267">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="cc955-268">1.2 X509 令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-268">1.2 X509 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-269"> 支持 X509v3 证书作为凭据类型，并且遵循 X509TokenProfile1.0 和 X509TokenProfile1.1，且有以下约束：</span><span class="sxs-lookup"><span data-stu-id="cc955-269"> supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="cc955-270">R1201 在包含 X509v3 证书时，BinarySecurityToken 元素的 ValueType 属性必须值为 #X509v3。</span><span class="sxs-lookup"><span data-stu-id="cc955-270">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="cc955-271">WSS X509 Token Profile 1.0 和 1.1 还定义了 #X509PKIPathv1 和 #PKCS7 作为值类型。</span><span class="sxs-lookup"><span data-stu-id="cc955-271">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-272"> 不支持这些类型。</span><span class="sxs-lookup"><span data-stu-id="cc955-272"> does not support these types.</span></span>  
  
 <span data-ttu-id="cc955-273">R1202 如果 SubjectKeyIdentifier (SKI) 扩展在 X509 证书中存在，wsse:KeyIdentifier 应该用于对该令牌的外部引用，并且 ValueType 属性为 #X509SubjectKeyIdentifier 且其内容为证书的 SKI 扩展的 base64 编码值。</span><span class="sxs-lookup"><span data-stu-id="cc955-273">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="cc955-274">SKI 引用已广泛实现，已证明是高度可互操作的外部引用类型。</span><span class="sxs-lookup"><span data-stu-id="cc955-274">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="cc955-275">R1203 对 X509 安全令牌的外部引用不应使用 ds:X509IssuerSerial。</span><span class="sxs-lookup"><span data-stu-id="cc955-275">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="cc955-276">R1204 如果使用 X509TokenProfile1.1，则对 X509 安全令牌的外部引用应该使用 WS-Security 1.1 引入的指纹。</span><span class="sxs-lookup"><span data-stu-id="cc955-276">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-277"> 支持 X509IssuerSerial。</span><span class="sxs-lookup"><span data-stu-id="cc955-277"> supports X509IssuerSerial.</span></span> <span data-ttu-id="cc955-278">但是，X509IssuerSerial 存在互操作性问题：[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 使用一个字符串来比较 X509IssuerSerial 的两个值。</span><span class="sxs-lookup"><span data-stu-id="cc955-278">However There are interoperability issues with X509IssuerSerial: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="cc955-279">因此，如果有人重新排序了“主题名称”的各个组成部分，并向 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务发送对证书的引用，则可能找不到该引用。</span><span class="sxs-lookup"><span data-stu-id="cc955-279">Therefore if one reorders components of the Subject Name and sends to an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="cc955-280">1.3 Kerberos 令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-280">1.3 Kerberos Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-281"> 支持 KerberosTokenProfile1.1 用于 Windows 身份验证，且有以下约束：</span><span class="sxs-lookup"><span data-stu-id="cc955-281"> supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="cc955-282">R1301 Kerberos 令牌必须携带 GSS_API 和 Kerberos 规范中定义的 GSS 包装的 Kerberos v4 AP_REQ 的值，并且必须有值为 #GSS_Kerberosv5_AP_REQ 的 ValueType 属性。</span><span class="sxs-lookup"><span data-stu-id="cc955-282">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-283"> 使用 GSS 包装的 Kerberos AP-REQ，而不是裸 AP-REQ。</span><span class="sxs-lookup"><span data-stu-id="cc955-283"> uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="cc955-284">这是一种安全最佳做法。</span><span class="sxs-lookup"><span data-stu-id="cc955-284">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="cc955-285">1.4 SAML v1.1 令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-285">1.4 SAML v1.1 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-286"> 支持针对 SAML v1.1 令牌的 WSS SAML Token Profile 1.0 和 1.1。</span><span class="sxs-lookup"><span data-stu-id="cc955-286"> supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="cc955-287">可以实现其他版本的 SAML 令牌格式。</span><span class="sxs-lookup"><span data-stu-id="cc955-287">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="cc955-288">1.5 安全上下文令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-288">1.5 Security Context Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-289"> 支持 WS-SecureCoversation 中引入的安全上下文令牌 (SCT)。</span><span class="sxs-lookup"><span data-stu-id="cc955-289"> supports the Security Context Token (SCT) introduced in WS-SecureCoversation.</span></span> <span data-ttu-id="cc955-290">SCT 用于表示在 SecureConversation 中建立的安全上下文以及下面所述的二进制协商协议 TLS 和 SSPI。</span><span class="sxs-lookup"><span data-stu-id="cc955-290">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="cc955-291">2.常用消息安全参数</span><span class="sxs-lookup"><span data-stu-id="cc955-291">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="cc955-292">2.1 时间戳</span><span class="sxs-lookup"><span data-stu-id="cc955-292">2.1 TimeStamp</span></span>  
 <span data-ttu-id="cc955-293">时间戳存在与否是使用 <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> 类的 <xref:System.ServiceModel.Channels.SecurityBindingElement> 属性控制的。</span><span class="sxs-lookup"><span data-stu-id="cc955-293">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-294"> 总是序列化带有 wsse:Created 和 wsse:Expires 字段的 wsse:TimeStamp。</span><span class="sxs-lookup"><span data-stu-id="cc955-294"> always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="cc955-295">使用签名时，总会对 wsse:TimeStamp 进行签名。</span><span class="sxs-lookup"><span data-stu-id="cc955-295">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="cc955-296">2.2 保护顺序</span><span class="sxs-lookup"><span data-stu-id="cc955-296">2.2 Protection Order</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-297"> 支持消息保护顺序“加密前签名”和“签名前加密”(Security Policy 1.1)。</span><span class="sxs-lookup"><span data-stu-id="cc955-297"> supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="cc955-298">建议使用“加密前签名”，其原因包括：除非使用 WS-Security 1.1 SignatureConfirmation 机制，否则使用“签名前加密”进行保护的消息易受签名替换攻击，并且对加密内容进行签名使得审核更加困难。</span><span class="sxs-lookup"><span data-stu-id="cc955-298">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="cc955-299">2.3 签名保护</span><span class="sxs-lookup"><span data-stu-id="cc955-299">2.3 Signature Protection</span></span>  
 <span data-ttu-id="cc955-300">在使用“签名前加密”时，建议保护签名以防止对加密内容或签名密钥进行猜测的蛮力攻击（尤其是在自定义令牌与弱密钥材料一起使用时）。</span><span class="sxs-lookup"><span data-stu-id="cc955-300">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="cc955-301">2.4 算法组</span><span class="sxs-lookup"><span data-stu-id="cc955-301">2.4 Algorithm Suite</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-302"> 支持 Security Policy 1.1 中列出的所有算法组。</span><span class="sxs-lookup"><span data-stu-id="cc955-302"> supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="cc955-303">2.5 密钥派生</span><span class="sxs-lookup"><span data-stu-id="cc955-303">2.5 Key Derivation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-304"> 使用 WS-SecureConversation 中所述的“对称密钥的密钥派生”。</span><span class="sxs-lookup"><span data-stu-id="cc955-304"> uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="cc955-305">2.6 签名确认</span><span class="sxs-lookup"><span data-stu-id="cc955-305">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="cc955-306">签名确认可用于防止中间人攻击以保护签名集。</span><span class="sxs-lookup"><span data-stu-id="cc955-306">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="cc955-307">2.7 安全标头布局</span><span class="sxs-lookup"><span data-stu-id="cc955-307">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="cc955-308">每种身份验证模式都描述一种特定的安全标头布局。</span><span class="sxs-lookup"><span data-stu-id="cc955-308">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="cc955-309">安全标头内的元素为半有序。</span><span class="sxs-lookup"><span data-stu-id="cc955-309">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="cc955-310">为了定义安全标头子元素的顺序，WS-Security Policy 定义了以下安全标头布局模式：</span><span class="sxs-lookup"><span data-stu-id="cc955-310">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc955-311">Strict</span><span class="sxs-lookup"><span data-stu-id="cc955-311">Strict</span></span>|<span data-ttu-id="cc955-312">根据“使用前先声明”的一般原则，各项按照 Security Policy 第 7.7.1 节中所述的编号布局规则添加到安全标头中。</span><span class="sxs-lookup"><span data-stu-id="cc955-312">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="cc955-313">Lax</span><span class="sxs-lookup"><span data-stu-id="cc955-313">Lax</span></span>|<span data-ttu-id="cc955-314">各项以任何符合“WSS: SOAP 消息安全”的顺序添加到安全标头中。</span><span class="sxs-lookup"><span data-stu-id="cc955-314">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="cc955-315">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="cc955-315">LaxTimestampFirst</span></span>|<span data-ttu-id="cc955-316">与 Lax 相同，只是安全标头中的第一项必须为 wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="cc955-316">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="cc955-317">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="cc955-317">LaxTimestampLast</span></span>|<span data-ttu-id="cc955-318">与 lax 相同，只是安全标头中的最后一项必须为 wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="cc955-318">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-319"> 支持安全标头布局的所有四种模式。</span><span class="sxs-lookup"><span data-stu-id="cc955-319"> supports all four modes for security header layout.</span></span> <span data-ttu-id="cc955-320">以下针对身份验证模式的安全标头结构和消息示例遵循“Strict”模式。</span><span class="sxs-lookup"><span data-stu-id="cc955-320">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="cc955-321">2.常用消息安全参数</span><span class="sxs-lookup"><span data-stu-id="cc955-321">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="cc955-322">本节介绍每种身份验证模式的示例策略以及演示客户端和服务所交换的消息中的安全标头结构的示例。</span><span class="sxs-lookup"><span data-stu-id="cc955-322">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="cc955-323">6.1 传输保护</span><span class="sxs-lookup"><span data-stu-id="cc955-323">6.1 Transport Protection</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cc955-324"> 提供了五种使用安全传输来保护消息的身份验证模式：UserNameOverTransport、CertificateOverTransport、KerberosOverTransport、IssuedTokenOverTransport 和 SspiNegotiatedOverTransport。</span><span class="sxs-lookup"><span data-stu-id="cc955-324"> provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="cc955-325">这些身份验证模式是使用 SecurityPolicy 中描述的传输绑定构造的。</span><span class="sxs-lookup"><span data-stu-id="cc955-325">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="cc955-326">对于 UserNameOverTransport 身份验证模式，UsernameToken 是签名支持令牌。</span><span class="sxs-lookup"><span data-stu-id="cc955-326">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="cc955-327">对于其他身份验证模式，令牌作为签名认可令牌出现。</span><span class="sxs-lookup"><span data-stu-id="cc955-327">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="cc955-328">SecurityPolicy 的附录 C.1.2 和 C.1.3 详细介绍了安全标头布局。</span><span class="sxs-lookup"><span data-stu-id="cc955-328">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="cc955-329">下面的示例安全标头演示给定身份验证模式的 Strict 布局。</span><span class="sxs-lookup"><span data-stu-id="cc955-329">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="cc955-330">任何情况下，令牌的“Derived Keys”属性的值总是为“false”。</span><span class="sxs-lookup"><span data-stu-id="cc955-330">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="cc955-331">传输绑定的各个属性的值如下：</span><span class="sxs-lookup"><span data-stu-id="cc955-331">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="cc955-332">时间戳：true</span><span class="sxs-lookup"><span data-stu-id="cc955-332">Timestamp: true</span></span>  
  
 <span data-ttu-id="cc955-333">安全标头布局：Strict</span><span class="sxs-lookup"><span data-stu-id="cc955-333">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="cc955-334">算法组：Basic256</span><span class="sxs-lookup"><span data-stu-id="cc955-334">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="cc955-335">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-335">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="cc955-336">在此身份验证模式下，客户端使用“用户名令牌”进行身份验证，该令牌作为签名支持令牌（总是从发起方发送到接收方）出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-336">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="cc955-337">在传输层，服务是用 X.509 证书进行身份验证的。</span><span class="sxs-lookup"><span data-stu-id="cc955-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="cc955-338">所用绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="cc955-338">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="cc955-339">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />   
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="cc955-340">安全标头布局</span><span class="sxs-lookup"><span data-stu-id="cc955-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="cc955-341">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-341">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-342">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="cc955-343">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-343">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="cc955-344">在此身份验证模式下，客户端使用 X.509 证书进行身份验证，该证书作为认可支持令牌（总是从发起方发送到接收方）出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-344">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="cc955-345">在传输层，服务是用 X.509 证书进行身份验证的。</span><span class="sxs-lookup"><span data-stu-id="cc955-345">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="cc955-346">所用绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="cc955-346">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="cc955-347">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-347">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />   
              <sp:WssX509V3Token10 />   
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="cc955-348">安全标头布局</span><span class="sxs-lookup"><span data-stu-id="cc955-348">Security Header Layout</span></span>  
  
 <span data-ttu-id="cc955-349">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-349">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-350">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-350">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="cc955-351">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-351">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="cc955-352">在此身份验证模式下，客户端不向服务进行身份验证，而是出示一个由安全令牌服务 (STS) 颁发的令牌，并证明掌握了共享密钥。</span><span class="sxs-lookup"><span data-stu-id="cc955-352">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="cc955-353">颁发的令牌作为认可支持令牌（总是从发起方发送到接收方）出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-353">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="cc955-354">在传输层，服务是用 X.509 证书进行身份验证的。</span><span class="sxs-lookup"><span data-stu-id="cc955-354">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="cc955-355">绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="cc955-355">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="cc955-356">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-356">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>   
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />   
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="cc955-357">安全标头布局</span><span class="sxs-lookup"><span data-stu-id="cc955-357">Security Header Layout</span></span>  
  
 <span data-ttu-id="cc955-358">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-358">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-359">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-359">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="cc955-360">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-360">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="cc955-361">在此身份验证模式下，客户端使用 Kerberos 票证向服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-361">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="cc955-362">Kerberos 令牌作为认可支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-362">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="cc955-363">在传输层，服务是用 X.509 证书进行身份验证的。</span><span class="sxs-lookup"><span data-stu-id="cc955-363">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="cc955-364">绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="cc955-364">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="cc955-365">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-365">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />   
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="cc955-366">安全标头布局</span><span class="sxs-lookup"><span data-stu-id="cc955-366">Security Header Layout</span></span>  
  
 <span data-ttu-id="cc955-367">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-367">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-368">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-368">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="cc955-369">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="cc955-369">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="cc955-370">在此模式下，将使用协商协议来执行客户端和服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-370">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="cc955-371">如果可能，就使用 Kerberos，否则使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="cc955-371">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="cc955-372">产生的 SCT 作为认可支持令牌（总是从发起方发送到接收方）出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-372">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="cc955-373">在传输层，服务还是由 X.509 证书另外进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-373">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="cc955-374">所用绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="cc955-374">The binding used is a transport binding.</span></span> <span data-ttu-id="cc955-375">“SPNEGO”（协商）描述 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 如何将 SSPI 二进制协商协议用于 WS-Trust。</span><span class="sxs-lookup"><span data-stu-id="cc955-375">"SPNEGO" (negotiation) describes how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="cc955-376">在通过 SPNEGO 握手建立 SCT 之后，本节将介绍安全标头示例。</span><span class="sxs-lookup"><span data-stu-id="cc955-376">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="cc955-377">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />   
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="cc955-378">安全标头示例</span><span class="sxs-lookup"><span data-stu-id="cc955-378">Security Header Examples</span></span>  
 <span data-ttu-id="cc955-379">在使用 WS-Trust 二进制协商通过 SPNEGO 握手建立安全上下文令牌之后，应用程序消息将具有如下结构的安全标头。</span><span class="sxs-lookup"><span data-stu-id="cc955-379">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="cc955-380">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-380">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-381">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-381">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="cc955-382">6.2 将 X.509 证书用于服务身份验证</span><span class="sxs-lookup"><span data-stu-id="cc955-382">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="cc955-383">本节介绍以下身份验证模式：MutualCertificate WSS1.0、Mutual CertificateDuplex、MutualCertificate WSS1.1、AnonymousForCertificate、UserNameForCertificate 和 IssuedTokenForCertificate。</span><span class="sxs-lookup"><span data-stu-id="cc955-383">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="cc955-384">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="cc955-384">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="cc955-385">在此身份验证模式下，客户端使用 X.509 证书进行身份验证，该证书作为发起方令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="cc955-386">同样使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="cc955-387">所用绑定为带有以下属性值的非对称绑定：</span><span class="sxs-lookup"><span data-stu-id="cc955-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="cc955-388">发起方令牌：客户端的 X.509 证书，包含模式设置为 …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="cc955-388">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="cc955-389">接收方令牌：服务器的 X.509 证书，包含模式设置为 …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="cc955-389">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="cc955-390">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="cc955-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="cc955-391">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="cc955-392">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="cc955-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="cc955-393">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="cc955-394">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-395">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-396">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-396">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-397">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-397">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-398">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-398">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="cc955-399">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-399">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-400">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-400">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="cc955-401">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="cc955-401">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="cc955-402">在此身份验证模式下，客户端使用 X.509 证书进行身份验证，该证书作为发起方令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-402">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="cc955-403">同样使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-403">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="cc955-404">所用绑定为带有以下属性值的非对称绑定：</span><span class="sxs-lookup"><span data-stu-id="cc955-404">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="cc955-405">发起方令牌：客户端的 X509 证书，包含模式设置为 …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="cc955-405">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="cc955-406">接收方令牌：服务器的 X509 证书，包含模式设置为 …/IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="cc955-406">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="cc955-407">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="cc955-407">Token Protection: False</span></span>  
  
 <span data-ttu-id="cc955-408">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-408">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="cc955-409">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="cc955-409">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="cc955-410">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-410">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="cc955-411">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-411">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-412">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-412">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-413">请求和响应</span><span class="sxs-lookup"><span data-stu-id="cc955-413">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-414">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-414">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-415">请求和响应</span><span class="sxs-lookup"><span data-stu-id="cc955-415">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="cc955-416">6.2.3 将 SymmetricBinding 用于 X.509 服务身份验证</span><span class="sxs-lookup"><span data-stu-id="cc955-416">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="cc955-417">“WSS10”对 X509 令牌方案提供有限支持。</span><span class="sxs-lookup"><span data-stu-id="cc955-417">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="cc955-418">例如，如果消息仅使用服务 X509 令牌，则无法为其提供签名和加密保护。</span><span class="sxs-lookup"><span data-stu-id="cc955-418">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="cc955-419">“WSS11”将 EncryptedKey 用作对称令牌。</span><span class="sxs-lookup"><span data-stu-id="cc955-419">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="cc955-420">现在，为服务的 X.509 证书加密的临时密钥可同时用于请求和响应消息保护。</span><span class="sxs-lookup"><span data-stu-id="cc955-420">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="cc955-421">下面第 6.4 节中介绍的身份验证模式使用此模式。</span><span class="sxs-lookup"><span data-stu-id="cc955-421">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="cc955-422">WS-SecurityPolicy 描述了此模式，即将 SymmetricBinding 用于服务 X509 令牌作为保护令牌。</span><span class="sxs-lookup"><span data-stu-id="cc955-422">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="cc955-423">身份验证模式 AnonymousForCertificate、UsernameForCertificate、MutualCertificate WSS11 和 IssuedTokenForCertificate 都使用具有以下属性值的类似的 sp:SymmetricBinding 实例：</span><span class="sxs-lookup"><span data-stu-id="cc955-423">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="cc955-424">保护令牌：服务器的 X509 证书，包含模式设置为 …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="cc955-424">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="cc955-425">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="cc955-425">Token Protection: False</span></span>  
  
 <span data-ttu-id="cc955-426">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-426">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="cc955-427">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="cc955-427">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="cc955-428">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-428">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="cc955-429">上述身份验证模式的区别仅在于它们所使用的支持令牌。</span><span class="sxs-lookup"><span data-stu-id="cc955-429">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="cc955-430">AnonymousForCertificate 没有任何支持令牌，MutualCertificate WSS 1.1 将客户端的 X509 证书作为认可支持令牌，UserNameForCertificate 将“用户名令牌”作为签名支持令牌，而 IssuedTokenForCertificate 将颁发的令牌作为认可支持令牌。</span><span class="sxs-lookup"><span data-stu-id="cc955-430">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="cc955-431">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-431">Policy</span></span>  
  
 <span data-ttu-id="cc955-432">对称绑定</span><span class="sxs-lookup"><span data-stu-id="cc955-432">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireThumbprintReference />   
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
          <sp:RequireSignatureConfirmation />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="cc955-433">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="cc955-433">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="cc955-434">在此身份验证模式下，客户端是匿名的，而使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-434">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="cc955-435">所用绑定为 6.4.2 中所述的对称绑定的实例。</span><span class="sxs-lookup"><span data-stu-id="cc955-435">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="cc955-436">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-436">Policy</span></span>  
  
 <span data-ttu-id="cc955-437">请参见上面 6.2.3 中的“策略”以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="cc955-437">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-438">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-438">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-439">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-439">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-440">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-440">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-441">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-441">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-442">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-442">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-443">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-443">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="cc955-444">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="cc955-444">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="cc955-445">在此身份验证模式下，客户端使用“用户名令牌”向服务进行身份验证，该令牌作为签名支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-445">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="cc955-446">服务使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-446">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="cc955-447">所用绑定为对称绑定，其保护令牌是由客户端生成的密钥，用服务的公钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="cc955-447">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="cc955-448">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-448">Policy</span></span>  
  
 <span data-ttu-id="cc955-449">请参见上面 6.2.3 中的“策略”以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="cc955-449">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="cc955-450">签名支持令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-450">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-451">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-451">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-452">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-452">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-453">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-453">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-454">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-454">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-455">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-455">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-456">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-456">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="cc955-457">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="cc955-457">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="cc955-458">在此身份验证模式下，客户端使用 X.509 证书进行身份验证，该证书作为认可支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-458">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="cc955-459">同样使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-459">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="cc955-460">所用绑定为对称绑定，其保护令牌是由客户端生成的密钥，用服务的公钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="cc955-460">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="cc955-461">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-461">Policy</span></span>  
  
 <span data-ttu-id="cc955-462">请参见 6.2.3 中的“策略”以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="cc955-462">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="cc955-463">认可支持令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-463">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-464">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-464">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-465">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-466">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-467">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-467">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-468">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-468">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-469">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-469">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="cc955-470">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="cc955-470">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="cc955-471">在此身份验证模式下，客户端不向服务进行身份验证，而是出示一个由 STS 颁发的令牌，并证明掌握了共享密钥。</span><span class="sxs-lookup"><span data-stu-id="cc955-471">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="cc955-472">颁发的令牌作为认可支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-472">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="cc955-473">服务使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-473">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="cc955-474">所用绑定为对称绑定，其保护令牌是由客户端生成的密钥，用服务的公钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="cc955-474">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="cc955-475">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-475">Policy</span></span>  
  
 <span data-ttu-id="cc955-476">请参见上面的 6.2.3 以了解绑定详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc955-476">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="cc955-477">认可支持令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-477">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />   
       <sp:RequireInternalReference />   
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-478">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-478">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-479">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-479">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-480">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-480">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-481">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-481">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-482">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-482">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-483">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-483">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="cc955-484">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="cc955-484">6.3 Kerberos</span></span>  
 <span data-ttu-id="cc955-485">在此身份验证模式下，客户端使用 Kerberos 票证向服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-485">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="cc955-486">该票证还提供服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-486">That same ticket also provides server authentication.</span></span> <span data-ttu-id="cc955-487">所用绑定为对称绑定，具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="cc955-487">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="cc955-488">保护令牌：Kerberos 票证，包含模式设置为 .../IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="cc955-488">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="cc955-489">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="cc955-489">Token Protection: False</span></span>  
  
 <span data-ttu-id="cc955-490">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-490">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="cc955-491">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="cc955-491">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="cc955-492">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-492">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="cc955-493">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-493">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:WssGssKerberosV5ApReqToken11 />   
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-494">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-494">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-495">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-495">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-496">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-496">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-497">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-497">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-498">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-498">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-499">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-499">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="cc955-500">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="cc955-500">6.4 IssuedToken</span></span>  
 <span data-ttu-id="cc955-501">在此身份验证模式下，客户端不向服务进行身份验证，而是提供一个由 STS 颁发的令牌，并证明掌握了共享密钥。</span><span class="sxs-lookup"><span data-stu-id="cc955-501">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="cc955-502">服务也不向客户端进行身份验证，而是由 STS 将共享密钥作为颁发的令牌的一部分进行加密，这样，只有服务才能解密该密钥。</span><span class="sxs-lookup"><span data-stu-id="cc955-502">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="cc955-503">所用绑定为对称绑定，具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="cc955-503">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="cc955-504">保护令牌：颁发的令牌，包含模式设置为 .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="cc955-504">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="cc955-505">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="cc955-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="cc955-506">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="cc955-507">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="cc955-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="cc955-508">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-508">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="cc955-509">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-509">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>   
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireInternalReference />   
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-510">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-510">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-511">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-511">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-512">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-512">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-513">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-513">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-514">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-514">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-515">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-515">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="cc955-516">6.5 将 SslNegotiated 用于服务身份验证</span><span class="sxs-lookup"><span data-stu-id="cc955-516">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="cc955-517">本节介绍的一组身份验证模式将对称绑定用于保护令牌，作为安全上下文令牌（符合 WS-SecureConversation (WS-SC)），其键值是通过对 WS-Trust (WS-T) RST/RSTR 消息执行 TLS 协议进行协商的。</span><span class="sxs-lookup"><span data-stu-id="cc955-517">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="cc955-518">有关使用 WS-Trust 实现 TLS 握手的详细信息，请参见 TLSNEGO 中的内容。</span><span class="sxs-lookup"><span data-stu-id="cc955-518">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="cc955-519">此处的消息示例中，我们假设已通过握手建立了带有关联安全上下文的 SCT。</span><span class="sxs-lookup"><span data-stu-id="cc955-519">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="cc955-520">所用绑定为对称绑定，具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="cc955-520">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="cc955-521">保护令牌：SslContextToken，包含模式设置为 .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="cc955-521">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="cc955-522">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="cc955-522">Token Protection: False</span></span>  
  
 <span data-ttu-id="cc955-523">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-523">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="cc955-524">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="cc955-524">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="cc955-525">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-525">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="cc955-526">6.5.1 SslNegotiated 服务身份验证的策略</span><span class="sxs-lookup"><span data-stu-id="cc955-526">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="cc955-527">本节介绍的所有身份验证模式的策略都相似，唯一的区别在于，所用的特定签名支持令牌或认可令牌不相同。</span><span class="sxs-lookup"><span data-stu-id="cc955-527">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>   
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="cc955-528">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-528">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="cc955-529">在此身份验证模式下，客户端是匿名的，而使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-529">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="cc955-530">所用绑定是对称绑定的一个实例，如上面 6.5.1 中所述。</span><span class="sxs-lookup"><span data-stu-id="cc955-530">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="cc955-531">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-531">Policy</span></span>  
  
 <span data-ttu-id="cc955-532">请参见上面 6.5.1 中的“策略”以了解绑定详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc955-532">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-533">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-533">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-534">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-534">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-535">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-535">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-536">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-536">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-537">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-537">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-538">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-538">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="cc955-539">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-539">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="cc955-540">在此身份验证模式下，客户端使用“用户名令牌”进行身份验证，该令牌作为签名支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-540">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="cc955-541">使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-541">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="cc955-542">所用绑定是对称绑定的一个实例，如上面 6.5.1 中所述。</span><span class="sxs-lookup"><span data-stu-id="cc955-542">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="cc955-543">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-543">Policy</span></span>  
  
 <span data-ttu-id="cc955-544">请参见上面的第 6.5.1 节以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="cc955-544">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="cc955-545">签名支持令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-545">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-546">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-546">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-547">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-547">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-548">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-548">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-549">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-549">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-550">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-550">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-551">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-551">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="cc955-552">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-552">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="cc955-553">在此身份验证模式下，客户端不向服务进行身份验证，而是出示一个由 STS 颁发的令牌，并证明掌握了共享密钥。</span><span class="sxs-lookup"><span data-stu-id="cc955-553">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="cc955-554">颁发的令牌作为认可支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="cc955-554">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="cc955-555">使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-555">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="cc955-556">所用绑定是对称绑定的一个实例，如上面 6.5.1 中所述。</span><span class="sxs-lookup"><span data-stu-id="cc955-556">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="cc955-557">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-557">Policy</span></span>  
  
 <span data-ttu-id="cc955-558">请参见上面的第 6.5.1 节以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="cc955-558">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="cc955-559">认可支持令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-559">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>   
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />   
        <sp:RequireInternalReference />   
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-560">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-560">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-561">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-561">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-562">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-562">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-563">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-563">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-564">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-564">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-565">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-565">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="cc955-566">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-566">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="cc955-567">在此身份验证模式下，客户端和服务都使用 X.509 证书进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-567">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="cc955-568">所用绑定是对称绑定的一个实例，如上面 6.5.1 中所述。</span><span class="sxs-lookup"><span data-stu-id="cc955-568">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="cc955-569">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-569">Policy</span></span>  
  
 <span data-ttu-id="cc955-570">请参见上面的第 6.5.1 节以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="cc955-570">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="cc955-571">认可支持令牌</span><span class="sxs-lookup"><span data-stu-id="cc955-571">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-572">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-572">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-573">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-573">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-574">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-574">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-575">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-575">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-576">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-576">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-577">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-577">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="cc955-578">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="cc955-578">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="cc955-579">在此身份验证模式下，将使用协商协议来执行客户端和服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-579">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="cc955-580">如果可能，就使用 Kerberos，否则使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="cc955-580">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="cc955-581">所用绑定为对称绑定，具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="cc955-581">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="cc955-582">保护令牌：SpnegoContextToken，包含模式设置为 .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="cc955-582">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="cc955-583">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="cc955-583">Token Protection: False</span></span>  
  
 <span data-ttu-id="cc955-584">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-584">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="cc955-585">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="cc955-585">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="cc955-586">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="cc955-586">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="cc955-587">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-587">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-588">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-588">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-589">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-589">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-590">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-590">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-591">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-591">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-592">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-592">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-593">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-593">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="cc955-594">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="cc955-594">6.7 SecureConversation</span></span>  
 <span data-ttu-id="cc955-595">所用绑定为对称绑定，保护令牌为符合 WS-SecureConversation (WS-SC) 的 SCT。</span><span class="sxs-lookup"><span data-stu-id="cc955-595">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="cc955-596">该 SCT 是根据嵌套的绑定使用 WS-Trust (WS-Trust) 或 WS-SecureConversation (WS-SC) 协商的，该嵌套绑定本身是使用协商协议的对称绑定。</span><span class="sxs-lookup"><span data-stu-id="cc955-596">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="cc955-597">如果可能，协商协议将使用 Kerberos 来执行客户端和服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc955-597">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="cc955-598">如果无法使用 Kerberos，则退而使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="cc955-598">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="cc955-599">策略</span><span class="sxs-lookup"><span data-stu-id="cc955-599">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />   
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />   
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />   
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />   
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />   
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />   
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />   
                          <sp:EncryptSignature />   
                          <sp:OnlySignEntireHeadersAndBody />   
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />   
                          <sp:MustSupportRefIssuerSerial />   
                          <sp:MustSupportRefThumbprint />   
                          <sp:MustSupportRefEncryptedKey />   
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />   
                          <sp:RequireClientEntropy />   
                          <sp:RequireServerEntropy />   
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="cc955-600">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="cc955-600">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="cc955-601">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-601">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-602">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-602">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="cc955-603">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="cc955-603">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="cc955-604">请求</span><span class="sxs-lookup"><span data-stu-id="cc955-604">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="cc955-605">响应</span><span class="sxs-lookup"><span data-stu-id="cc955-605">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
