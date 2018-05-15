---
title: '&lt;clientCertificate&gt; 的 &lt;authentication&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: ccc184f63428fd4a12b9047c0bcf4416e87f24d2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltauthenticationgt-of-ltclientcertificategt-element"></a><span data-ttu-id="442a1-102">&lt;clientCertificate&gt; 的 &lt;authentication&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="442a1-102">&lt;authentication&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="442a1-103">指定服务所使用的客户端证书的身份验证行为。</span><span class="sxs-lookup"><span data-stu-id="442a1-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
 <span data-ttu-id="442a1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="442a1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="442a1-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="442a1-105">\<behaviors></span></span>  
<span data-ttu-id="442a1-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="442a1-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="442a1-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="442a1-107">\<behavior></span></span>  
<span data-ttu-id="442a1-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="442a1-108">\<serviceCredentials></span></span>  
<span data-ttu-id="442a1-109">\<t i a l ></span><span class="sxs-lookup"><span data-stu-id="442a1-109">\<clientCertificate></span></span>  
<span data-ttu-id="442a1-110">\<身份验证 ></span><span class="sxs-lookup"><span data-stu-id="442a1-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="442a1-111">语法</span><span class="sxs-lookup"><span data-stu-id="442a1-111">Syntax</span></span>  
  
