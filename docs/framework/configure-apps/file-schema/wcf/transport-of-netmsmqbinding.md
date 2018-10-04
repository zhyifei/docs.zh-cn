---
title: '&lt;netMsmqBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 06114990f931eb06d064fcec425e9ab42507c932
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582302"
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="d6447-102">&lt;netMsmqBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="d6447-102">&lt;transport&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="d6447-103">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="d6447-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="d6447-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6447-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6447-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d6447-105">\<bindings></span></span>  
<span data-ttu-id="d6447-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="d6447-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="d6447-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d6447-107">\<binding></span></span>  
<span data-ttu-id="d6447-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="d6447-108">\<security></span></span>  
<span data-ttu-id="d6447-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="d6447-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6447-110">语法</span><span class="sxs-lookup"><span data-stu-id="d6447-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6447-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d6447-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d6447-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d6447-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6447-113">特性</span><span class="sxs-lookup"><span data-stu-id="d6447-113">Attributes</span></span>  
  
|<span data-ttu-id="d6447-114">特性</span><span class="sxs-lookup"><span data-stu-id="d6447-114">Attribute</span></span>|<span data-ttu-id="d6447-115">描述</span><span class="sxs-lookup"><span data-stu-id="d6447-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6447-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="d6447-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="d6447-117">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d6447-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="d6447-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="d6447-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d6447-119">-None： 无身份验证。</span><span class="sxs-lookup"><span data-stu-id="d6447-119">-   None: No authentication.</span></span><br /><span data-ttu-id="d6447-120">-WindowsDomain： 身份验证机制使用 Active Directory 检索与消息关联的安全标识符的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="d6447-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="d6447-121">然后使用它来检查队列的 ACL 以确保用户具有队列写权限。</span><span class="sxs-lookup"><span data-stu-id="d6447-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="d6447-122">-证书： 通道从证书存储检索证书。</span><span class="sxs-lookup"><span data-stu-id="d6447-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="d6447-123">默认值为 `WindowsDomain`。</span><span class="sxs-lookup"><span data-stu-id="d6447-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="d6447-124">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="d6447-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="d6447-125">此特性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode></span><span class="sxs-lookup"><span data-stu-id="d6447-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="d6447-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="d6447-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="d6447-127">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="d6447-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="d6447-128">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="d6447-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d6447-129">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="d6447-129">-   RC4Stream</span></span><br /><span data-ttu-id="d6447-130">-AES</span><span class="sxs-lookup"><span data-stu-id="d6447-130">-   AES</span></span><br /><span data-ttu-id="d6447-131">-默认值是`RC4Stream`。</span><span class="sxs-lookup"><span data-stu-id="d6447-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="d6447-132">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="d6447-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="d6447-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="d6447-133">msmqProtectionLevel</span></span>|<span data-ttu-id="d6447-134">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="d6447-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="d6447-135">加密可确保消息的完整性，而签名和加密不仅可以确保消息的完整性，还可以确保消息的不可否认性。</span><span class="sxs-lookup"><span data-stu-id="d6447-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="d6447-136">也就是说，消息确实来自发送者，发送者与他所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="d6447-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="d6447-137">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="d6447-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d6447-138">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="d6447-138">-   None: No protection.</span></span><br /><span data-ttu-id="d6447-139">登录： 对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="d6447-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="d6447-140">-EncryptAndSign： 消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="d6447-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="d6447-141">-默认值是`Sign`。</span><span class="sxs-lookup"><span data-stu-id="d6447-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="d6447-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="d6447-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="d6447-143">指定用于计算消息摘要的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="d6447-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="d6447-144">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="d6447-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d6447-145">-   MD5</span><span class="sxs-lookup"><span data-stu-id="d6447-145">-   MD5</span></span><br /><span data-ttu-id="d6447-146">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="d6447-146">-   SHA1</span></span><br /><span data-ttu-id="d6447-147">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="d6447-147">-   SHA256</span></span><br /><span data-ttu-id="d6447-148">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="d6447-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="d6447-149">默认值为 `SHA1`。</span><span class="sxs-lookup"><span data-stu-id="d6447-149">The default is `SHA1`.</span></span> <span data-ttu-id="d6447-150">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="d6447-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6447-151">子元素</span><span class="sxs-lookup"><span data-stu-id="d6447-151">Child Elements</span></span>  
 <span data-ttu-id="d6447-152">无</span><span class="sxs-lookup"><span data-stu-id="d6447-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6447-153">父元素</span><span class="sxs-lookup"><span data-stu-id="d6447-153">Parent Elements</span></span>  
  
|<span data-ttu-id="d6447-154">元素</span><span class="sxs-lookup"><span data-stu-id="d6447-154">Element</span></span>|<span data-ttu-id="d6447-155">描述</span><span class="sxs-lookup"><span data-stu-id="d6447-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6447-156">\<security></span><span class="sxs-lookup"><span data-stu-id="d6447-156">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="d6447-157">定义排队传输的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="d6447-157">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6447-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6447-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="d6447-159">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="d6447-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="d6447-160">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="d6447-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="d6447-161">绑定</span><span class="sxs-lookup"><span data-stu-id="d6447-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d6447-162">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="d6447-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d6447-163">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="d6447-163">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="d6447-164">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d6447-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
