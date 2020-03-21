---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5899c609b3cf52c4a275ba6fb10c5826fcf37f1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153004"
---
# <a name="msmqtransportsecurity"></a><span data-ttu-id="0da8e-101">\<msmq运输安全></span><span class="sxs-lookup"><span data-stu-id="0da8e-101">\<msmqTransportSecurity></span></span>
<span data-ttu-id="0da8e-102">指定自定义绑定的 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="0da8e-102">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
<span data-ttu-id="0da8e-103">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0da8e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0da8e-104">&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0da8e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0da8e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<绑定>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0da8e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0da8e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<自定义绑定>**](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="0da8e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="0da8e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绑定>**</span><span class="sxs-lookup"><span data-stu-id="0da8e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0da8e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmq集成>**](msmqintegration.md)</span><span class="sxs-lookup"><span data-stu-id="0da8e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)</span></span>\
<span data-ttu-id="0da8e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmq传输安全>**</span><span class="sxs-lookup"><span data-stu-id="0da8e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da8e-110">语法</span><span class="sxs-lookup"><span data-stu-id="0da8e-110">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0da8e-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0da8e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0da8e-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0da8e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0da8e-113">属性</span><span class="sxs-lookup"><span data-stu-id="0da8e-113">Attributes</span></span>  
  
|<span data-ttu-id="0da8e-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="0da8e-114">Attribute</span></span>|<span data-ttu-id="0da8e-115">说明</span><span class="sxs-lookup"><span data-stu-id="0da8e-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="0da8e-116">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0da8e-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="0da8e-117">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="0da8e-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="0da8e-118">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="0da8e-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0da8e-119">- 无：无身份验证。</span><span class="sxs-lookup"><span data-stu-id="0da8e-119">-   None: No authentication.</span></span><br /><span data-ttu-id="0da8e-120">- Windows：身份验证机制使用 Active Directory 获取与消息关联的 SID 的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="0da8e-120">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="0da8e-121">然后使用它来检查队列的 ACL 以确保用户有权写入队列。</span><span class="sxs-lookup"><span data-stu-id="0da8e-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="0da8e-122">- 证书：通道从证书存储获取证书。</span><span class="sxs-lookup"><span data-stu-id="0da8e-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="0da8e-123">默认值为 Windows。</span><span class="sxs-lookup"><span data-stu-id="0da8e-123">The default value is Windows.</span></span> <span data-ttu-id="0da8e-124">此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。</span><span class="sxs-lookup"><span data-stu-id="0da8e-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="0da8e-125">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="0da8e-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="0da8e-126">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="0da8e-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0da8e-127">- RC4流</span><span class="sxs-lookup"><span data-stu-id="0da8e-127">-   RC4Stream</span></span><br /><span data-ttu-id="0da8e-128">- AES</span><span class="sxs-lookup"><span data-stu-id="0da8e-128">-   AES</span></span><br /><br /> <span data-ttu-id="0da8e-129">默认值为 RC4Stream。</span><span class="sxs-lookup"><span data-stu-id="0da8e-129">The default value is RC4Stream.</span></span> <span data-ttu-id="0da8e-130">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="0da8e-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="0da8e-131">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="0da8e-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="0da8e-132">加密可确保邮件完整性，而加密和签名可确保邮件的完整性和非否认性;也就是说，邮件确实来自发件人，发件人是他们说的。</span><span class="sxs-lookup"><span data-stu-id="0da8e-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="0da8e-133">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="0da8e-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0da8e-134">-无：没有保护</span><span class="sxs-lookup"><span data-stu-id="0da8e-134">-   None: No protection.</span></span><br /><span data-ttu-id="0da8e-135">- 签名：消息已签名。</span><span class="sxs-lookup"><span data-stu-id="0da8e-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="0da8e-136">- 加密和签名：邮件经过加密并签名。</span><span class="sxs-lookup"><span data-stu-id="0da8e-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="0da8e-137">默认值为 Sign。</span><span class="sxs-lookup"><span data-stu-id="0da8e-137">The default value is Sign.</span></span> <span data-ttu-id="0da8e-138">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="0da8e-138">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="0da8e-139">指定用于计算签名中的摘要的算法。</span><span class="sxs-lookup"><span data-stu-id="0da8e-139">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="0da8e-140">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="0da8e-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0da8e-141">- MD5</span><span class="sxs-lookup"><span data-stu-id="0da8e-141">-   MD5</span></span><br /><span data-ttu-id="0da8e-142">- SHA1</span><span class="sxs-lookup"><span data-stu-id="0da8e-142">-   SHA1</span></span><br /><span data-ttu-id="0da8e-143">- SHA256</span><span class="sxs-lookup"><span data-stu-id="0da8e-143">-   SHA256</span></span><br /><span data-ttu-id="0da8e-144">- SHA512</span><span class="sxs-lookup"><span data-stu-id="0da8e-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="0da8e-145">默认值为 SHA1。</span><span class="sxs-lookup"><span data-stu-id="0da8e-145">The default value is SHA1.</span></span> <span data-ttu-id="0da8e-146">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="0da8e-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="0da8e-147">由于与 MD5 和 SHA1 的碰撞问题，Microsoft 推荐 SHA256 或更高。</span><span class="sxs-lookup"><span data-stu-id="0da8e-147">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0da8e-148">子元素</span><span class="sxs-lookup"><span data-stu-id="0da8e-148">Child Elements</span></span>  
 <span data-ttu-id="0da8e-149">无。</span><span class="sxs-lookup"><span data-stu-id="0da8e-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0da8e-150">父元素</span><span class="sxs-lookup"><span data-stu-id="0da8e-150">Parent Elements</span></span>  
  
|<span data-ttu-id="0da8e-151">元素</span><span class="sxs-lookup"><span data-stu-id="0da8e-151">Element</span></span>|<span data-ttu-id="0da8e-152">说明</span><span class="sxs-lookup"><span data-stu-id="0da8e-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0da8e-153">\<msmq集成></span><span class="sxs-lookup"><span data-stu-id="0da8e-153">\<msmqIntegration></span></span>](msmqintegration.md)|<span data-ttu-id="0da8e-154">指定与消息队列 (MSMQ) 发送方或接收方进行交互所需的设置。</span><span class="sxs-lookup"><span data-stu-id="0da8e-154">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="0da8e-155">\<msmq 传输></span><span class="sxs-lookup"><span data-stu-id="0da8e-155">\<msmqTransport></span></span>](msmqtransport.md)|<span data-ttu-id="0da8e-156">指定使用本机 MSMQ 协议的 Windows Communication Foundation (WCF) 服务的队列通信属性。</span><span class="sxs-lookup"><span data-stu-id="0da8e-156">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0da8e-157">备注</span><span class="sxs-lookup"><span data-stu-id="0da8e-157">Remarks</span></span>  
 <span data-ttu-id="0da8e-158">有关运输安全的详细信息，请参阅[运输安全](../../../wcf/feature-details/transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="0da8e-158">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da8e-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0da8e-159">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0da8e-160">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="0da8e-160">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="0da8e-161">传输</span><span class="sxs-lookup"><span data-stu-id="0da8e-161">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="0da8e-162">选择传输</span><span class="sxs-lookup"><span data-stu-id="0da8e-162">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="0da8e-163">绑定</span><span class="sxs-lookup"><span data-stu-id="0da8e-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0da8e-164">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0da8e-164">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0da8e-165">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0da8e-165">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0da8e-166">\<自定义绑定></span><span class="sxs-lookup"><span data-stu-id="0da8e-166">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="0da8e-167">运输安全</span><span class="sxs-lookup"><span data-stu-id="0da8e-167">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
