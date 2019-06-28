---
title: <peerAuthentication> 元素
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 6aa11c50ef950a8a9d902a0fb77fdf301d18f7cb
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423042"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="ec36b-102">\<peerAuthentication > 元素</span><span class="sxs-lookup"><span data-stu-id="ec36b-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="ec36b-103">指定用于对等客户端的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="ec36b-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="ec36b-104">有关对等编程的详细信息，请参阅[对等网络](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="ec36b-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="ec36b-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ec36b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ec36b-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ec36b-106">\<behaviors></span></span>  
<span data-ttu-id="ec36b-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="ec36b-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="ec36b-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ec36b-108">\<behavior></span></span>  
<span data-ttu-id="ec36b-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ec36b-109">\<clientCredentials></span></span>  
<span data-ttu-id="ec36b-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="ec36b-110">\<peer></span></span>  
<span data-ttu-id="ec36b-111">\<PeerAuthentication></span><span class="sxs-lookup"><span data-stu-id="ec36b-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec36b-112">语法</span><span class="sxs-lookup"><span data-stu-id="ec36b-112">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec36b-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ec36b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ec36b-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ec36b-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec36b-115">特性</span><span class="sxs-lookup"><span data-stu-id="ec36b-115">Attributes</span></span>  
  
|<span data-ttu-id="ec36b-116">特性</span><span class="sxs-lookup"><span data-stu-id="ec36b-116">Attribute</span></span>|<span data-ttu-id="ec36b-117">描述</span><span class="sxs-lookup"><span data-stu-id="ec36b-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="ec36b-118">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="ec36b-118">Optional string.</span></span> <span data-ttu-id="ec36b-119">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="ec36b-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ec36b-120">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="ec36b-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="ec36b-121">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="ec36b-121">Optional enumeration.</span></span> <span data-ttu-id="ec36b-122">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="ec36b-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="ec36b-123">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="ec36b-124">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="ec36b-125">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="ec36b-125">Optional enumeration.</span></span> <span data-ttu-id="ec36b-126">用于检查吊销证书列表 (CRL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="ec36b-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="ec36b-127">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="ec36b-128">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="ec36b-128">Optional enumeration.</span></span> <span data-ttu-id="ec36b-129">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="ec36b-130">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="ec36b-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="ec36b-131">对执行验证**受信任的人员**将存储在指定的存储位置。</span><span class="sxs-lookup"><span data-stu-id="ec36b-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="ec36b-132">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="ec36b-133">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="ec36b-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="ec36b-134">值</span><span class="sxs-lookup"><span data-stu-id="ec36b-134">Value</span></span>|<span data-ttu-id="ec36b-135">描述</span><span class="sxs-lookup"><span data-stu-id="ec36b-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec36b-136">String</span><span class="sxs-lookup"><span data-stu-id="ec36b-136">String</span></span>|<span data-ttu-id="ec36b-137">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="ec36b-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="ec36b-138">至少需要命名空间和类型名称。</span><span class="sxs-lookup"><span data-stu-id="ec36b-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="ec36b-139">可选信息包括：程序集名称、版本号、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="ec36b-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="ec36b-140">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="ec36b-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="ec36b-141">值</span><span class="sxs-lookup"><span data-stu-id="ec36b-141">Value</span></span>|<span data-ttu-id="ec36b-142">描述</span><span class="sxs-lookup"><span data-stu-id="ec36b-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec36b-143">枚举</span><span class="sxs-lookup"><span data-stu-id="ec36b-143">Enumeration</span></span>|<span data-ttu-id="ec36b-144">下列值之一：`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust` 和 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="ec36b-145">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="ec36b-146">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="ec36b-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="ec36b-147">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="ec36b-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="ec36b-148">值</span><span class="sxs-lookup"><span data-stu-id="ec36b-148">Value</span></span>|<span data-ttu-id="ec36b-149">描述</span><span class="sxs-lookup"><span data-stu-id="ec36b-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec36b-150">枚举</span><span class="sxs-lookup"><span data-stu-id="ec36b-150">Enumeration</span></span>|<span data-ttu-id="ec36b-151">下列值之一：`NoCheck`、`Online` 和 `Offline`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="ec36b-152">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="ec36b-153">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="ec36b-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="ec36b-154">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="ec36b-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="ec36b-155">值</span><span class="sxs-lookup"><span data-stu-id="ec36b-155">Value</span></span>|<span data-ttu-id="ec36b-156">描述</span><span class="sxs-lookup"><span data-stu-id="ec36b-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ec36b-157">枚举</span><span class="sxs-lookup"><span data-stu-id="ec36b-157">Enumeration</span></span>|<span data-ttu-id="ec36b-158">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="ec36b-159">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="ec36b-160">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="ec36b-161">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec36b-162">子元素</span><span class="sxs-lookup"><span data-stu-id="ec36b-162">Child Elements</span></span>  
 <span data-ttu-id="ec36b-163">无。</span><span class="sxs-lookup"><span data-stu-id="ec36b-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec36b-164">父元素</span><span class="sxs-lookup"><span data-stu-id="ec36b-164">Parent Elements</span></span>  
  
|<span data-ttu-id="ec36b-165">元素</span><span class="sxs-lookup"><span data-stu-id="ec36b-165">Element</span></span>|<span data-ttu-id="ec36b-166">描述</span><span class="sxs-lookup"><span data-stu-id="ec36b-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec36b-167">\<peer></span><span class="sxs-lookup"><span data-stu-id="ec36b-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="ec36b-168">指定一个用于向对等服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="ec36b-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec36b-169">备注</span><span class="sxs-lookup"><span data-stu-id="ec36b-169">Remarks</span></span>  
 <span data-ttu-id="ec36b-170">`<authentication>` 元素与 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 类相对应。</span><span class="sxs-lookup"><span data-stu-id="ec36b-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="ec36b-171">此元素指定一个验证程序，在网格中执行邻居对等身份验证的过程中将调用该验证程序。</span><span class="sxs-lookup"><span data-stu-id="ec36b-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="ec36b-172">当新对等方尝试建立邻居连接时，它会将自己的凭据传递到响应的对等方。</span><span class="sxs-lookup"><span data-stu-id="ec36b-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="ec36b-173">将调用响应方的验证程序来验证远程方的凭据。</span><span class="sxs-lookup"><span data-stu-id="ec36b-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="ec36b-174">每当在网格中建立对等连接时，对等方将会相互进行身份验证，这意味着会同时在两方调用验证程序。</span><span class="sxs-lookup"><span data-stu-id="ec36b-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec36b-175">示例</span><span class="sxs-lookup"><span data-stu-id="ec36b-175">Example</span></span>  
 <span data-ttu-id="ec36b-176">下面的代码将证书验证模式设置为 `PeerOrChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="ec36b-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="ec36b-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec36b-177">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="ec36b-178">使用证书</span><span class="sxs-lookup"><span data-stu-id="ec36b-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ec36b-179">对等网络</span><span class="sxs-lookup"><span data-stu-id="ec36b-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="ec36b-180">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ec36b-180">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="ec36b-181">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ec36b-181">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="ec36b-182">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="ec36b-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