```xml  
<authentication  
customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
includeWindowsGroups="Boolean"  
mapClientCertificateToWindowsAccount="Boolean"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="442a1-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="442a1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="442a1-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="442a1-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="442a1-114">特性</span><span class="sxs-lookup"><span data-stu-id="442a1-114">Attributes</span></span>  
  
|<span data-ttu-id="442a1-115">特性</span><span class="sxs-lookup"><span data-stu-id="442a1-115">Attribute</span></span>|<span data-ttu-id="442a1-116">描述</span><span class="sxs-lookup"><span data-stu-id="442a1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="442a1-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="442a1-117">customCertificateValidatorType</span></span>|<span data-ttu-id="442a1-118">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="442a1-118">Optional string.</span></span> <span data-ttu-id="442a1-119">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="442a1-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="442a1-120">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="442a1-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="442a1-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="442a1-121">certificateValidationMode</span></span>|<span data-ttu-id="442a1-122">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="442a1-122">Optional enumeration.</span></span> <span data-ttu-id="442a1-123">指定用来验证凭据的其中一种模式。</span><span class="sxs-lookup"><span data-stu-id="442a1-123">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="442a1-124">此特性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="442a1-124">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="442a1-125">如果设置为 <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="442a1-125">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="442a1-126">默认值为 <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="442a1-126">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="442a1-127">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="442a1-127">includeWindowsGroups</span></span>|<span data-ttu-id="442a1-128">可选的布尔值。</span><span class="sxs-lookup"><span data-stu-id="442a1-128">Optional Boolean.</span></span> <span data-ttu-id="442a1-129">指定 Windows 组是否包含在安全上下文中。</span><span class="sxs-lookup"><span data-stu-id="442a1-129">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="442a1-130">将此属性设置为 `true` 会影响性能，因为这会导致完全组扩展。</span><span class="sxs-lookup"><span data-stu-id="442a1-130">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="442a1-131">如果不需要建立用户所属组的列表，请将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="442a1-131">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="442a1-132">mapClientCertificateToWindowsAcccount</span><span class="sxs-lookup"><span data-stu-id="442a1-132">mapClientCertificateToWindowsAcccount</span></span>|<span data-ttu-id="442a1-133">布尔值。</span><span class="sxs-lookup"><span data-stu-id="442a1-133">Boolean.</span></span> <span data-ttu-id="442a1-134">指定是否可以使用证书将客户端映射到 Windows 标识。</span><span class="sxs-lookup"><span data-stu-id="442a1-134">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="442a1-135">为此，必须启用 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="442a1-135">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="442a1-136">revocationMode</span><span class="sxs-lookup"><span data-stu-id="442a1-136">revocationMode</span></span>|<span data-ttu-id="442a1-137">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="442a1-137">Optional enumeration.</span></span> <span data-ttu-id="442a1-138">用于检查吊销证书列表 (RCL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="442a1-138">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="442a1-139">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="442a1-139">The default is `Online`.</span></span> <span data-ttu-id="442a1-140">使用 HTTP 传输安全性时，将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="442a1-140">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="442a1-141">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="442a1-141">trustedStoreLocation</span></span>|<span data-ttu-id="442a1-142">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="442a1-142">Optional enumeration.</span></span> <span data-ttu-id="442a1-143">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="442a1-143">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="442a1-144">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="442a1-144">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="442a1-145">验证针对**受信任人**将存储在指定的存储位置。</span><span class="sxs-lookup"><span data-stu-id="442a1-145">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="442a1-146">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="442a1-146">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="442a1-147">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="442a1-147">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="442a1-148">值</span><span class="sxs-lookup"><span data-stu-id="442a1-148">Value</span></span>|<span data-ttu-id="442a1-149">描述</span><span class="sxs-lookup"><span data-stu-id="442a1-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="442a1-150">String</span><span class="sxs-lookup"><span data-stu-id="442a1-150">String</span></span>|<span data-ttu-id="442a1-151">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="442a1-151">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="442a1-152">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="442a1-152">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="442a1-153">值</span><span class="sxs-lookup"><span data-stu-id="442a1-153">Value</span></span>|<span data-ttu-id="442a1-154">描述</span><span class="sxs-lookup"><span data-stu-id="442a1-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="442a1-155">枚举</span><span class="sxs-lookup"><span data-stu-id="442a1-155">Enumeration</span></span>|<span data-ttu-id="442a1-156">下列值之一：None、PeerTrust、ChainTrust、PeerOrChainTrust 和 Custom。</span><span class="sxs-lookup"><span data-stu-id="442a1-156">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="442a1-157">有关详细信息，请参阅[使用证书](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="442a1-157">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="442a1-158">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="442a1-158">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="442a1-159">值</span><span class="sxs-lookup"><span data-stu-id="442a1-159">Value</span></span>|<span data-ttu-id="442a1-160">描述</span><span class="sxs-lookup"><span data-stu-id="442a1-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="442a1-161">枚举</span><span class="sxs-lookup"><span data-stu-id="442a1-161">Enumeration</span></span>|<span data-ttu-id="442a1-162">下列值之一：NoCheck、Online 和 Offline。</span><span class="sxs-lookup"><span data-stu-id="442a1-162">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="442a1-163">有关详细信息，请参阅[使用证书](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="442a1-163">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="442a1-164">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="442a1-164">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="442a1-165">值</span><span class="sxs-lookup"><span data-stu-id="442a1-165">Value</span></span>|<span data-ttu-id="442a1-166">描述</span><span class="sxs-lookup"><span data-stu-id="442a1-166">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="442a1-167">枚举</span><span class="sxs-lookup"><span data-stu-id="442a1-167">Enumeration</span></span>|<span data-ttu-id="442a1-168">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="442a1-168">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="442a1-169">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="442a1-169">The default is `CurrentUser`.</span></span> <span data-ttu-id="442a1-170">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="442a1-170">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="442a1-171">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="442a1-171">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="442a1-172">子元素</span><span class="sxs-lookup"><span data-stu-id="442a1-172">Child Elements</span></span>  
 <span data-ttu-id="442a1-173">无。</span><span class="sxs-lookup"><span data-stu-id="442a1-173">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="442a1-174">父元素</span><span class="sxs-lookup"><span data-stu-id="442a1-174">Parent Elements</span></span>  
  
|<span data-ttu-id="442a1-175">元素</span><span class="sxs-lookup"><span data-stu-id="442a1-175">Element</span></span>|<span data-ttu-id="442a1-176">描述</span><span class="sxs-lookup"><span data-stu-id="442a1-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="442a1-177">\<t i a l ></span><span class="sxs-lookup"><span data-stu-id="442a1-177">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="442a1-178">定义用于针对服务进行客户端身份验证的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="442a1-178">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="442a1-179">备注</span><span class="sxs-lookup"><span data-stu-id="442a1-179">Remarks</span></span>  
 <span data-ttu-id="442a1-180">`<authentication>` 元素与 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 类相对应。</span><span class="sxs-lookup"><span data-stu-id="442a1-180">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="442a1-181">利用它您可以自定义对客户端进行身份验证的方式。</span><span class="sxs-lookup"><span data-stu-id="442a1-181">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="442a1-182">可以将 `certificateValidationMode` 属性设置为 `None`、`ChainTrust`、`PeerOrChainTrust`、`PeerTrust` 或 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="442a1-182">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="442a1-183">默认情况下，级别设置为`ChainTrust`，它指定每个证书必须位于层次结构的证书以*根颁发机构*在链顶部。</span><span class="sxs-lookup"><span data-stu-id="442a1-183">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="442a1-184">这是最安全的模式。</span><span class="sxs-lookup"><span data-stu-id="442a1-184">This is the most secure mode.</span></span> <span data-ttu-id="442a1-185">您还可以将此值设置为 `PeerOrChainTrust`，该值指定受信任的链中的证书以及自行颁发的证书（对等信任）都被接受。</span><span class="sxs-lookup"><span data-stu-id="442a1-185">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="442a1-186">因为不需要从受信任的证书颁发机构那里购买自行颁发的证书，所以可以在开发和调试客户端和服务时使用此值。</span><span class="sxs-lookup"><span data-stu-id="442a1-186">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="442a1-187">在部署客户端时，请改用 `ChainTrust` 值。</span><span class="sxs-lookup"><span data-stu-id="442a1-187">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="442a1-188">还可以将该值设置为 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="442a1-188">You can also set the value to `Custom`.</span></span> <span data-ttu-id="442a1-189">当该值设置为 `Custom` 值时，您还必须将 `customCertificateValidatorType` 属性设置为用于验证证书的程序集和类型。</span><span class="sxs-lookup"><span data-stu-id="442a1-189">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="442a1-190">若要创建您自己的自定义验证程序，必须从 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 抽象类进行继承。</span><span class="sxs-lookup"><span data-stu-id="442a1-190">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="442a1-191">有关详细信息，请参阅[如何： 创建服务，它采用一个自定义证书验证程序](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)。</span><span class="sxs-lookup"><span data-stu-id="442a1-191">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="442a1-192">示例</span><span class="sxs-lookup"><span data-stu-id="442a1-192">Example</span></span>  
 <span data-ttu-id="442a1-193">下面的代码指定 `<authentication>` 元素中的 X.509 证书和自定义验证类型。</span><span class="sxs-lookup"><span data-stu-id="442a1-193">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="442a1-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="442a1-194">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>  
 <xref:System.ServiceModel.Security.X509CertificateValidationMode>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>  
 [<span data-ttu-id="442a1-195">安全行为</span><span class="sxs-lookup"><span data-stu-id="442a1-195">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="442a1-196">如何：创建使用自定义证书验证程序的服务</span><span class="sxs-lookup"><span data-stu-id="442a1-196">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="442a1-197">使用证书</span><span class="sxs-lookup"><span data-stu-id="442a1-197">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
