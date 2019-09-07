---
title: <messageSenderAuthentication> 元素
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397778"
---
# <a name="messagesenderauthentication-element"></a><span data-ttu-id="b51be-102">\<n > 元素</span><span class="sxs-lookup"><span data-stu-id="b51be-102">\<messageSenderAuthentication> element</span></span>
<span data-ttu-id="b51be-103">指定用于对等消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="b51be-103">Specifies authentication options for peer-to-peer message senders.</span></span>  
  
 <span data-ttu-id="b51be-104">有关对等编程的详细信息，请参阅对等[网络](../../../wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="b51be-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
<span data-ttu-id="b51be-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b51be-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b51be-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b51be-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b51be-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b51be-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b51be-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b51be-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="b51be-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b51be-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="b51be-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="b51be-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="b51be-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<对等 >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="b51be-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="b51be-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<n >**</span><span class="sxs-lookup"><span data-stu-id="b51be-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b51be-113">语法</span><span class="sxs-lookup"><span data-stu-id="b51be-113">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b51be-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b51be-114">Attributes and Elements</span></span>  
 <span data-ttu-id="b51be-115">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b51be-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b51be-116">特性</span><span class="sxs-lookup"><span data-stu-id="b51be-116">Attributes</span></span>  
  
|<span data-ttu-id="b51be-117">特性</span><span class="sxs-lookup"><span data-stu-id="b51be-117">Attribute</span></span>|<span data-ttu-id="b51be-118">描述</span><span class="sxs-lookup"><span data-stu-id="b51be-118">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="b51be-119">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="b51be-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="b51be-120">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="b51be-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="b51be-121">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="b51be-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="b51be-122">如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="b51be-122">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`revocationMode`|<span data-ttu-id="b51be-123">用于检查吊销证书列表 (CRL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="b51be-123">One of the modes used to check for a revoked certificate lists (CRL).</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="b51be-124">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="b51be-124">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="b51be-125">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="b51be-125">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="b51be-126">针对指定存储位置中的 "**受信任人**" 存储执行验证。</span><span class="sxs-lookup"><span data-stu-id="b51be-126">Validation is performed against the **Trusted People** store in the specified store location.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="b51be-127">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="b51be-127">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="b51be-128">值</span><span class="sxs-lookup"><span data-stu-id="b51be-128">Value</span></span>|<span data-ttu-id="b51be-129">描述</span><span class="sxs-lookup"><span data-stu-id="b51be-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b51be-130">String</span><span class="sxs-lookup"><span data-stu-id="b51be-130">String</span></span>|<span data-ttu-id="b51be-131">可选。</span><span class="sxs-lookup"><span data-stu-id="b51be-131">Optional.</span></span> <span data-ttu-id="b51be-132">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="b51be-132">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="b51be-133">至少需要命名空间和类型名称。</span><span class="sxs-lookup"><span data-stu-id="b51be-133">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="b51be-134">可选信息包括：程序集名称、版本号、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="b51be-134">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="b51be-135">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="b51be-135">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="b51be-136">值</span><span class="sxs-lookup"><span data-stu-id="b51be-136">Value</span></span>|<span data-ttu-id="b51be-137">描述</span><span class="sxs-lookup"><span data-stu-id="b51be-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b51be-138">枚举</span><span class="sxs-lookup"><span data-stu-id="b51be-138">Enumeration</span></span>|<span data-ttu-id="b51be-139">可选。</span><span class="sxs-lookup"><span data-stu-id="b51be-139">Optional.</span></span> <span data-ttu-id="b51be-140">下列值之一：`None`、`PeerTrust`、`ChainTrust`、`PeerOrChainTrust` 和 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="b51be-140">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="b51be-141">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="b51be-141">The default is `ChainTrust`.</span></span> <span data-ttu-id="b51be-142">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="b51be-142">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="b51be-143">有关详细信息，请参阅使用[证书](../../../wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="b51be-143">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="b51be-144">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="b51be-144">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="b51be-145">值</span><span class="sxs-lookup"><span data-stu-id="b51be-145">Value</span></span>|<span data-ttu-id="b51be-146">描述</span><span class="sxs-lookup"><span data-stu-id="b51be-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b51be-147">枚举</span><span class="sxs-lookup"><span data-stu-id="b51be-147">Enumeration</span></span>|<span data-ttu-id="b51be-148">下列值之一：`NoCheck`、`Online` 和 `Offline`。</span><span class="sxs-lookup"><span data-stu-id="b51be-148">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="b51be-149">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="b51be-149">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="b51be-150">有关详细信息，请参阅使用[证书](../../../wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="b51be-150">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="b51be-151">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="b51be-151">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="b51be-152">值</span><span class="sxs-lookup"><span data-stu-id="b51be-152">Value</span></span>|<span data-ttu-id="b51be-153">描述</span><span class="sxs-lookup"><span data-stu-id="b51be-153">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b51be-154">枚举</span><span class="sxs-lookup"><span data-stu-id="b51be-154">Enumeration</span></span>|<span data-ttu-id="b51be-155">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="b51be-155">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="b51be-156">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="b51be-156">The default is `CurrentUser`.</span></span> <span data-ttu-id="b51be-157">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="b51be-157">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="b51be-158">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="b51be-158">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span> <span data-ttu-id="b51be-159">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="b51be-159">The default is `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b51be-160">子元素</span><span class="sxs-lookup"><span data-stu-id="b51be-160">Child Elements</span></span>  
 <span data-ttu-id="b51be-161">无。</span><span class="sxs-lookup"><span data-stu-id="b51be-161">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b51be-162">父元素</span><span class="sxs-lookup"><span data-stu-id="b51be-162">Parent Elements</span></span>  
  
|<span data-ttu-id="b51be-163">元素</span><span class="sxs-lookup"><span data-stu-id="b51be-163">Element</span></span>|<span data-ttu-id="b51be-164">描述</span><span class="sxs-lookup"><span data-stu-id="b51be-164">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b51be-165">\<peer></span><span class="sxs-lookup"><span data-stu-id="b51be-165">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="b51be-166">指定一个用于向对等服务证明客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="b51be-166">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b51be-167">备注</span><span class="sxs-lookup"><span data-stu-id="b51be-167">Remarks</span></span>  
 <span data-ttu-id="b51be-168">如果选择了消息身份验证，则必须配置此元素。</span><span class="sxs-lookup"><span data-stu-id="b51be-168">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="b51be-169">对于输出通道，每条消息都使用[ \<证书 >](certificate-element.md)提供的证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="b51be-169">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="b51be-170">在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="b51be-170">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="b51be-171">验证程序可以接受或拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="b51be-171">The validator can either accept or reject the credential.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b51be-172">示例</span><span class="sxs-lookup"><span data-stu-id="b51be-172">Example</span></span>  
 <span data-ttu-id="b51be-173">下面的代码将消息发送方验证模式设置为 `PeerOrChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="b51be-173">The following code sets the message sender validation mode to `PeerOrChainTrust`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b51be-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="b51be-174">See also</span></span>

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="b51be-175">使用证书</span><span class="sxs-lookup"><span data-stu-id="b51be-175">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="b51be-176">对等网络</span><span class="sxs-lookup"><span data-stu-id="b51be-176">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="b51be-177">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b51be-177">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="b51be-178">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b51be-178">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="b51be-179">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="b51be-179">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
