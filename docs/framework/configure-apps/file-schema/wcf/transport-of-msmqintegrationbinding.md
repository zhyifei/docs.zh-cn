---
title: "&lt;msmqIntegrationBinding&gt; 的 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dc4f3cb08436f0f1af2e559c924446faa7b870c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="e378d-102">&lt;msmqIntegrationBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="e378d-102">&lt;transport&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="e378d-103">定义消息队列集成传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="e378d-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="e378d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e378d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e378d-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e378d-105">\<bindings></span></span>  
<span data-ttu-id="e378d-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="e378d-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="e378d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e378d-107">\<binding></span></span>  
<span data-ttu-id="e378d-108">\<security></span><span class="sxs-lookup"><span data-stu-id="e378d-108">\<security></span></span>  
<span data-ttu-id="e378d-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="e378d-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e378d-110">语法</span><span class="sxs-lookup"><span data-stu-id="e378d-110">Syntax</span></span>  
  
```xml  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e378d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e378d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e378d-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e378d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e378d-113">特性</span><span class="sxs-lookup"><span data-stu-id="e378d-113">Attributes</span></span>  
  
|<span data-ttu-id="e378d-114">特性</span><span class="sxs-lookup"><span data-stu-id="e378d-114">Attribute</span></span>|<span data-ttu-id="e378d-115">描述</span><span class="sxs-lookup"><span data-stu-id="e378d-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="e378d-116">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e378d-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="e378d-117">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="e378d-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="e378d-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e378d-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e378d-119">-None： 无身份验证。</span><span class="sxs-lookup"><span data-stu-id="e378d-119">-   None: No authentication.</span></span><br /><span data-ttu-id="e378d-120">-WindowsDomain： 身份验证机制使用 Active Directory 获取与消息关联的 SID 的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e378d-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="e378d-121">然后使用它来检查队列的 ACL 以确保用户有权写入队列。</span><span class="sxs-lookup"><span data-stu-id="e378d-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="e378d-122">-证书： 通道从证书存储中获取的证书。</span><span class="sxs-lookup"><span data-stu-id="e378d-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="e378d-123">默认值为 WindowsDomain。</span><span class="sxs-lookup"><span data-stu-id="e378d-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="e378d-124">此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。</span><span class="sxs-lookup"><span data-stu-id="e378d-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="e378d-125">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="e378d-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="e378d-126">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e378d-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e378d-127">-   RC4Stream</span><span class="sxs-lookup"><span data-stu-id="e378d-127">-   RC4Stream</span></span><br /><span data-ttu-id="e378d-128">-AES</span><span class="sxs-lookup"><span data-stu-id="e378d-128">-   AES</span></span><br /><br /> <span data-ttu-id="e378d-129">默认值为 RC4Stream。</span><span class="sxs-lookup"><span data-stu-id="e378d-129">The default value is RC4Stream.</span></span> <span data-ttu-id="e378d-130">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="e378d-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="e378d-131">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="e378d-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="e378d-132">加密可以确保消息的完整性，而 EncryptAndSign 不仅可以确保消息的完整性，还可以确保消息的不可否认性，也就是说，消息确实来自发送者，并且发送者与其所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="e378d-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="e378d-133">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="e378d-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="e378d-134">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="e378d-134">-   None: No protection.</span></span><br /><span data-ttu-id="e378d-135">-Sign： 消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="e378d-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e378d-136">-EncryptAndSign： 消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="e378d-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="e378d-137">默认值为 Sign。</span><span class="sxs-lookup"><span data-stu-id="e378d-137">The default value is Sign.</span></span> <span data-ttu-id="e378d-138">此属性的类型为 ProtectionLevel。</span><span class="sxs-lookup"><span data-stu-id="e378d-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="e378d-139">-指定用于计算签名摘要算法。</span><span class="sxs-lookup"><span data-stu-id="e378d-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="e378d-140">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e378d-140">Valid values include the following:</span></span><br /><span data-ttu-id="e378d-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="e378d-141">-   MD5</span></span><br /><span data-ttu-id="e378d-142">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="e378d-142">-   SHA1</span></span><br /><span data-ttu-id="e378d-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="e378d-143">-   SHA256</span></span><br /><span data-ttu-id="e378d-144">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="e378d-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="e378d-145">默认值为 SHA1。</span><span class="sxs-lookup"><span data-stu-id="e378d-145">The default value is SHA1.</span></span> <span data-ttu-id="e378d-146">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="e378d-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e378d-147">子元素</span><span class="sxs-lookup"><span data-stu-id="e378d-147">Child Elements</span></span>  
 <span data-ttu-id="e378d-148">无</span><span class="sxs-lookup"><span data-stu-id="e378d-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e378d-149">父元素</span><span class="sxs-lookup"><span data-stu-id="e378d-149">Parent Elements</span></span>  
  
|<span data-ttu-id="e378d-150">元素</span><span class="sxs-lookup"><span data-stu-id="e378d-150">Element</span></span>|<span data-ttu-id="e378d-151">描述</span><span class="sxs-lookup"><span data-stu-id="e378d-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e378d-152">\<security></span><span class="sxs-lookup"><span data-stu-id="e378d-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="e378d-153">定义 MSMQ 绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="e378d-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e378d-154">备注</span><span class="sxs-lookup"><span data-stu-id="e378d-154">Remarks</span></span>  
 <span data-ttu-id="e378d-155">此元素包装消息队列集成传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="e378d-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="e378d-156">消息队列集成传输和排队传输的设置是相同的。</span><span class="sxs-lookup"><span data-stu-id="e378d-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="e378d-157">使用此元素可以设置身份验证模式、加密算法、安全哈希算法和保护级别。</span><span class="sxs-lookup"><span data-stu-id="e378d-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e378d-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="e378d-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="e378d-159">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="e378d-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e378d-160">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="e378d-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e378d-161">绑定</span><span class="sxs-lookup"><span data-stu-id="e378d-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e378d-162">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="e378d-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e378d-163">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="e378d-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e378d-164">\<binding></span><span class="sxs-lookup"><span data-stu-id="e378d-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
