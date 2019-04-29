---
title: <transport> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: ec726c4b39fedbf63a7ecc9e685a86367609fa43
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788331"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="e088b-102">\<传输 > 的\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="e088b-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="e088b-103">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="e088b-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="e088b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e088b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e088b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e088b-105">\<bindings></span></span>  
<span data-ttu-id="e088b-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="e088b-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="e088b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e088b-107">\<binding></span></span>  
<span data-ttu-id="e088b-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="e088b-108">\<security></span></span>  
<span data-ttu-id="e088b-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="e088b-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e088b-110">语法</span><span class="sxs-lookup"><span data-stu-id="e088b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e088b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e088b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e088b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e088b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e088b-113">特性</span><span class="sxs-lookup"><span data-stu-id="e088b-113">Attributes</span></span>  
  
|<span data-ttu-id="e088b-114">特性</span><span class="sxs-lookup"><span data-stu-id="e088b-114">Attribute</span></span>|<span data-ttu-id="e088b-115">描述</span><span class="sxs-lookup"><span data-stu-id="e088b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e088b-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="e088b-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="e088b-117">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e088b-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="e088b-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e088b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e088b-119">-None:无身份验证。</span><span class="sxs-lookup"><span data-stu-id="e088b-119">-   None: No authentication.</span></span><br /><span data-ttu-id="e088b-120">-   WindowsDomain:身份验证机制使用 Active Directory 检索与消息关联的安全标识符的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e088b-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="e088b-121">然后使用它来检查队列的 ACL 以确保用户具有队列写权限。</span><span class="sxs-lookup"><span data-stu-id="e088b-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="e088b-122">-证书：通道从证书存储检索证书。</span><span class="sxs-lookup"><span data-stu-id="e088b-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="e088b-123">默认值为 `WindowsDomain`。</span><span class="sxs-lookup"><span data-stu-id="e088b-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="e088b-124">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="e088b-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="e088b-125">此特性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode></span><span class="sxs-lookup"><span data-stu-id="e088b-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="e088b-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="e088b-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="e088b-127">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="e088b-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="e088b-128">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e088b-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e088b-129">-   RC4Stream</span><span class="sxs-lookup"><span data-stu-id="e088b-129">-   RC4Stream</span></span><br /><span data-ttu-id="e088b-130">-   AES</span><span class="sxs-lookup"><span data-stu-id="e088b-130">-   AES</span></span><br /><span data-ttu-id="e088b-131">-默认值是`RC4Stream`。</span><span class="sxs-lookup"><span data-stu-id="e088b-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="e088b-132">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="e088b-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="e088b-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="e088b-133">msmqProtectionLevel</span></span>|<span data-ttu-id="e088b-134">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="e088b-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="e088b-135">加密可确保消息的完整性，而签名和加密不仅可以确保消息的完整性，还可以确保消息的不可否认性。</span><span class="sxs-lookup"><span data-stu-id="e088b-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="e088b-136">也就是说，消息确实来自发送者，发送者与他所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="e088b-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="e088b-137">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e088b-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e088b-138">-None:无保护。</span><span class="sxs-lookup"><span data-stu-id="e088b-138">-   None: No protection.</span></span><br /><span data-ttu-id="e088b-139">登录：对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="e088b-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e088b-140">-EncryptAndSign:对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="e088b-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="e088b-141">-默认值是`Sign`。</span><span class="sxs-lookup"><span data-stu-id="e088b-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="e088b-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="e088b-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="e088b-143">指定用于计算消息摘要的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="e088b-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="e088b-144">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e088b-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e088b-145">-   MD5</span><span class="sxs-lookup"><span data-stu-id="e088b-145">-   MD5</span></span><br /><span data-ttu-id="e088b-146">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="e088b-146">-   SHA1</span></span><br /><span data-ttu-id="e088b-147">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="e088b-147">-   SHA256</span></span><br /><span data-ttu-id="e088b-148">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="e088b-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="e088b-149">默认值为 `SHA1`。</span><span class="sxs-lookup"><span data-stu-id="e088b-149">The default is `SHA1`.</span></span> <span data-ttu-id="e088b-150">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="e088b-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="e088b-151">由于存在冲突问题 MD5 和 SHA1，Microsoft 建议 SHA256 或更好的。</span><span class="sxs-lookup"><span data-stu-id="e088b-151">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e088b-152">子元素</span><span class="sxs-lookup"><span data-stu-id="e088b-152">Child Elements</span></span>  
 <span data-ttu-id="e088b-153">None</span><span class="sxs-lookup"><span data-stu-id="e088b-153">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e088b-154">父元素</span><span class="sxs-lookup"><span data-stu-id="e088b-154">Parent Elements</span></span>  
  
|<span data-ttu-id="e088b-155">元素</span><span class="sxs-lookup"><span data-stu-id="e088b-155">Element</span></span>|<span data-ttu-id="e088b-156">描述</span><span class="sxs-lookup"><span data-stu-id="e088b-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e088b-157">\<security></span><span class="sxs-lookup"><span data-stu-id="e088b-157">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="e088b-158">定义排队传输的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="e088b-158">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e088b-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="e088b-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="e088b-160">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="e088b-160">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="e088b-161">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="e088b-161">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e088b-162">绑定</span><span class="sxs-lookup"><span data-stu-id="e088b-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e088b-163">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="e088b-163">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e088b-164">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="e088b-164">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e088b-165">\<binding></span><span class="sxs-lookup"><span data-stu-id="e088b-165">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
