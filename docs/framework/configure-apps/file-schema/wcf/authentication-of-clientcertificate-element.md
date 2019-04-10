---
title: <authentication> <clientCertificate>元素
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: e232cde8f6838de734e37aeee3f52cd7f7e7502d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221197"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="c6c7b-102">\<身份验证 > 的\<clientCertificate > 元素</span><span class="sxs-lookup"><span data-stu-id="c6c7b-102">\<authentication> of \<clientCertificate> Element</span></span>
<span data-ttu-id="c6c7b-103">指定服务所使用的客户端证书的身份验证行为。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
 <span data-ttu-id="c6c7b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c6c7b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c6c7b-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c6c7b-105">\<behaviors></span></span>  
<span data-ttu-id="c6c7b-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c6c7b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c6c7b-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c6c7b-107">\<behavior></span></span>  
<span data-ttu-id="c6c7b-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="c6c7b-108">\<serviceCredentials></span></span>  
<span data-ttu-id="c6c7b-109">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="c6c7b-109">\<clientCertificate></span></span>  
<span data-ttu-id="c6c7b-110">\<身份验证 ></span><span class="sxs-lookup"><span data-stu-id="c6c7b-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c7b-111">语法</span><span class="sxs-lookup"><span data-stu-id="c6c7b-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6c7b-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c6c7b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c6c7b-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6c7b-114">特性</span><span class="sxs-lookup"><span data-stu-id="c6c7b-114">Attributes</span></span>  
  
|<span data-ttu-id="c6c7b-115">特性</span><span class="sxs-lookup"><span data-stu-id="c6c7b-115">Attribute</span></span>|<span data-ttu-id="c6c7b-116">描述</span><span class="sxs-lookup"><span data-stu-id="c6c7b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6c7b-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="c6c7b-117">customCertificateValidatorType</span></span>|<span data-ttu-id="c6c7b-118">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-118">Optional string.</span></span> <span data-ttu-id="c6c7b-119">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="c6c7b-120">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="c6c7b-121">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="c6c7b-121">certificateValidationMode</span></span>|<span data-ttu-id="c6c7b-122">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-122">Optional enumeration.</span></span> <span data-ttu-id="c6c7b-123">指定用来验证凭据的其中一种模式。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-123">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="c6c7b-124">此特性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-124">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="c6c7b-125">如果设置为 <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-125">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="c6c7b-126">默认值为 <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-126">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="c6c7b-127">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="c6c7b-127">includeWindowsGroups</span></span>|<span data-ttu-id="c6c7b-128">可选的布尔值。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-128">Optional Boolean.</span></span> <span data-ttu-id="c6c7b-129">指定 Windows 组是否包含在安全上下文中。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-129">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="c6c7b-130">将此属性设置为 `true` 会影响性能，因为这会导致完全组扩展。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-130">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="c6c7b-131">如果不需要建立用户所属组的列表，请将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-131">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="c6c7b-132">mapClientCertificateToWindowsAcccount</span><span class="sxs-lookup"><span data-stu-id="c6c7b-132">mapClientCertificateToWindowsAcccount</span></span>|<span data-ttu-id="c6c7b-133">布尔值。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-133">Boolean.</span></span> <span data-ttu-id="c6c7b-134">指定是否可以使用证书将客户端映射到 Windows 标识。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-134">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="c6c7b-135">为此，必须启用 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-135">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="c6c7b-136">revocationMode</span><span class="sxs-lookup"><span data-stu-id="c6c7b-136">revocationMode</span></span>|<span data-ttu-id="c6c7b-137">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-137">Optional enumeration.</span></span> <span data-ttu-id="c6c7b-138">用于检查吊销证书列表 (RCL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-138">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="c6c7b-139">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-139">The default is `Online`.</span></span> <span data-ttu-id="c6c7b-140">使用 HTTP 传输安全性时，将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-140">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="c6c7b-141">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c6c7b-141">trustedStoreLocation</span></span>|<span data-ttu-id="c6c7b-142">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-142">Optional enumeration.</span></span> <span data-ttu-id="c6c7b-143">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-143">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="c6c7b-144">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-144">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="c6c7b-145">对执行验证**受信任的人员**将存储在指定的存储位置。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-145">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="c6c7b-146">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-146">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="c6c7b-147">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="c6c7b-147">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="c6c7b-148">“值”</span><span class="sxs-lookup"><span data-stu-id="c6c7b-148">Value</span></span>|<span data-ttu-id="c6c7b-149">描述</span><span class="sxs-lookup"><span data-stu-id="c6c7b-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c6c7b-150">String</span><span class="sxs-lookup"><span data-stu-id="c6c7b-150">String</span></span>|<span data-ttu-id="c6c7b-151">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-151">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="c6c7b-152">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="c6c7b-152">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="c6c7b-153">“值”</span><span class="sxs-lookup"><span data-stu-id="c6c7b-153">Value</span></span>|<span data-ttu-id="c6c7b-154">描述</span><span class="sxs-lookup"><span data-stu-id="c6c7b-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c6c7b-155">枚举</span><span class="sxs-lookup"><span data-stu-id="c6c7b-155">Enumeration</span></span>|<span data-ttu-id="c6c7b-156">以下值之一：None、 PeerTrust、 ChainTrust、 PeerOrChainTrust、 自定义。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-156">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="c6c7b-157">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-157">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="c6c7b-158">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="c6c7b-158">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="c6c7b-159">“值”</span><span class="sxs-lookup"><span data-stu-id="c6c7b-159">Value</span></span>|<span data-ttu-id="c6c7b-160">描述</span><span class="sxs-lookup"><span data-stu-id="c6c7b-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c6c7b-161">枚举</span><span class="sxs-lookup"><span data-stu-id="c6c7b-161">Enumeration</span></span>|<span data-ttu-id="c6c7b-162">以下值之一：NoCheck、 Online 和 Offline。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-162">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="c6c7b-163">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-163">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="c6c7b-164">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="c6c7b-164">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="c6c7b-165">“值”</span><span class="sxs-lookup"><span data-stu-id="c6c7b-165">Value</span></span>|<span data-ttu-id="c6c7b-166">描述</span><span class="sxs-lookup"><span data-stu-id="c6c7b-166">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c6c7b-167">枚举</span><span class="sxs-lookup"><span data-stu-id="c6c7b-167">Enumeration</span></span>|<span data-ttu-id="c6c7b-168">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-168">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="c6c7b-169">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-169">The default is `CurrentUser`.</span></span> <span data-ttu-id="c6c7b-170">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-170">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="c6c7b-171">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-171">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6c7b-172">子元素</span><span class="sxs-lookup"><span data-stu-id="c6c7b-172">Child Elements</span></span>  
 <span data-ttu-id="c6c7b-173">无。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-173">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6c7b-174">父元素</span><span class="sxs-lookup"><span data-stu-id="c6c7b-174">Parent Elements</span></span>  
  
