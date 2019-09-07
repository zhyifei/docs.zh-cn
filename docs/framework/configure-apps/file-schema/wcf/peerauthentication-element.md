---
title: <peerAuthentication> 元素
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 4c29c84a2cc56a890c8273e410ba31b5f3900732
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400084"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="757ab-102">\<peerAuthentication > 元素</span><span class="sxs-lookup"><span data-stu-id="757ab-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="757ab-103">指定用于对等客户端的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="757ab-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="757ab-104">有关对等编程的详细信息，请参阅对等[网络](../../../wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="757ab-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="757ab-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="757ab-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="757ab-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="757ab-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="757ab-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="757ab-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="757ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="757ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="757ab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="757ab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="757ab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="757ab-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="757ab-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<对等 >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="757ab-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="757ab-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<peerAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="757ab-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="757ab-113">语法</span><span class="sxs-lookup"><span data-stu-id="757ab-113">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="757ab-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="757ab-114">Attributes and Elements</span></span>  
 <span data-ttu-id="757ab-115">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="757ab-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="757ab-116">特性</span><span class="sxs-lookup"><span data-stu-id="757ab-116">Attributes</span></span>  
  
|<span data-ttu-id="757ab-117">特性</span><span class="sxs-lookup"><span data-stu-id="757ab-117">Attribute</span></span>|<span data-ttu-id="757ab-118">描述</span><span class="sxs-lookup"><span data-stu-id="757ab-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="757ab-119">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="757ab-119">Optional string.</span></span> <span data-ttu-id="757ab-120">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="757ab-120">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="757ab-121">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="757ab-121">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="757ab-122">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="757ab-122">Optional enumeration.</span></span> <span data-ttu-id="757ab-123">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="757ab-123">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="757ab-124">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="757ab-124">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="757ab-125">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="757ab-125">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="757ab-126">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="757ab-126">Optional enumeration.</span></span> <span data-ttu-id="757ab-127">用于检查吊销证书列表 (CRL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="757ab-127">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="757ab-128">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="757ab-128">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="757ab-129">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="757ab-129">Optional enumeration.</span></span> <span data-ttu-id="757ab-130">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="757ab-130">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="757ab-131">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="757ab-131">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="757ab-132">针对指定存储位置中的 "**受信任人**" 存储执行验证。</span><span class="sxs-lookup"><span data-stu-id="757ab-132">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="757ab-133">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="757ab-133">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="757ab-134">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="757ab-134">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="757ab-135">值</span><span class="sxs-lookup"><span data-stu-id="757ab-135">Value</span></span>|<span data-ttu-id="757ab-136">描述</span><span class="sxs-lookup"><span data-stu-id="757ab-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="757ab-137">String</span><span class="sxs-lookup"><span data-stu-id="757ab-137">String</span></span>|<span data-ttu-id="757ab-138">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="757ab-138">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="757ab-139">至少需要命名空间和类型名称。</span><span class="sxs-lookup"><span data-stu-id="757ab-139">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="757ab-140">可选信息包括：程序集名称、版本号、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="757ab-140">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="757ab-141">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="757ab-141">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="757ab-142">值</span><span class="sxs-lookup"><span data-stu-id="757ab-142">Value</span></span>|<span data-ttu-id="757ab-143">描述</span><span class="sxs-lookup"><span data-stu-id="757ab-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="757ab-144">枚举</span><span class="sxs-lookup"><span data-stu-id="757ab-144">Enumeration</span></span>|<span data-ttu-id="757ab-145">下列值之一：`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust` 和 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="757ab-145">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="757ab-146">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="757ab-146">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="757ab-147">有关详细信息，请参阅使用[证书](../../../wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="757ab-147">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="757ab-148">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="757ab-148">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="757ab-149">值</span><span class="sxs-lookup"><span data-stu-id="757ab-149">Value</span></span>|<span data-ttu-id="757ab-150">描述</span><span class="sxs-lookup"><span data-stu-id="757ab-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="757ab-151">枚举</span><span class="sxs-lookup"><span data-stu-id="757ab-151">Enumeration</span></span>|<span data-ttu-id="757ab-152">下列值之一：`NoCheck`、`Online` 和 `Offline`。</span><span class="sxs-lookup"><span data-stu-id="757ab-152">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="757ab-153">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="757ab-153">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="757ab-154">有关详细信息，请参阅使用[证书](../../../wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="757ab-154">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="757ab-155">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="757ab-155">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="757ab-156">值</span><span class="sxs-lookup"><span data-stu-id="757ab-156">Value</span></span>|<span data-ttu-id="757ab-157">描述</span><span class="sxs-lookup"><span data-stu-id="757ab-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="757ab-158">枚举</span><span class="sxs-lookup"><span data-stu-id="757ab-158">Enumeration</span></span>|<span data-ttu-id="757ab-159">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="757ab-159">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="757ab-160">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="757ab-160">The default is `CurrentUser`.</span></span> <span data-ttu-id="757ab-161">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="757ab-161">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="757ab-162">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="757ab-162">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="757ab-163">子元素</span><span class="sxs-lookup"><span data-stu-id="757ab-163">Child Elements</span></span>  
 <span data-ttu-id="757ab-164">无。</span><span class="sxs-lookup"><span data-stu-id="757ab-164">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="757ab-165">父元素</span><span class="sxs-lookup"><span data-stu-id="757ab-165">Parent Elements</span></span>  
  
|<span data-ttu-id="757ab-166">元素</span><span class="sxs-lookup"><span data-stu-id="757ab-166">Element</span></span>|<span data-ttu-id="757ab-167">描述</span><span class="sxs-lookup"><span data-stu-id="757ab-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="757ab-168">\<peer></span><span class="sxs-lookup"><span data-stu-id="757ab-168">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="757ab-169">指定一个用于向对等服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="757ab-169">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="757ab-170">备注</span><span class="sxs-lookup"><span data-stu-id="757ab-170">Remarks</span></span>  
 <span data-ttu-id="757ab-171">`<authentication>` 元素与 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 类相对应。</span><span class="sxs-lookup"><span data-stu-id="757ab-171">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="757ab-172">此元素指定一个验证程序，在网格中执行邻居对等身份验证的过程中将调用该验证程序。</span><span class="sxs-lookup"><span data-stu-id="757ab-172">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="757ab-173">当新对等方尝试建立邻居连接时，它会将自己的凭据传递到响应的对等方。</span><span class="sxs-lookup"><span data-stu-id="757ab-173">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="757ab-174">将调用响应方的验证程序来验证远程方的凭据。</span><span class="sxs-lookup"><span data-stu-id="757ab-174">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="757ab-175">每当在网格中建立对等连接时，对等方将会相互进行身份验证，这意味着会同时在两方调用验证程序。</span><span class="sxs-lookup"><span data-stu-id="757ab-175">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="757ab-176">示例</span><span class="sxs-lookup"><span data-stu-id="757ab-176">Example</span></span>  
 <span data-ttu-id="757ab-177">下面的代码将证书验证模式设置为 `PeerOrChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="757ab-177">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="757ab-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="757ab-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="757ab-179">使用证书</span><span class="sxs-lookup"><span data-stu-id="757ab-179">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="757ab-180">对等网络</span><span class="sxs-lookup"><span data-stu-id="757ab-180">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="757ab-181">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="757ab-181">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="757ab-182">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="757ab-182">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="757ab-183">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="757ab-183">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
