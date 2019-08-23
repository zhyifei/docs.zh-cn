---
title: <messageSenderAuthentication> 元素
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: 1e63b6fa93e1abfa87c83da4b5d46f492c59b9bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931374"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="d6d33-102">\<n > 元素</span><span class="sxs-lookup"><span data-stu-id="d6d33-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="d6d33-103">指定用于对等消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="d6d33-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="d6d33-104">有关对等编程的详细信息, 请参阅对等[网络](../../../wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d33-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="d6d33-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6d33-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6d33-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d6d33-106">\<behaviors></span></span>  
<span data-ttu-id="d6d33-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d6d33-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="d6d33-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d6d33-108">\<behavior></span></span>  
<span data-ttu-id="d6d33-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d6d33-109">\<clientCredentials></span></span>  
<span data-ttu-id="d6d33-110">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="d6d33-110">\<peer></span></span>  
<span data-ttu-id="d6d33-111">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="d6d33-111">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6d33-112">语法</span><span class="sxs-lookup"><span data-stu-id="d6d33-112">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6d33-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d6d33-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d6d33-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d6d33-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6d33-115">特性</span><span class="sxs-lookup"><span data-stu-id="d6d33-115">Attributes</span></span>  
  
|<span data-ttu-id="d6d33-116">特性</span><span class="sxs-lookup"><span data-stu-id="d6d33-116">Attribute</span></span>|<span data-ttu-id="d6d33-117">描述</span><span class="sxs-lookup"><span data-stu-id="d6d33-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="d6d33-118">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="d6d33-118">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="d6d33-119">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="d6d33-119">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="d6d33-120">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="d6d33-120">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="d6d33-121">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-121">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="d6d33-122">用于检查吊销证书列表 (CRL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="d6d33-122">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="d6d33-123">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-123">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="d6d33-124">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="d6d33-124">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="d6d33-125">针对指定存储位置中的 "**受信任人**" 存储执行验证。</span><span class="sxs-lookup"><span data-stu-id="d6d33-125">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="d6d33-126">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="d6d33-126">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="d6d33-127">值</span><span class="sxs-lookup"><span data-stu-id="d6d33-127">Value</span></span>|<span data-ttu-id="d6d33-128">描述</span><span class="sxs-lookup"><span data-stu-id="d6d33-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6d33-129">String</span><span class="sxs-lookup"><span data-stu-id="d6d33-129">String</span></span>|<span data-ttu-id="d6d33-130">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d33-130">Optional.</span></span> <span data-ttu-id="d6d33-131">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="d6d33-131">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="d6d33-132">至少需要命名空间和类型名称。</span><span class="sxs-lookup"><span data-stu-id="d6d33-132">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="d6d33-133">可选信息包括：程序集名称、版本号、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="d6d33-133">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="d6d33-134">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="d6d33-134">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="d6d33-135">值</span><span class="sxs-lookup"><span data-stu-id="d6d33-135">Value</span></span>|<span data-ttu-id="d6d33-136">描述</span><span class="sxs-lookup"><span data-stu-id="d6d33-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6d33-137">枚举</span><span class="sxs-lookup"><span data-stu-id="d6d33-137">Enumeration</span></span>|<span data-ttu-id="d6d33-138">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d33-138">Optional.</span></span> <span data-ttu-id="d6d33-139">下列值之一：`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust` 和 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-139">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="d6d33-140">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-140">The default is `ChainTrust`.</span></span> <span data-ttu-id="d6d33-141">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-141">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="d6d33-142">有关详细信息, 请参阅使用[证书](../../../wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d33-142">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="d6d33-143">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="d6d33-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="d6d33-144">值</span><span class="sxs-lookup"><span data-stu-id="d6d33-144">Value</span></span>|<span data-ttu-id="d6d33-145">描述</span><span class="sxs-lookup"><span data-stu-id="d6d33-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6d33-146">枚举</span><span class="sxs-lookup"><span data-stu-id="d6d33-146">Enumeration</span></span>|<span data-ttu-id="d6d33-147">下列值之一：`NoCheck`、`Online` 和 `Offline`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-147">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="d6d33-148">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-148">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="d6d33-149">有关详细信息, 请参阅使用[证书](../../../wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d33-149">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="d6d33-150">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="d6d33-150">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="d6d33-151">值</span><span class="sxs-lookup"><span data-stu-id="d6d33-151">Value</span></span>|<span data-ttu-id="d6d33-152">描述</span><span class="sxs-lookup"><span data-stu-id="d6d33-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d6d33-153">枚举</span><span class="sxs-lookup"><span data-stu-id="d6d33-153">Enumeration</span></span>|<span data-ttu-id="d6d33-154">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-154">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="d6d33-155">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-155">The default is `CurrentUser`.</span></span> <span data-ttu-id="d6d33-156">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-156">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="d6d33-157">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-157">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="d6d33-158">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-158">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6d33-159">子元素</span><span class="sxs-lookup"><span data-stu-id="d6d33-159">Child Elements</span></span>  
 <span data-ttu-id="d6d33-160">无。</span><span class="sxs-lookup"><span data-stu-id="d6d33-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6d33-161">父元素</span><span class="sxs-lookup"><span data-stu-id="d6d33-161">Parent Elements</span></span>  
  
|<span data-ttu-id="d6d33-162">元素</span><span class="sxs-lookup"><span data-stu-id="d6d33-162">Element</span></span>|<span data-ttu-id="d6d33-163">描述</span><span class="sxs-lookup"><span data-stu-id="d6d33-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6d33-164">\<peer></span><span class="sxs-lookup"><span data-stu-id="d6d33-164">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="d6d33-165">指定一个用于向对等服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="d6d33-165">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6d33-166">备注</span><span class="sxs-lookup"><span data-stu-id="d6d33-166">Remarks</span></span>  
 <span data-ttu-id="d6d33-167">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="d6d33-167">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="d6d33-168">对于输出通道, 每条消息都使用[ \<证书 >](certificate-element.md)提供的证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="d6d33-168">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="d6d33-169">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="d6d33-169">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="d6d33-170">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="d6d33-170">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6d33-171">示例</span><span class="sxs-lookup"><span data-stu-id="d6d33-171">Example</span></span>  
 <span data-ttu-id="d6d33-172">下面的代码将消息发送方验证模式设置为 `PeerOrChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="d6d33-172">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d6d33-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6d33-173">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="d6d33-174">使用证书</span><span class="sxs-lookup"><span data-stu-id="d6d33-174">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d6d33-175">对等网络</span><span class="sxs-lookup"><span data-stu-id="d6d33-175">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="d6d33-176">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d6d33-176">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="d6d33-177">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d6d33-177">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="d6d33-178">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="d6d33-178">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
