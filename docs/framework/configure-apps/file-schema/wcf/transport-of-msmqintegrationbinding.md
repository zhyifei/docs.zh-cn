---
title: <transport> 的 <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 1cb165fed9266307335482166116c4c1d62efe7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152952"
---
# <a name="transport-of-msmqintegrationbinding"></a><span data-ttu-id="1c6c4-102">\<msmq\<集成绑定>传输></span><span class="sxs-lookup"><span data-stu-id="1c6c4-102">\<transport> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="1c6c4-103">定义消息队列集成传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
<span data-ttu-id="1c6c4-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1c6c4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1c6c4-105">&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1c6c4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1c6c4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<绑定>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1c6c4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="1c6c4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmq集成绑定>**](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="1c6c4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="1c6c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绑定>**</span><span class="sxs-lookup"><span data-stu-id="1c6c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="1c6c4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全>**](security-of-msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="1c6c4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="1c6c4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<运输>**</span><span class="sxs-lookup"><span data-stu-id="1c6c4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c6c4-111">语法</span><span class="sxs-lookup"><span data-stu-id="1c6c4-111">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c6c4-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1c6c4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1c6c4-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c6c4-114">属性</span><span class="sxs-lookup"><span data-stu-id="1c6c4-114">Attributes</span></span>  
  
|<span data-ttu-id="1c6c4-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="1c6c4-115">Attribute</span></span>|<span data-ttu-id="1c6c4-116">说明</span><span class="sxs-lookup"><span data-stu-id="1c6c4-116">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="1c6c4-117">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="1c6c4-118">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-118">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="1c6c4-119">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="1c6c4-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1c6c4-120">- 无：无身份验证。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-120">-   None: No authentication.</span></span><br /><span data-ttu-id="1c6c4-121">- WindowsDomain：身份验证机制使用 Active Directory 获取与消息关联的 SID 的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-121">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="1c6c4-122">然后使用它来检查队列的 ACL 以确保用户有权写入队列。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-122">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="1c6c4-123">- 证书：通道从证书存储获取证书。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-123">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="1c6c4-124">默认值为 WindowsDomain。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-124">The default value is WindowsDomain.</span></span> <span data-ttu-id="1c6c4-125">此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="1c6c4-126">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-126">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="1c6c4-127">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="1c6c4-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1c6c4-128">- RC4流</span><span class="sxs-lookup"><span data-stu-id="1c6c4-128">-   RC4Stream</span></span><br /><span data-ttu-id="1c6c4-129">- AES</span><span class="sxs-lookup"><span data-stu-id="1c6c4-129">-   AES</span></span><br /><br /> <span data-ttu-id="1c6c4-130">默认值为 RC4Stream。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-130">The default value is RC4Stream.</span></span> <span data-ttu-id="1c6c4-131">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-131">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="1c6c4-132">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-132">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="1c6c4-133">加密可确保邮件完整性，而加密和签名可确保邮件的完整性和非否认性;也就是说，邮件确实来自发件人，发件人是他们说的。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-133">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span><br /><br /> <span data-ttu-id="1c6c4-134">- 有效值包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="1c6c4-134">-   Valid values include the following:</span></span><br /><span data-ttu-id="1c6c4-135">-无：没有保护</span><span class="sxs-lookup"><span data-stu-id="1c6c4-135">-   None: No protection.</span></span><br /><span data-ttu-id="1c6c4-136">- 签名：消息已签名。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-136">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="1c6c4-137">- 加密和签名：邮件经过加密并签名。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-137">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="1c6c4-138">默认值为 Sign。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-138">The default value is Sign.</span></span> <span data-ttu-id="1c6c4-139">此属性的类型为 ProtectionLevel。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-139">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="1c6c4-140">- 指定用于计算摘要作为签名的一部分的算法。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-140">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="1c6c4-141">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="1c6c4-141">Valid values include the following:</span></span><br /><span data-ttu-id="1c6c4-142">- MD5</span><span class="sxs-lookup"><span data-stu-id="1c6c4-142">-   MD5</span></span><br /><span data-ttu-id="1c6c4-143">- SHA1</span><span class="sxs-lookup"><span data-stu-id="1c6c4-143">-   SHA1</span></span><br /><span data-ttu-id="1c6c4-144">- SHA256</span><span class="sxs-lookup"><span data-stu-id="1c6c4-144">-   SHA256</span></span><br /><span data-ttu-id="1c6c4-145">- SHA512</span><span class="sxs-lookup"><span data-stu-id="1c6c4-145">-   SHA512</span></span><br /><br /> <span data-ttu-id="1c6c4-146">默认值为 SHA1。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-146">The default value is SHA1.</span></span> <span data-ttu-id="1c6c4-147">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-147">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="1c6c4-148">由于与 MD5 和 SHA1 的碰撞问题，Microsoft 推荐 SHA256 或更高。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-148">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c6c4-149">子元素</span><span class="sxs-lookup"><span data-stu-id="1c6c4-149">Child Elements</span></span>  
 <span data-ttu-id="1c6c4-150">无</span><span class="sxs-lookup"><span data-stu-id="1c6c4-150">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c6c4-151">父元素</span><span class="sxs-lookup"><span data-stu-id="1c6c4-151">Parent Elements</span></span>  
  
|<span data-ttu-id="1c6c4-152">元素</span><span class="sxs-lookup"><span data-stu-id="1c6c4-152">Element</span></span>|<span data-ttu-id="1c6c4-153">说明</span><span class="sxs-lookup"><span data-stu-id="1c6c4-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c6c4-154">\<安全></span><span class="sxs-lookup"><span data-stu-id="1c6c4-154">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="1c6c4-155">定义 MSMQ 绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-155">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c6c4-156">备注</span><span class="sxs-lookup"><span data-stu-id="1c6c4-156">Remarks</span></span>  
 <span data-ttu-id="1c6c4-157">此元素包装消息队列集成传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-157">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="1c6c4-158">消息队列集成传输和排队传输的设置是相同的。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-158">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="1c6c4-159">使用此元素可以设置身份验证模式、加密算法、安全哈希算法和保护级别。</span><span class="sxs-lookup"><span data-stu-id="1c6c4-159">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6c4-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c6c4-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="1c6c4-161">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="1c6c4-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1c6c4-162">绑定</span><span class="sxs-lookup"><span data-stu-id="1c6c4-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1c6c4-163">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="1c6c4-163">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1c6c4-164">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="1c6c4-164">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1c6c4-165">\<绑定></span><span class="sxs-lookup"><span data-stu-id="1c6c4-165">\<binding></span></span>](bindings.md)
