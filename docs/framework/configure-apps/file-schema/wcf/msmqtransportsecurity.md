---
title: '&lt;msmqTransportSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
author: BrucePerlerMS
ms.openlocfilehash: 2d9fd78e349f5c3affb1184ba0ee146eb7076922
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793716"
---
# <a name="ltmsmqtransportsecuritygt"></a><span data-ttu-id="c0712-102">&lt;msmqTransportSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="c0712-102">&lt;msmqTransportSecurity&gt;</span></span>
<span data-ttu-id="c0712-103">指定自定义绑定的 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="c0712-103">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
 <span data-ttu-id="c0712-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c0712-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c0712-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c0712-105">\<bindings></span></span>  
<span data-ttu-id="c0712-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c0712-106">\<customBinding></span></span>  
<span data-ttu-id="c0712-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c0712-107">\<binding></span></span>  
<span data-ttu-id="c0712-108">\<msmqIntegration ></span><span class="sxs-lookup"><span data-stu-id="c0712-108">\<msmqIntegration></span></span>  
<span data-ttu-id="c0712-109">\<msmqTransportSecurity ></span><span class="sxs-lookup"><span data-stu-id="c0712-109">\<msmqTransportSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0712-110">语法</span><span class="sxs-lookup"><span data-stu-id="c0712-110">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0712-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c0712-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c0712-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c0712-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0712-113">特性</span><span class="sxs-lookup"><span data-stu-id="c0712-113">Attributes</span></span>  
  
|<span data-ttu-id="c0712-114">特性</span><span class="sxs-lookup"><span data-stu-id="c0712-114">Attribute</span></span>|<span data-ttu-id="c0712-115">描述</span><span class="sxs-lookup"><span data-stu-id="c0712-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="c0712-116">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c0712-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="c0712-117">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="c0712-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="c0712-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c0712-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c0712-119">-None： 无身份验证。</span><span class="sxs-lookup"><span data-stu-id="c0712-119">-   None: No authentication.</span></span><br /><span data-ttu-id="c0712-120">-Windows： 身份验证机制使用 Active Directory 获取与消息关联的 SID 的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="c0712-120">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="c0712-121">然后使用它来检查队列的 ACL 以确保用户有权写入队列。</span><span class="sxs-lookup"><span data-stu-id="c0712-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="c0712-122">-证书： 通道从证书存储中获取的证书。</span><span class="sxs-lookup"><span data-stu-id="c0712-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="c0712-123">默认值为 Windows。</span><span class="sxs-lookup"><span data-stu-id="c0712-123">The default value is Windows.</span></span> <span data-ttu-id="c0712-124">此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。</span><span class="sxs-lookup"><span data-stu-id="c0712-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="c0712-125">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="c0712-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="c0712-126">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c0712-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c0712-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="c0712-127">-   RC4Stream</span></span><br /><span data-ttu-id="c0712-128">-AES</span><span class="sxs-lookup"><span data-stu-id="c0712-128">-   AES</span></span><br /><br /> <span data-ttu-id="c0712-129">默认值为 RC4Stream。</span><span class="sxs-lookup"><span data-stu-id="c0712-129">The default value is RC4Stream.</span></span> <span data-ttu-id="c0712-130">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="c0712-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="c0712-131">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="c0712-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="c0712-132">加密可以确保消息的完整性，而 EncryptAndSign 不仅可以确保消息的完整性，还可以确保消息的不可否认性，也就是说，消息确实来自发送者，并且发送者与其所声称的身份一致。</span><span class="sxs-lookup"><span data-stu-id="c0712-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="c0712-133">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c0712-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c0712-134">-None： 无保护。</span><span class="sxs-lookup"><span data-stu-id="c0712-134">-   None: No protection.</span></span><br /><span data-ttu-id="c0712-135">登录： 对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="c0712-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c0712-136">-EncryptAndSign： 消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="c0712-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="c0712-137">默认值为 Sign。</span><span class="sxs-lookup"><span data-stu-id="c0712-137">The default value is Sign.</span></span> <span data-ttu-id="c0712-138">此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。</span><span class="sxs-lookup"><span data-stu-id="c0712-138">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="c0712-139">指定用于计算签名中的摘要的算法。</span><span class="sxs-lookup"><span data-stu-id="c0712-139">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="c0712-140">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c0712-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c0712-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="c0712-141">-   MD5</span></span><br /><span data-ttu-id="c0712-142">-   SHA1</span><span class="sxs-lookup"><span data-stu-id="c0712-142">-   SHA1</span></span><br /><span data-ttu-id="c0712-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="c0712-143">-   SHA256</span></span><br /><span data-ttu-id="c0712-144">-   SHA512</span><span class="sxs-lookup"><span data-stu-id="c0712-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="c0712-145">默认值为 SHA1。</span><span class="sxs-lookup"><span data-stu-id="c0712-145">The default value is SHA1.</span></span> <span data-ttu-id="c0712-146">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="c0712-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0712-147">子元素</span><span class="sxs-lookup"><span data-stu-id="c0712-147">Child Elements</span></span>  
 <span data-ttu-id="c0712-148">无。</span><span class="sxs-lookup"><span data-stu-id="c0712-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0712-149">父元素</span><span class="sxs-lookup"><span data-stu-id="c0712-149">Parent Elements</span></span>  
  
|<span data-ttu-id="c0712-150">元素</span><span class="sxs-lookup"><span data-stu-id="c0712-150">Element</span></span>|<span data-ttu-id="c0712-151">描述</span><span class="sxs-lookup"><span data-stu-id="c0712-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0712-152">\<msmqIntegration ></span><span class="sxs-lookup"><span data-stu-id="c0712-152">\<msmqIntegration></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|<span data-ttu-id="c0712-153">指定与消息队列 (MSMQ) 发送方或接收方进行交互所需的设置。</span><span class="sxs-lookup"><span data-stu-id="c0712-153">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="c0712-154">\<msmqTransport ></span><span class="sxs-lookup"><span data-stu-id="c0712-154">\<msmqTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|<span data-ttu-id="c0712-155">指定使用本机 MSMQ 协议的 Windows Communication Foundation (WCF) 服务的队列通信属性。</span><span class="sxs-lookup"><span data-stu-id="c0712-155">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0712-156">备注</span><span class="sxs-lookup"><span data-stu-id="c0712-156">Remarks</span></span>  
 <span data-ttu-id="c0712-157">传输安全性的详细信息，请参阅[传输安全](../../../../../docs/framework/wcf/feature-details/transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="c0712-157">For more information on transport security, see [Transport Security](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0712-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0712-158">See Also</span></span>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="c0712-159">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="c0712-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="c0712-160">传输</span><span class="sxs-lookup"><span data-stu-id="c0712-160">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="c0712-161">选择传输</span><span class="sxs-lookup"><span data-stu-id="c0712-161">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="c0712-162">绑定</span><span class="sxs-lookup"><span data-stu-id="c0712-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c0712-163">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="c0712-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c0712-164">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c0712-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c0712-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c0712-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="c0712-166">传输安全性</span><span class="sxs-lookup"><span data-stu-id="c0712-166">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
