---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: fece74e76f879eff51f154eab8c8edea2c27119e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180123"
---
# <a name="msmqtransportsecurity"></a><span data-ttu-id="96557-101">\<msmqTransportSecurity></span><span class="sxs-lookup"><span data-stu-id="96557-101">\<msmqTransportSecurity></span></span>
<span data-ttu-id="96557-102">指定自定义绑定的 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="96557-102">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
 <span data-ttu-id="96557-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="96557-103">\<system.serviceModel></span></span>  
<span data-ttu-id="96557-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="96557-104">\<bindings></span></span>  
<span data-ttu-id="96557-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="96557-105">\<customBinding></span></span>  
<span data-ttu-id="96557-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="96557-106">\<binding></span></span>  
<span data-ttu-id="96557-107">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="96557-107">\<msmqIntegration></span></span>  
<span data-ttu-id="96557-108">\<msmqTransportSecurity></span><span class="sxs-lookup"><span data-stu-id="96557-108">\<msmqTransportSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96557-109">语法</span><span class="sxs-lookup"><span data-stu-id="96557-109">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96557-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="96557-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96557-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="96557-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96557-112">特性</span><span class="sxs-lookup"><span data-stu-id="96557-112">Attributes</span></span>  
  
|<span data-ttu-id="96557-113">特性</span><span class="sxs-lookup"><span data-stu-id="96557-113">Attribute</span></span>|<span data-ttu-id="96557-114">描述</span><span class="sxs-lookup"><span data-stu-id="96557-114">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="96557-115">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="96557-115">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="96557-116">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="96557-116">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="96557-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="96557-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="96557-118">-None:无身份验证。</span><span class="sxs-lookup"><span data-stu-id="96557-118">-   None: No authentication.</span></span><br /><span data-ttu-id="96557-119">-Windows:身份验证机制使用 Active Directory 获取与消息关联的 SID 的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="96557-119">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="96557-120">然后使用它来检查队列的 ACL 以确保用户有权写入队列。</span><span class="sxs-lookup"><span data-stu-id="96557-120">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="96557-121">-证书：通道从证书存储获取的证书。</span><span class="sxs-lookup"><span data-stu-id="96557-121">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="96557-122">默认值为 Windows。</span><span class="sxs-lookup"><span data-stu-id="96557-122">The default value is Windows.</span></span> <span data-ttu-id="96557-123">此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。</span><span class="sxs-lookup"><span data-stu-id="96557-123">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="96557-124">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="96557-124">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="96557-125">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="96557-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="96557-126">-   RC4Stream</span><span class="sxs-lookup"><span data-stu-id="96557-126">-   RC4Stream</span></span><br /><span data-ttu-id="96557-127">-   AES</span><span class="sxs-lookup"><span data-stu-id="96557-127">-   AES</span></span><br /><br /> <span data-ttu-id="96557-128">默认值为 RC4Stream。</span><span class="sxs-lookup"><span data-stu-id="96557-128">The default value is RC4Stream.</span></span> <span data-ttu-id="96557-129">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="96557-129">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="96557-130">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="96557-130">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="96557-131">加密可以确保消息的完整性，而 EncryptAndSign 不仅可以确保消息的完整性，还可以确保消息的不可否认性，也就是说，消息确实来自发送者，并且发送者与其所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="96557-131">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="96557-132">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="96557-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="96557-133">-None:无保护。</span><span class="sxs-lookup"><span data-stu-id="96557-133">-   None: No protection.</span></span><br /><span data-ttu-id="96557-134">登录：对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="96557-134">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="96557-135">-EncryptAndSign:对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="96557-135">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="96557-136">默认值为 Sign。</span><span class="sxs-lookup"><span data-stu-id="96557-136">The default value is Sign.</span></span> <span data-ttu-id="96557-137">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="96557-137">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="96557-138">指定用于计算签名中的摘要的算法。</span><span class="sxs-lookup"><span data-stu-id="96557-138">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="96557-139">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="96557-139">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="96557-140">-   MD5</span><span class="sxs-lookup"><span data-stu-id="96557-140">-   MD5</span></span><br /><span data-ttu-id="96557-141">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="96557-141">-   SHA1</span></span><br /><span data-ttu-id="96557-142">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="96557-142">-   SHA256</span></span><br /><span data-ttu-id="96557-143">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="96557-143">-   SHA512</span></span><br /><br /> <span data-ttu-id="96557-144">默认值为 SHA1。</span><span class="sxs-lookup"><span data-stu-id="96557-144">The default value is SHA1.</span></span> <span data-ttu-id="96557-145">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="96557-145">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="96557-146">由于存在冲突问题 MD5 和 SHA1，Microsoft 建议 SHA256 或更好的。</span><span class="sxs-lookup"><span data-stu-id="96557-146">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96557-147">子元素</span><span class="sxs-lookup"><span data-stu-id="96557-147">Child Elements</span></span>  
 <span data-ttu-id="96557-148">无。</span><span class="sxs-lookup"><span data-stu-id="96557-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96557-149">父元素</span><span class="sxs-lookup"><span data-stu-id="96557-149">Parent Elements</span></span>  
  
|<span data-ttu-id="96557-150">元素</span><span class="sxs-lookup"><span data-stu-id="96557-150">Element</span></span>|<span data-ttu-id="96557-151">描述</span><span class="sxs-lookup"><span data-stu-id="96557-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96557-152">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="96557-152">\<msmqIntegration></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|<span data-ttu-id="96557-153">指定与消息队列 (MSMQ) 发送方或接收方进行交互所需的设置。</span><span class="sxs-lookup"><span data-stu-id="96557-153">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="96557-154">\<msmqTransport></span><span class="sxs-lookup"><span data-stu-id="96557-154">\<msmqTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|<span data-ttu-id="96557-155">指定使用本机 MSMQ 协议的 Windows Communication Foundation (WCF) 服务的队列通信属性。</span><span class="sxs-lookup"><span data-stu-id="96557-155">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96557-156">备注</span><span class="sxs-lookup"><span data-stu-id="96557-156">Remarks</span></span>  
 <span data-ttu-id="96557-157">传输安全性的详细信息，请参阅[传输安全](../../../../../docs/framework/wcf/feature-details/transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="96557-157">For more information on transport security, see [Transport Security](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96557-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="96557-158">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="96557-159">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="96557-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="96557-160">传输</span><span class="sxs-lookup"><span data-stu-id="96557-160">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="96557-161">选择传输方式</span><span class="sxs-lookup"><span data-stu-id="96557-161">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="96557-162">绑定</span><span class="sxs-lookup"><span data-stu-id="96557-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="96557-163">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="96557-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="96557-164">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="96557-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="96557-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="96557-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="96557-166">传输安全</span><span class="sxs-lookup"><span data-stu-id="96557-166">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
