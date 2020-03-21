---
title: <transport> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152926"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="eac6e-102">\<\<网络mq绑定>的传输></span><span class="sxs-lookup"><span data-stu-id="eac6e-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="eac6e-103">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="eac6e-103">Defines the transport security settings.</span></span>  
  
<span data-ttu-id="eac6e-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eac6e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eac6e-105">&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="eac6e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="eac6e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<绑定>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="eac6e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="eac6e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<净Mmq绑定>**](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="eac6e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="eac6e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绑定>**</span><span class="sxs-lookup"><span data-stu-id="eac6e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="eac6e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全>**](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="eac6e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="eac6e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<运输>**</span><span class="sxs-lookup"><span data-stu-id="eac6e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eac6e-111">语法</span><span class="sxs-lookup"><span data-stu-id="eac6e-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eac6e-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="eac6e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="eac6e-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="eac6e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eac6e-114">属性</span><span class="sxs-lookup"><span data-stu-id="eac6e-114">Attributes</span></span>  
  
|<span data-ttu-id="eac6e-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="eac6e-115">Attribute</span></span>|<span data-ttu-id="eac6e-116">说明</span><span class="sxs-lookup"><span data-stu-id="eac6e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eac6e-117">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="eac6e-117">msmqAuthenticationMode</span></span>|<span data-ttu-id="eac6e-118">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="eac6e-118">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="eac6e-119">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="eac6e-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="eac6e-120">- 无：无身份验证。</span><span class="sxs-lookup"><span data-stu-id="eac6e-120">-   None: No authentication.</span></span><br /><span data-ttu-id="eac6e-121">- WindowsDomain：身份验证机制使用 Active Directory 检索与消息关联的安全标识符的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="eac6e-121">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="eac6e-122">然后使用它来检查队列的 ACL 以确保用户具有队列写权限。</span><span class="sxs-lookup"><span data-stu-id="eac6e-122">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="eac6e-123">- 证书：通道从证书存储中检索证书。</span><span class="sxs-lookup"><span data-stu-id="eac6e-123">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="eac6e-124">默认为 `WindowsDomain`。</span><span class="sxs-lookup"><span data-stu-id="eac6e-124">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="eac6e-125">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="eac6e-125">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="eac6e-126">此特性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode></span><span class="sxs-lookup"><span data-stu-id="eac6e-126">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="eac6e-127">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="eac6e-127">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="eac6e-128">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="eac6e-128">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="eac6e-129">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="eac6e-129">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="eac6e-130">- RC4流</span><span class="sxs-lookup"><span data-stu-id="eac6e-130">-   RC4Stream</span></span><br /><span data-ttu-id="eac6e-131">- AES</span><span class="sxs-lookup"><span data-stu-id="eac6e-131">-   AES</span></span><br /><span data-ttu-id="eac6e-132">- 默认值为`RC4Stream`。</span><span class="sxs-lookup"><span data-stu-id="eac6e-132">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="eac6e-133">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="eac6e-133">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="eac6e-134">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="eac6e-134">msmqProtectionLevel</span></span>|<span data-ttu-id="eac6e-135">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="eac6e-135">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="eac6e-136">加密可确保消息的完整性，而签名和加密不仅可以确保消息的完整性，还可以确保消息的不可否认性。</span><span class="sxs-lookup"><span data-stu-id="eac6e-136">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="eac6e-137">也就是说，邮件确实来自发件人，发件人就是他们所说的发件人。</span><span class="sxs-lookup"><span data-stu-id="eac6e-137">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="eac6e-138">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="eac6e-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="eac6e-139">-无：没有保护</span><span class="sxs-lookup"><span data-stu-id="eac6e-139">-   None: No protection.</span></span><br /><span data-ttu-id="eac6e-140">- 签名：消息已签名。</span><span class="sxs-lookup"><span data-stu-id="eac6e-140">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="eac6e-141">- 加密和签名：邮件经过加密并签名。</span><span class="sxs-lookup"><span data-stu-id="eac6e-141">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="eac6e-142">- 默认值为`Sign`。</span><span class="sxs-lookup"><span data-stu-id="eac6e-142">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="eac6e-143">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="eac6e-143">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="eac6e-144">指定用于计算消息摘要的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="eac6e-144">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="eac6e-145">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="eac6e-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="eac6e-146">- MD5</span><span class="sxs-lookup"><span data-stu-id="eac6e-146">-   MD5</span></span><br /><span data-ttu-id="eac6e-147">- SHA1</span><span class="sxs-lookup"><span data-stu-id="eac6e-147">-   SHA1</span></span><br /><span data-ttu-id="eac6e-148">- SHA256</span><span class="sxs-lookup"><span data-stu-id="eac6e-148">-   SHA256</span></span><br /><span data-ttu-id="eac6e-149">- SHA512</span><span class="sxs-lookup"><span data-stu-id="eac6e-149">-   SHA512</span></span><br /><br /> <span data-ttu-id="eac6e-150">默认为 `SHA1`。</span><span class="sxs-lookup"><span data-stu-id="eac6e-150">The default is `SHA1`.</span></span> <span data-ttu-id="eac6e-151">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="eac6e-151">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="eac6e-152">由于与 MD5 和 SHA1 的碰撞问题，Microsoft 推荐 SHA256 或更高。</span><span class="sxs-lookup"><span data-stu-id="eac6e-152">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eac6e-153">子元素</span><span class="sxs-lookup"><span data-stu-id="eac6e-153">Child Elements</span></span>  
 <span data-ttu-id="eac6e-154">无</span><span class="sxs-lookup"><span data-stu-id="eac6e-154">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eac6e-155">父元素</span><span class="sxs-lookup"><span data-stu-id="eac6e-155">Parent Elements</span></span>  
  
|<span data-ttu-id="eac6e-156">元素</span><span class="sxs-lookup"><span data-stu-id="eac6e-156">Element</span></span>|<span data-ttu-id="eac6e-157">说明</span><span class="sxs-lookup"><span data-stu-id="eac6e-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eac6e-158">\<安全></span><span class="sxs-lookup"><span data-stu-id="eac6e-158">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="eac6e-159">定义排队传输的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="eac6e-159">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eac6e-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eac6e-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="eac6e-161">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="eac6e-161">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="eac6e-162">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="eac6e-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="eac6e-163">绑定</span><span class="sxs-lookup"><span data-stu-id="eac6e-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eac6e-164">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="eac6e-164">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="eac6e-165">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="eac6e-165">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="eac6e-166">\<绑定></span><span class="sxs-lookup"><span data-stu-id="eac6e-166">\<binding></span></span>](bindings.md)
