---
title: '&lt;netMsmqBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 1b0de5e1d581384d00c18dbefbf7b170325e2061
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44174174"
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="e5339-102">&lt;netMsmqBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="e5339-102">&lt;transport&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="e5339-103">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="e5339-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="e5339-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e5339-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5339-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e5339-105">\<bindings></span></span>  
<span data-ttu-id="e5339-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="e5339-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="e5339-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e5339-107">\<binding></span></span>  
<span data-ttu-id="e5339-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="e5339-108">\<security></span></span>  
<span data-ttu-id="e5339-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="e5339-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5339-110">语法</span><span class="sxs-lookup"><span data-stu-id="e5339-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>  
    <binding>  
    <security>  
         <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
    </security>  
   </binding>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5339-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e5339-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5339-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e5339-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5339-113">特性</span><span class="sxs-lookup"><span data-stu-id="e5339-113">Attributes</span></span>  
  
|<span data-ttu-id="e5339-114">特性</span><span class="sxs-lookup"><span data-stu-id="e5339-114">Attribute</span></span>|<span data-ttu-id="e5339-115">描述</span><span class="sxs-lookup"><span data-stu-id="e5339-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5339-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="e5339-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="e5339-117">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e5339-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="e5339-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e5339-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e5339-119">-None： 无身份验证。</span><span class="sxs-lookup"><span data-stu-id="e5339-119">-   None: No authentication.</span></span><br /><span data-ttu-id="e5339-120">-WindowsDomain： 身份验证机制使用 Active Directory 检索与消息关联的安全标识符的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e5339-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="e5339-121">然后使用它来检查队列的 ACL 以确保用户具有队列写权限。</span><span class="sxs-lookup"><span data-stu-id="e5339-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="e5339-122">-证书： 通道从证书存储检索证书。</span><span class="sxs-lookup"><span data-stu-id="e5339-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="e5339-123">默认值为 `WindowsDomain`。</span><span class="sxs-lookup"><span data-stu-id="e5339-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="e5339-124">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="e5339-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="e5339-125">此特性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode></span><span class="sxs-lookup"><span data-stu-id="e5339-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="e5339-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="e5339-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="e5339-127">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="e5339-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="e5339-128">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e5339-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e5339-129">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="e5339-129">-   RC4Stream</span></span><br /><span data-ttu-id="e5339-130">-AES</span><span class="sxs-lookup"><span data-stu-id="e5339-130">-   AES</span></span><br /><span data-ttu-id="e5339-131">-默认值是`RC4Stream`。</span><span class="sxs-lookup"><span data-stu-id="e5339-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="e5339-132">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="e5339-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="e5339-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="e5339-133">msmqProtectionLevel</span></span>|<span data-ttu-id="e5339-134">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="e5339-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="e5339-135">加密可确保消息的完整性，而签名和加密不仅可以确保消息的完整性，还可以确保消息的不可否认性。</span><span class="sxs-lookup"><span data-stu-id="e5339-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="e5339-136">也就是说，消息确实来自发送者，发送者与他所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="e5339-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="e5339-137">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e5339-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e5339-138">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="e5339-138">-   None: No protection.</span></span><br /><span data-ttu-id="e5339-139">登录： 对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="e5339-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e5339-140">-EncryptAndSign： 消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="e5339-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="e5339-141">-默认值是`Sign`。</span><span class="sxs-lookup"><span data-stu-id="e5339-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="e5339-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="e5339-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="e5339-143">指定用于计算消息摘要的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="e5339-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="e5339-144">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e5339-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e5339-145">-   MD5</span><span class="sxs-lookup"><span data-stu-id="e5339-145">-   MD5</span></span><br /><span data-ttu-id="e5339-146">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="e5339-146">-   SHA1</span></span><br /><span data-ttu-id="e5339-147">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="e5339-147">-   SHA256</span></span><br /><span data-ttu-id="e5339-148">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="e5339-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="e5339-149">默认值为 `SHA1`。</span><span class="sxs-lookup"><span data-stu-id="e5339-149">The default is `SHA1`.</span></span> <span data-ttu-id="e5339-150">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="e5339-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5339-151">子元素</span><span class="sxs-lookup"><span data-stu-id="e5339-151">Child Elements</span></span>  
 <span data-ttu-id="e5339-152">无</span><span class="sxs-lookup"><span data-stu-id="e5339-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5339-153">父元素</span><span class="sxs-lookup"><span data-stu-id="e5339-153">Parent Elements</span></span>  
  
|<span data-ttu-id="e5339-154">元素</span><span class="sxs-lookup"><span data-stu-id="e5339-154">Element</span></span>|<span data-ttu-id="e5339-155">描述</span><span class="sxs-lookup"><span data-stu-id="e5339-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5339-156">\<security></span><span class="sxs-lookup"><span data-stu-id="e5339-156">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="e5339-157">定义排队传输的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="e5339-157">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5339-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5339-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="e5339-159">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="e5339-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="e5339-160">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="e5339-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e5339-161">绑定</span><span class="sxs-lookup"><span data-stu-id="e5339-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e5339-162">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="e5339-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e5339-163">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="e5339-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e5339-164">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e5339-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
