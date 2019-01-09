---
title: '&lt;messageSenderAuthentication&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: d543e5ac436e181c76e2954db7a3eaa8e1b8d6a3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145863"
---
# <a name="ltmessagesenderauthenticationgt-element"></a><span data-ttu-id="47a06-102">&lt;messageSenderAuthentication&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="47a06-102">&lt;messageSenderAuthentication&gt; element</span></span>
<span data-ttu-id="47a06-103">指定用于对等消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="47a06-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="47a06-104">有关对等编程的详细信息，请参阅[对等网络](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="47a06-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="47a06-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="47a06-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="47a06-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="47a06-106">\<behaviors></span></span>  
<span data-ttu-id="47a06-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="47a06-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="47a06-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="47a06-108">\<behavior></span></span>  
<span data-ttu-id="47a06-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="47a06-109">\<clientCredentials></span></span>  
<span data-ttu-id="47a06-110">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="47a06-110">\<peer></span></span>  
<span data-ttu-id="47a06-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="47a06-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47a06-112">语法</span><span class="sxs-lookup"><span data-stu-id="47a06-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47a06-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="47a06-113">Attributes and Elements</span></span>  
 <span data-ttu-id="47a06-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="47a06-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47a06-115">特性</span><span class="sxs-lookup"><span data-stu-id="47a06-115">Attributes</span></span>  
  
|<span data-ttu-id="47a06-116">特性</span><span class="sxs-lookup"><span data-stu-id="47a06-116">Attribute</span></span>|<span data-ttu-id="47a06-117">描述</span><span class="sxs-lookup"><span data-stu-id="47a06-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47a06-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="47a06-118">customCertificateValidatorType</span></span>|<span data-ttu-id="47a06-119">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="47a06-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="47a06-120">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="47a06-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="47a06-121">certifcateValidationMode</span><span class="sxs-lookup"><span data-stu-id="47a06-121">certifcateValidationMode</span></span>|<span data-ttu-id="47a06-122">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="47a06-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="47a06-123">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="47a06-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|<span data-ttu-id="47a06-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="47a06-124">revocationMode</span></span>|<span data-ttu-id="47a06-125">用于检查吊销证书列表 (CRL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="47a06-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|<span data-ttu-id="47a06-126">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="47a06-126">trustedStoreLocation</span></span>|<span data-ttu-id="47a06-127">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="47a06-127">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="47a06-128">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="47a06-128">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="47a06-129">对执行验证**受信任的人员**将存储在指定的存储位置。</span><span class="sxs-lookup"><span data-stu-id="47a06-129">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="47a06-130">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="47a06-130">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="47a06-131">值</span><span class="sxs-lookup"><span data-stu-id="47a06-131">Value</span></span>|<span data-ttu-id="47a06-132">描述</span><span class="sxs-lookup"><span data-stu-id="47a06-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47a06-133">String</span><span class="sxs-lookup"><span data-stu-id="47a06-133">String</span></span>|<span data-ttu-id="47a06-134">可选。</span><span class="sxs-lookup"><span data-stu-id="47a06-134">Optional.</span></span> <span data-ttu-id="47a06-135">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="47a06-135">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="47a06-136">至少需要命名空间和类型名称。</span><span class="sxs-lookup"><span data-stu-id="47a06-136">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="47a06-137">可选信息包括：程序集名称、版本号、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="47a06-137">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="47a06-138">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="47a06-138">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="47a06-139">值</span><span class="sxs-lookup"><span data-stu-id="47a06-139">Value</span></span>|<span data-ttu-id="47a06-140">描述</span><span class="sxs-lookup"><span data-stu-id="47a06-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47a06-141">枚举</span><span class="sxs-lookup"><span data-stu-id="47a06-141">Enumeration</span></span>|<span data-ttu-id="47a06-142">可选。</span><span class="sxs-lookup"><span data-stu-id="47a06-142">Optional.</span></span> <span data-ttu-id="47a06-143">下列值之一：`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust` 和 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="47a06-143">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="47a06-144">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="47a06-144">The default is `ChainTrust`.</span></span> <span data-ttu-id="47a06-145">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="47a06-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="47a06-146">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="47a06-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="47a06-147">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="47a06-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="47a06-148">值</span><span class="sxs-lookup"><span data-stu-id="47a06-148">Value</span></span>|<span data-ttu-id="47a06-149">描述</span><span class="sxs-lookup"><span data-stu-id="47a06-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47a06-150">枚举</span><span class="sxs-lookup"><span data-stu-id="47a06-150">Enumeration</span></span>|<span data-ttu-id="47a06-151">下列值之一：`NoCheck`、`Online` 和 `Offline`。</span><span class="sxs-lookup"><span data-stu-id="47a06-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="47a06-152">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="47a06-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="47a06-153">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="47a06-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="47a06-154">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="47a06-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="47a06-155">值</span><span class="sxs-lookup"><span data-stu-id="47a06-155">Value</span></span>|<span data-ttu-id="47a06-156">描述</span><span class="sxs-lookup"><span data-stu-id="47a06-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="47a06-157">枚举</span><span class="sxs-lookup"><span data-stu-id="47a06-157">Enumeration</span></span>|<span data-ttu-id="47a06-158">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="47a06-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="47a06-159">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="47a06-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="47a06-160">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="47a06-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="47a06-161">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="47a06-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="47a06-162">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="47a06-162">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47a06-163">子元素</span><span class="sxs-lookup"><span data-stu-id="47a06-163">Child Elements</span></span>  
 <span data-ttu-id="47a06-164">无。</span><span class="sxs-lookup"><span data-stu-id="47a06-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47a06-165">父元素</span><span class="sxs-lookup"><span data-stu-id="47a06-165">Parent Elements</span></span>  
  
|<span data-ttu-id="47a06-166">元素</span><span class="sxs-lookup"><span data-stu-id="47a06-166">Element</span></span>|<span data-ttu-id="47a06-167">描述</span><span class="sxs-lookup"><span data-stu-id="47a06-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47a06-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="47a06-168">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="47a06-169">指定一个用于向对等服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="47a06-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47a06-170">备注</span><span class="sxs-lookup"><span data-stu-id="47a06-170">Remarks</span></span>  
 <span data-ttu-id="47a06-171">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="47a06-171">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="47a06-172">对于输出通道，每个消息进行签名使用提供的证书[\<证书 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。</span><span class="sxs-lookup"><span data-stu-id="47a06-172">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="47a06-173">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="47a06-173">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="47a06-174">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="47a06-174">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47a06-175">示例</span><span class="sxs-lookup"><span data-stu-id="47a06-175">Example</span></span>  
 <span data-ttu-id="47a06-176">下面的代码将消息发送方验证模式设置为 `PeerOrChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="47a06-176">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="47a06-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="47a06-177">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="47a06-178">使用证书</span><span class="sxs-lookup"><span data-stu-id="47a06-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="47a06-179">对等网络</span><span class="sxs-lookup"><span data-stu-id="47a06-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="47a06-180">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="47a06-180">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="47a06-181">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="47a06-181">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="47a06-182">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="47a06-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
