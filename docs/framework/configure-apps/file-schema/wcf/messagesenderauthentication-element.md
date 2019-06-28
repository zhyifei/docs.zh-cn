---
title: <messageSenderAuthentication> 元素
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 804c280bcdb0fecc87f71121b7d95b5fd0268de9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423127"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="c1e28-102">\<messageSenderAuthentication > 元素</span><span class="sxs-lookup"><span data-stu-id="c1e28-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="c1e28-103">指定用于对等消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="c1e28-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="c1e28-104">有关对等编程的详细信息，请参阅[对等网络](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e28-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="c1e28-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1e28-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1e28-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c1e28-106">\<behaviors></span></span>  
<span data-ttu-id="c1e28-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="c1e28-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="c1e28-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c1e28-108">\<behavior></span></span>  
<span data-ttu-id="c1e28-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="c1e28-109">\<clientCredentials></span></span>  
<span data-ttu-id="c1e28-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="c1e28-110">\<peer></span></span>  
<span data-ttu-id="c1e28-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="c1e28-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1e28-112">语法</span><span class="sxs-lookup"><span data-stu-id="c1e28-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1e28-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c1e28-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c1e28-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c1e28-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1e28-115">特性</span><span class="sxs-lookup"><span data-stu-id="c1e28-115">Attributes</span></span>  
  
|<span data-ttu-id="c1e28-116">特性</span><span class="sxs-lookup"><span data-stu-id="c1e28-116">Attribute</span></span>|<span data-ttu-id="c1e28-117">描述</span><span class="sxs-lookup"><span data-stu-id="c1e28-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="c1e28-118">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="c1e28-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="c1e28-119">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="c1e28-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="c1e28-120">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="c1e28-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="c1e28-121">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="c1e28-122">用于检查吊销证书列表 (CRL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="c1e28-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="c1e28-123">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="c1e28-124">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="c1e28-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="c1e28-125">对执行验证**受信任的人员**将存储在指定的存储位置。</span><span class="sxs-lookup"><span data-stu-id="c1e28-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="c1e28-126">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="c1e28-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="c1e28-127">值</span><span class="sxs-lookup"><span data-stu-id="c1e28-127">Value</span></span>|<span data-ttu-id="c1e28-128">描述</span><span class="sxs-lookup"><span data-stu-id="c1e28-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c1e28-129">String</span><span class="sxs-lookup"><span data-stu-id="c1e28-129">String</span></span>|<span data-ttu-id="c1e28-130">可选。</span><span class="sxs-lookup"><span data-stu-id="c1e28-130">Optional.</span></span> <span data-ttu-id="c1e28-131">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="c1e28-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="c1e28-132">至少需要命名空间和类型名称。</span><span class="sxs-lookup"><span data-stu-id="c1e28-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="c1e28-133">可选信息包括：程序集名称、版本号、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="c1e28-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="c1e28-134">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="c1e28-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="c1e28-135">值</span><span class="sxs-lookup"><span data-stu-id="c1e28-135">Value</span></span>|<span data-ttu-id="c1e28-136">描述</span><span class="sxs-lookup"><span data-stu-id="c1e28-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c1e28-137">枚举</span><span class="sxs-lookup"><span data-stu-id="c1e28-137">Enumeration</span></span>|<span data-ttu-id="c1e28-138">可选。</span><span class="sxs-lookup"><span data-stu-id="c1e28-138">Optional.</span></span> <span data-ttu-id="c1e28-139">下列值之一：`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust` 和 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="c1e28-140">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="c1e28-141">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="c1e28-142">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e28-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="c1e28-143">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="c1e28-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="c1e28-144">值</span><span class="sxs-lookup"><span data-stu-id="c1e28-144">Value</span></span>|<span data-ttu-id="c1e28-145">描述</span><span class="sxs-lookup"><span data-stu-id="c1e28-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c1e28-146">枚举</span><span class="sxs-lookup"><span data-stu-id="c1e28-146">Enumeration</span></span>|<span data-ttu-id="c1e28-147">下列值之一：`NoCheck`、`Online` 和 `Offline`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="c1e28-148">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="c1e28-149">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e28-149">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="c1e28-150">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="c1e28-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="c1e28-151">值</span><span class="sxs-lookup"><span data-stu-id="c1e28-151">Value</span></span>|<span data-ttu-id="c1e28-152">描述</span><span class="sxs-lookup"><span data-stu-id="c1e28-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c1e28-153">枚举</span><span class="sxs-lookup"><span data-stu-id="c1e28-153">Enumeration</span></span>|<span data-ttu-id="c1e28-154">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="c1e28-155">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="c1e28-156">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="c1e28-157">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="c1e28-158">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1e28-159">子元素</span><span class="sxs-lookup"><span data-stu-id="c1e28-159">Child Elements</span></span>  
 <span data-ttu-id="c1e28-160">无。</span><span class="sxs-lookup"><span data-stu-id="c1e28-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1e28-161">父元素</span><span class="sxs-lookup"><span data-stu-id="c1e28-161">Parent Elements</span></span>  
  
|<span data-ttu-id="c1e28-162">元素</span><span class="sxs-lookup"><span data-stu-id="c1e28-162">Element</span></span>|<span data-ttu-id="c1e28-163">描述</span><span class="sxs-lookup"><span data-stu-id="c1e28-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1e28-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="c1e28-164">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="c1e28-165">指定一个用于向对等服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="c1e28-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1e28-166">备注</span><span class="sxs-lookup"><span data-stu-id="c1e28-166">Remarks</span></span>  
 <span data-ttu-id="c1e28-167">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="c1e28-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="c1e28-168">对于输出通道，每个消息进行签名使用提供的证书[\<证书 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e28-168">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="c1e28-169">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="c1e28-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="c1e28-170">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="c1e28-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1e28-171">示例</span><span class="sxs-lookup"><span data-stu-id="c1e28-171">Example</span></span>  
 <span data-ttu-id="c1e28-172">下面的代码将消息发送方验证模式设置为 `PeerOrChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="c1e28-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1e28-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1e28-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="c1e28-174">使用证书</span><span class="sxs-lookup"><span data-stu-id="c1e28-174">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c1e28-175">对等网络</span><span class="sxs-lookup"><span data-stu-id="c1e28-175">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="c1e28-176">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c1e28-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="c1e28-177">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c1e28-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="c1e28-178">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="c1e28-178">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
