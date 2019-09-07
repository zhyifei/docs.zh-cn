---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: dc7371d694925d3ac5aa49d7d1269df323358f90
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397814"
---
# <a name="msmqtransportsecurity"></a><span data-ttu-id="c018b-101">\<msmqTransportSecurity></span><span class="sxs-lookup"><span data-stu-id="c018b-101">\<msmqTransportSecurity></span></span>
<span data-ttu-id="c018b-102">指定自定义绑定的 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="c018b-102">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
<span data-ttu-id="c018b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c018b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c018b-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c018b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c018b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c018b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c018b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c018b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c018b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="c018b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c018b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<msmqIntegration >** ](msmqintegration.md)</span><span class="sxs-lookup"><span data-stu-id="c018b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)</span></span>\
<span data-ttu-id="c018b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Msmqtransportsecurity.msmqprotectionlevel >**</span><span class="sxs-lookup"><span data-stu-id="c018b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c018b-110">语法</span><span class="sxs-lookup"><span data-stu-id="c018b-110">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c018b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c018b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c018b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c018b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c018b-113">特性</span><span class="sxs-lookup"><span data-stu-id="c018b-113">Attributes</span></span>  
  
|<span data-ttu-id="c018b-114">特性</span><span class="sxs-lookup"><span data-stu-id="c018b-114">Attribute</span></span>|<span data-ttu-id="c018b-115">描述</span><span class="sxs-lookup"><span data-stu-id="c018b-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="c018b-116">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c018b-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="c018b-117">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="c018b-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="c018b-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c018b-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c018b-119">内容无身份验证。</span><span class="sxs-lookup"><span data-stu-id="c018b-119">-   None: No authentication.</span></span><br /><span data-ttu-id="c018b-120">Windows身份验证机制使用 Active Directory 获取与消息关联的 SID 的 x.509 证书。</span><span class="sxs-lookup"><span data-stu-id="c018b-120">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="c018b-121">然后使用它来检查队列的 ACL 以确保用户有权写入队列。</span><span class="sxs-lookup"><span data-stu-id="c018b-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="c018b-122">证书通道从证书存储区获取证书。</span><span class="sxs-lookup"><span data-stu-id="c018b-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="c018b-123">默认值为 Windows。</span><span class="sxs-lookup"><span data-stu-id="c018b-123">The default value is Windows.</span></span> <span data-ttu-id="c018b-124">此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。</span><span class="sxs-lookup"><span data-stu-id="c018b-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="c018b-125">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="c018b-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="c018b-126">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c018b-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c018b-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="c018b-127">-   RC4Stream</span></span><br /><span data-ttu-id="c018b-128">-   AES</span><span class="sxs-lookup"><span data-stu-id="c018b-128">-   AES</span></span><br /><br /> <span data-ttu-id="c018b-129">默认值为 RC4Stream。</span><span class="sxs-lookup"><span data-stu-id="c018b-129">The default value is RC4Stream.</span></span> <span data-ttu-id="c018b-130">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="c018b-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="c018b-131">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="c018b-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="c018b-132">加密可以确保消息的完整性，而 EncryptAndSign 不仅可以确保消息的完整性，还可以确保消息的不可否认性，也就是说，消息确实来自发送者，并且发送者与其所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="c018b-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="c018b-133">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c018b-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c018b-134">内容无保护。</span><span class="sxs-lookup"><span data-stu-id="c018b-134">-   None: No protection.</span></span><br /><span data-ttu-id="c018b-135">表明对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="c018b-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c018b-136">EncryptAndSign对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="c018b-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="c018b-137">默认值为 Sign。</span><span class="sxs-lookup"><span data-stu-id="c018b-137">The default value is Sign.</span></span> <span data-ttu-id="c018b-138">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="c018b-138">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="c018b-139">指定用于计算签名中的摘要的算法。</span><span class="sxs-lookup"><span data-stu-id="c018b-139">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="c018b-140">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c018b-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c018b-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="c018b-141">-   MD5</span></span><br /><span data-ttu-id="c018b-142">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="c018b-142">-   SHA1</span></span><br /><span data-ttu-id="c018b-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="c018b-143">-   SHA256</span></span><br /><span data-ttu-id="c018b-144">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="c018b-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="c018b-145">默认值为 SHA1。</span><span class="sxs-lookup"><span data-stu-id="c018b-145">The default value is SHA1.</span></span> <span data-ttu-id="c018b-146">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="c018b-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="c018b-147">由于 MD5 和 SHA1 出现冲突，Microsoft 建议 SHA256 或更好。</span><span class="sxs-lookup"><span data-stu-id="c018b-147">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c018b-148">子元素</span><span class="sxs-lookup"><span data-stu-id="c018b-148">Child Elements</span></span>  
 <span data-ttu-id="c018b-149">无。</span><span class="sxs-lookup"><span data-stu-id="c018b-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c018b-150">父元素</span><span class="sxs-lookup"><span data-stu-id="c018b-150">Parent Elements</span></span>  
  
|<span data-ttu-id="c018b-151">元素</span><span class="sxs-lookup"><span data-stu-id="c018b-151">Element</span></span>|<span data-ttu-id="c018b-152">描述</span><span class="sxs-lookup"><span data-stu-id="c018b-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c018b-153">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="c018b-153">\<msmqIntegration></span></span>](msmqintegration.md)|<span data-ttu-id="c018b-154">指定与消息队列 (MSMQ) 发送方或接收方进行交互所需的设置。</span><span class="sxs-lookup"><span data-stu-id="c018b-154">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="c018b-155">\<msmqTransport></span><span class="sxs-lookup"><span data-stu-id="c018b-155">\<msmqTransport></span></span>](msmqtransport.md)|<span data-ttu-id="c018b-156">指定使用本机 MSMQ 协议的 Windows Communication Foundation (WCF) 服务的队列通信属性。</span><span class="sxs-lookup"><span data-stu-id="c018b-156">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c018b-157">备注</span><span class="sxs-lookup"><span data-stu-id="c018b-157">Remarks</span></span>  
 <span data-ttu-id="c018b-158">有关传输安全的详细信息，请参阅[传输安全性](../../../wcf/feature-details/transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="c018b-158">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c018b-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="c018b-159">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c018b-160">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="c018b-160">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="c018b-161">传输</span><span class="sxs-lookup"><span data-stu-id="c018b-161">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="c018b-162">选择传输</span><span class="sxs-lookup"><span data-stu-id="c018b-162">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="c018b-163">绑定</span><span class="sxs-lookup"><span data-stu-id="c018b-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c018b-164">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="c018b-164">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c018b-165">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c018b-165">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c018b-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c018b-166">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="c018b-167">传输安全性</span><span class="sxs-lookup"><span data-stu-id="c018b-167">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
