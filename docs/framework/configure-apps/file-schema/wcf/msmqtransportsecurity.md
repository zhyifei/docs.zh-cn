---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5a7dcac4edce75029bb2e0293461557f56e3c3be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933224"
---
# <a name="msmqtransportsecurity"></a><span data-ttu-id="826eb-101">\<msmqTransportSecurity></span><span class="sxs-lookup"><span data-stu-id="826eb-101">\<msmqTransportSecurity></span></span>
<span data-ttu-id="826eb-102">指定自定义绑定的 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="826eb-102">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
 <span data-ttu-id="826eb-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="826eb-103">\<system.serviceModel></span></span>  
<span data-ttu-id="826eb-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="826eb-104">\<bindings></span></span>  
<span data-ttu-id="826eb-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="826eb-105">\<customBinding></span></span>  
<span data-ttu-id="826eb-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="826eb-106">\<binding></span></span>  
<span data-ttu-id="826eb-107">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="826eb-107">\<msmqIntegration></span></span>  
<span data-ttu-id="826eb-108">\<msmqTransportSecurity></span><span class="sxs-lookup"><span data-stu-id="826eb-108">\<msmqTransportSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="826eb-109">语法</span><span class="sxs-lookup"><span data-stu-id="826eb-109">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="826eb-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="826eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="826eb-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="826eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="826eb-112">特性</span><span class="sxs-lookup"><span data-stu-id="826eb-112">Attributes</span></span>  
  
|<span data-ttu-id="826eb-113">特性</span><span class="sxs-lookup"><span data-stu-id="826eb-113">Attribute</span></span>|<span data-ttu-id="826eb-114">描述</span><span class="sxs-lookup"><span data-stu-id="826eb-114">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="826eb-115">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="826eb-115">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="826eb-116">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="826eb-116">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="826eb-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="826eb-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="826eb-118">内容无身份验证。</span><span class="sxs-lookup"><span data-stu-id="826eb-118">-   None: No authentication.</span></span><br /><span data-ttu-id="826eb-119">Windows身份验证机制使用 Active Directory 获取与消息关联的 SID 的 x.509 证书。</span><span class="sxs-lookup"><span data-stu-id="826eb-119">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="826eb-120">然后使用它来检查队列的 ACL 以确保用户有权写入队列。</span><span class="sxs-lookup"><span data-stu-id="826eb-120">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="826eb-121">证书通道从证书存储区获取证书。</span><span class="sxs-lookup"><span data-stu-id="826eb-121">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="826eb-122">默认值为 Windows。</span><span class="sxs-lookup"><span data-stu-id="826eb-122">The default value is Windows.</span></span> <span data-ttu-id="826eb-123">此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。</span><span class="sxs-lookup"><span data-stu-id="826eb-123">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="826eb-124">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="826eb-124">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="826eb-125">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="826eb-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="826eb-126">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="826eb-126">-   RC4Stream</span></span><br /><span data-ttu-id="826eb-127">-   AES</span><span class="sxs-lookup"><span data-stu-id="826eb-127">-   AES</span></span><br /><br /> <span data-ttu-id="826eb-128">默认值为 RC4Stream。</span><span class="sxs-lookup"><span data-stu-id="826eb-128">The default value is RC4Stream.</span></span> <span data-ttu-id="826eb-129">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="826eb-129">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="826eb-130">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="826eb-130">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="826eb-131">加密可以确保消息的完整性，而 EncryptAndSign 不仅可以确保消息的完整性，还可以确保消息的不可否认性，也就是说，消息确实来自发送者，并且发送者与其所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="826eb-131">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="826eb-132">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="826eb-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="826eb-133">内容无保护。</span><span class="sxs-lookup"><span data-stu-id="826eb-133">-   None: No protection.</span></span><br /><span data-ttu-id="826eb-134">表明对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="826eb-134">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="826eb-135">EncryptAndSign对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="826eb-135">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="826eb-136">默认值为 Sign。</span><span class="sxs-lookup"><span data-stu-id="826eb-136">The default value is Sign.</span></span> <span data-ttu-id="826eb-137">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="826eb-137">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="826eb-138">指定用于计算签名中的摘要的算法。</span><span class="sxs-lookup"><span data-stu-id="826eb-138">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="826eb-139">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="826eb-139">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="826eb-140">-   MD5</span><span class="sxs-lookup"><span data-stu-id="826eb-140">-   MD5</span></span><br /><span data-ttu-id="826eb-141">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="826eb-141">-   SHA1</span></span><br /><span data-ttu-id="826eb-142">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="826eb-142">-   SHA256</span></span><br /><span data-ttu-id="826eb-143">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="826eb-143">-   SHA512</span></span><br /><br /> <span data-ttu-id="826eb-144">默认值为 SHA1。</span><span class="sxs-lookup"><span data-stu-id="826eb-144">The default value is SHA1.</span></span> <span data-ttu-id="826eb-145">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="826eb-145">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="826eb-146">由于 MD5 和 SHA1 出现冲突, Microsoft 建议 SHA256 或更好。</span><span class="sxs-lookup"><span data-stu-id="826eb-146">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="826eb-147">子元素</span><span class="sxs-lookup"><span data-stu-id="826eb-147">Child Elements</span></span>  
 <span data-ttu-id="826eb-148">无。</span><span class="sxs-lookup"><span data-stu-id="826eb-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="826eb-149">父元素</span><span class="sxs-lookup"><span data-stu-id="826eb-149">Parent Elements</span></span>  
  
|<span data-ttu-id="826eb-150">元素</span><span class="sxs-lookup"><span data-stu-id="826eb-150">Element</span></span>|<span data-ttu-id="826eb-151">描述</span><span class="sxs-lookup"><span data-stu-id="826eb-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="826eb-152">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="826eb-152">\<msmqIntegration></span></span>](msmqintegration.md)|<span data-ttu-id="826eb-153">指定与消息队列 (MSMQ) 发送方或接收方进行交互所需的设置。</span><span class="sxs-lookup"><span data-stu-id="826eb-153">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="826eb-154">\<msmqTransport></span><span class="sxs-lookup"><span data-stu-id="826eb-154">\<msmqTransport></span></span>](msmqtransport.md)|<span data-ttu-id="826eb-155">指定使用本机 MSMQ 协议的 Windows Communication Foundation (WCF) 服务的队列通信属性。</span><span class="sxs-lookup"><span data-stu-id="826eb-155">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="826eb-156">备注</span><span class="sxs-lookup"><span data-stu-id="826eb-156">Remarks</span></span>  
 <span data-ttu-id="826eb-157">有关传输安全的详细信息, 请参阅[传输安全性](../../../wcf/feature-details/transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="826eb-157">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826eb-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="826eb-158">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="826eb-159">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="826eb-159">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="826eb-160">传输</span><span class="sxs-lookup"><span data-stu-id="826eb-160">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="826eb-161">选择传输</span><span class="sxs-lookup"><span data-stu-id="826eb-161">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="826eb-162">绑定</span><span class="sxs-lookup"><span data-stu-id="826eb-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="826eb-163">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="826eb-163">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="826eb-164">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="826eb-164">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="826eb-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="826eb-165">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="826eb-166">传输安全性</span><span class="sxs-lookup"><span data-stu-id="826eb-166">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
