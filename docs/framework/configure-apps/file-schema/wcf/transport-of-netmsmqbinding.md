---
title: <transport> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 0df17832818e6e4e7c8e551fabaf4f5241807a74
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735997"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="de6ae-102">\<netMsmqBinding 的 \<传输 > ></span><span class="sxs-lookup"><span data-stu-id="de6ae-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="de6ae-103">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="de6ae-103">Defines the transport security settings.</span></span>  
  
<span data-ttu-id="de6ae-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="de6ae-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="de6ae-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="de6ae-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="de6ae-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="de6ae-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="de6ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="de6ae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="de6ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="de6ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="de6ae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-netmsmqbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="de6ae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="de6ae-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="de6ae-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de6ae-111">语法</span><span class="sxs-lookup"><span data-stu-id="de6ae-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de6ae-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="de6ae-112">Attributes and Elements</span></span>  
 <span data-ttu-id="de6ae-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="de6ae-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de6ae-114">特性</span><span class="sxs-lookup"><span data-stu-id="de6ae-114">Attributes</span></span>  
  
|<span data-ttu-id="de6ae-115">特性</span><span class="sxs-lookup"><span data-stu-id="de6ae-115">Attribute</span></span>|<span data-ttu-id="de6ae-116">描述</span><span class="sxs-lookup"><span data-stu-id="de6ae-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de6ae-117">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="de6ae-117">msmqAuthenticationMode</span></span>|<span data-ttu-id="de6ae-118">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="de6ae-118">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="de6ae-119">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="de6ae-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="de6ae-120">-None：无身份验证。</span><span class="sxs-lookup"><span data-stu-id="de6ae-120">-   None: No authentication.</span></span><br /><span data-ttu-id="de6ae-121">-WindowsDomain：身份验证机制使用 Active Directory 检索与消息关联的安全标识符的 x.509 证书。</span><span class="sxs-lookup"><span data-stu-id="de6ae-121">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="de6ae-122">然后使用它来检查队列的 ACL 以确保用户具有队列写权限。</span><span class="sxs-lookup"><span data-stu-id="de6ae-122">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="de6ae-123">-Certificate：通道从证书存储中检索证书。</span><span class="sxs-lookup"><span data-stu-id="de6ae-123">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="de6ae-124">默认值为 `WindowsDomain`。</span><span class="sxs-lookup"><span data-stu-id="de6ae-124">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="de6ae-125">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="de6ae-125">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="de6ae-126">此特性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode></span><span class="sxs-lookup"><span data-stu-id="de6ae-126">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="de6ae-127">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="de6ae-127">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="de6ae-128">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="de6ae-128">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="de6ae-129">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="de6ae-129">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="de6ae-130">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="de6ae-130">-   RC4Stream</span></span><br /><span data-ttu-id="de6ae-131">-AES</span><span class="sxs-lookup"><span data-stu-id="de6ae-131">-   AES</span></span><br /><span data-ttu-id="de6ae-132">-默认值为 `RC4Stream`。</span><span class="sxs-lookup"><span data-stu-id="de6ae-132">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="de6ae-133">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="de6ae-133">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="de6ae-134">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="de6ae-134">msmqProtectionLevel</span></span>|<span data-ttu-id="de6ae-135">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="de6ae-135">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="de6ae-136">加密可确保消息的完整性，而签名和加密不仅可以确保消息的完整性，还可以确保消息的不可否认性。</span><span class="sxs-lookup"><span data-stu-id="de6ae-136">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="de6ae-137">也就是说，消息确实来自发送者，发送者与他所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="de6ae-137">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="de6ae-138">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="de6ae-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="de6ae-139">-None：无保护。</span><span class="sxs-lookup"><span data-stu-id="de6ae-139">-   None: No protection.</span></span><br /><span data-ttu-id="de6ae-140">-Sign：对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="de6ae-140">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="de6ae-141">-EncryptAndSign：对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="de6ae-141">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="de6ae-142">-默认值为 `Sign`。</span><span class="sxs-lookup"><span data-stu-id="de6ae-142">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="de6ae-143">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="de6ae-143">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="de6ae-144">指定用于计算消息摘要的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="de6ae-144">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="de6ae-145">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="de6ae-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="de6ae-146">-MD5</span><span class="sxs-lookup"><span data-stu-id="de6ae-146">-   MD5</span></span><br /><span data-ttu-id="de6ae-147">-SHA1</span><span class="sxs-lookup"><span data-stu-id="de6ae-147">-   SHA1</span></span><br /><span data-ttu-id="de6ae-148">-SHA256</span><span class="sxs-lookup"><span data-stu-id="de6ae-148">-   SHA256</span></span><br /><span data-ttu-id="de6ae-149">-SHA512</span><span class="sxs-lookup"><span data-stu-id="de6ae-149">-   SHA512</span></span><br /><br /> <span data-ttu-id="de6ae-150">默认值为 `SHA1`。</span><span class="sxs-lookup"><span data-stu-id="de6ae-150">The default is `SHA1`.</span></span> <span data-ttu-id="de6ae-151">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="de6ae-151">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="de6ae-152">由于 MD5 和 SHA1 出现冲突，Microsoft 建议 SHA256 或更好。</span><span class="sxs-lookup"><span data-stu-id="de6ae-152">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de6ae-153">子元素</span><span class="sxs-lookup"><span data-stu-id="de6ae-153">Child Elements</span></span>  
 <span data-ttu-id="de6ae-154">None</span><span class="sxs-lookup"><span data-stu-id="de6ae-154">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de6ae-155">父元素</span><span class="sxs-lookup"><span data-stu-id="de6ae-155">Parent Elements</span></span>  
  
|<span data-ttu-id="de6ae-156">元素</span><span class="sxs-lookup"><span data-stu-id="de6ae-156">Element</span></span>|<span data-ttu-id="de6ae-157">描述</span><span class="sxs-lookup"><span data-stu-id="de6ae-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de6ae-158">\<security ></span><span class="sxs-lookup"><span data-stu-id="de6ae-158">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="de6ae-159">定义排队传输的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="de6ae-159">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de6ae-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="de6ae-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="de6ae-161">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="de6ae-161">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="de6ae-162">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="de6ae-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="de6ae-163">绑定</span><span class="sxs-lookup"><span data-stu-id="de6ae-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="de6ae-164">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="de6ae-164">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="de6ae-165">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="de6ae-165">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="de6ae-166">\<binding ></span><span class="sxs-lookup"><span data-stu-id="de6ae-166">\<binding></span></span>](bindings.md)