|<span data-ttu-id="c6c7b-175">元素</span><span class="sxs-lookup"><span data-stu-id="c6c7b-175">Element</span></span>|<span data-ttu-id="c6c7b-176">描述</span><span class="sxs-lookup"><span data-stu-id="c6c7b-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6c7b-177">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="c6c7b-177">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="c6c7b-178">定义用于针对服务进行客户端身份验证的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-178">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6c7b-179">备注</span><span class="sxs-lookup"><span data-stu-id="c6c7b-179">Remarks</span></span>  
 <span data-ttu-id="c6c7b-180">`<authentication>` 元素与 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 类相对应。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-180">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="c6c7b-181">利用它您可以自定义对客户端进行身份验证的方式。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-181">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="c6c7b-182">可以将 `certificateValidationMode` 属性设置为 `None`、`ChainTrust`、`PeerOrChainTrust`、`PeerTrust` 或 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-182">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="c6c7b-183">默认情况下的级别设置为`ChainTrust`，它指定每个证书都必须存在的证书以层次结构中*根颁发机构*链的顶部。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-183">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="c6c7b-184">这是最安全的模式。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-184">This is the most secure mode.</span></span> <span data-ttu-id="c6c7b-185">您还可以将此值设置为 `PeerOrChainTrust`，该值指定受信任的链中的证书以及自行颁发的证书（对等信任）都被接受。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-185">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="c6c7b-186">因为不需要从受信任的证书颁发机构那里购买自行颁发的证书，所以可以在开发和调试客户端和服务时使用此值。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-186">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="c6c7b-187">在部署客户端时，请改用 `ChainTrust` 值。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-187">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="c6c7b-188">还可以将该值设置为 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-188">You can also set the value to `Custom`.</span></span> <span data-ttu-id="c6c7b-189">当该值设置为 `Custom` 值时，您还必须将 `customCertificateValidatorType` 属性设置为用于验证证书的程序集和类型。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-189">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="c6c7b-190">若要创建您自己的自定义验证程序，必须从 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 抽象类进行继承。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-190">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="c6c7b-191">有关详细信息，请参阅[如何：创建使用自定义证书验证程序的服务](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-191">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6c7b-192">示例</span><span class="sxs-lookup"><span data-stu-id="c6c7b-192">Example</span></span>  
 <span data-ttu-id="c6c7b-193">下面的代码指定 `<authentication>` 元素中的 X.509 证书和自定义验证类型。</span><span class="sxs-lookup"><span data-stu-id="c6c7b-193">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
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
  
## <a name="see-also"></a><span data-ttu-id="c6c7b-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6c7b-194">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="c6c7b-195">安全行为</span><span class="sxs-lookup"><span data-stu-id="c6c7b-195">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c6c7b-196">如何：创建使用自定义证书验证程序的服务</span><span class="sxs-lookup"><span data-stu-id="c6c7b-196">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="c6c7b-197">使用证书</span><span class="sxs-lookup"><span data-stu-id="c6c7b-197">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
