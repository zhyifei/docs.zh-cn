---
title: <authentication>of <clientCertificate>元素
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 99084f6b7afbdd8586ee706cd6ec44b349d81ff2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398271"
---
# <a name="authentication-of-clientcertificate-element"></a><span data-ttu-id="aa93c-102">\<clientCertificate > 元素\<的身份验证 ></span><span class="sxs-lookup"><span data-stu-id="aa93c-102">\<authentication> of \<clientCertificate> Element</span></span>
<span data-ttu-id="aa93c-103">指定服务所使用的客户端证书的身份验证行为。</span><span class="sxs-lookup"><span data-stu-id="aa93c-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
<span data-ttu-id="aa93c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa93c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aa93c-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aa93c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aa93c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aa93c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="aa93c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aa93c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="aa93c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="aa93c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="aa93c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="aa93c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="aa93c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCertificate >** ](clientcertificate-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="aa93c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)</span></span>\
<span data-ttu-id="aa93c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<身份验证 >**</span><span class="sxs-lookup"><span data-stu-id="aa93c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa93c-112">语法</span><span class="sxs-lookup"><span data-stu-id="aa93c-112">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa93c-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="aa93c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="aa93c-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="aa93c-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa93c-115">特性</span><span class="sxs-lookup"><span data-stu-id="aa93c-115">Attributes</span></span>  
  
|<span data-ttu-id="aa93c-116">特性</span><span class="sxs-lookup"><span data-stu-id="aa93c-116">Attribute</span></span>|<span data-ttu-id="aa93c-117">描述</span><span class="sxs-lookup"><span data-stu-id="aa93c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa93c-118">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="aa93c-118">customCertificateValidatorType</span></span>|<span data-ttu-id="aa93c-119">可选的字符串。</span><span class="sxs-lookup"><span data-stu-id="aa93c-119">Optional string.</span></span> <span data-ttu-id="aa93c-120">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="aa93c-120">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="aa93c-121">当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。</span><span class="sxs-lookup"><span data-stu-id="aa93c-121">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="aa93c-122">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="aa93c-122">certificateValidationMode</span></span>|<span data-ttu-id="aa93c-123">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="aa93c-123">Optional enumeration.</span></span> <span data-ttu-id="aa93c-124">指定用来验证凭据的其中一种模式。</span><span class="sxs-lookup"><span data-stu-id="aa93c-124">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="aa93c-125">此特性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="aa93c-125">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="aa93c-126">如果设置为 <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>，则还必须提供 `customCertificateValidator`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-126">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="aa93c-127">默认值为 <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="aa93c-127">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="aa93c-128">includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="aa93c-128">includeWindowsGroups</span></span>|<span data-ttu-id="aa93c-129">可选的布尔值。</span><span class="sxs-lookup"><span data-stu-id="aa93c-129">Optional Boolean.</span></span> <span data-ttu-id="aa93c-130">指定 Windows 组是否包含在安全上下文中。</span><span class="sxs-lookup"><span data-stu-id="aa93c-130">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="aa93c-131">将此属性设置为 `true` 会影响性能，因为这会导致完全组扩展。</span><span class="sxs-lookup"><span data-stu-id="aa93c-131">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="aa93c-132">如果不需要建立用户所属组的列表，请将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-132">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="aa93c-133">mapClientCertificateToWindowsAccount</span><span class="sxs-lookup"><span data-stu-id="aa93c-133">mapClientCertificateToWindowsAccount</span></span>|<span data-ttu-id="aa93c-134">布尔值。</span><span class="sxs-lookup"><span data-stu-id="aa93c-134">Boolean.</span></span> <span data-ttu-id="aa93c-135">指定是否可以使用证书将客户端映射到 Windows 标识。</span><span class="sxs-lookup"><span data-stu-id="aa93c-135">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="aa93c-136">为此，必须启用 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="aa93c-136">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="aa93c-137">revocationMode</span><span class="sxs-lookup"><span data-stu-id="aa93c-137">revocationMode</span></span>|<span data-ttu-id="aa93c-138">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="aa93c-138">Optional enumeration.</span></span> <span data-ttu-id="aa93c-139">用于检查吊销证书列表 (RCL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="aa93c-139">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="aa93c-140">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-140">The default is `Online`.</span></span> <span data-ttu-id="aa93c-141">使用 HTTP 传输安全性时，将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="aa93c-141">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="aa93c-142">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="aa93c-142">trustedStoreLocation</span></span>|<span data-ttu-id="aa93c-143">可选的枚举。</span><span class="sxs-lookup"><span data-stu-id="aa93c-143">Optional enumeration.</span></span> <span data-ttu-id="aa93c-144">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-144">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="aa93c-145">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="aa93c-145">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="aa93c-146">针对指定存储位置中的 "**受信任人**" 存储执行验证。</span><span class="sxs-lookup"><span data-stu-id="aa93c-146">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="aa93c-147">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-147">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="aa93c-148">customCertificateValidatorType 属性</span><span class="sxs-lookup"><span data-stu-id="aa93c-148">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="aa93c-149">值</span><span class="sxs-lookup"><span data-stu-id="aa93c-149">Value</span></span>|<span data-ttu-id="aa93c-150">描述</span><span class="sxs-lookup"><span data-stu-id="aa93c-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aa93c-151">String</span><span class="sxs-lookup"><span data-stu-id="aa93c-151">String</span></span>|<span data-ttu-id="aa93c-152">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="aa93c-152">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="aa93c-153">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="aa93c-153">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="aa93c-154">值</span><span class="sxs-lookup"><span data-stu-id="aa93c-154">Value</span></span>|<span data-ttu-id="aa93c-155">描述</span><span class="sxs-lookup"><span data-stu-id="aa93c-155">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aa93c-156">枚举</span><span class="sxs-lookup"><span data-stu-id="aa93c-156">Enumeration</span></span>|<span data-ttu-id="aa93c-157">以下值之一：None、PeerTrust、ChainTrust、PeerOrChainTrust、Custom。</span><span class="sxs-lookup"><span data-stu-id="aa93c-157">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="aa93c-158">有关详细信息，请参阅使用[证书](../../../wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="aa93c-158">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="aa93c-159">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="aa93c-159">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="aa93c-160">值</span><span class="sxs-lookup"><span data-stu-id="aa93c-160">Value</span></span>|<span data-ttu-id="aa93c-161">描述</span><span class="sxs-lookup"><span data-stu-id="aa93c-161">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aa93c-162">枚举</span><span class="sxs-lookup"><span data-stu-id="aa93c-162">Enumeration</span></span>|<span data-ttu-id="aa93c-163">以下值之一：NoCheck、联机、脱机。</span><span class="sxs-lookup"><span data-stu-id="aa93c-163">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="aa93c-164">有关详细信息，请参阅使用[证书](../../../wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="aa93c-164">For more information, see [Working with Certificates](../../../wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="aa93c-165">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="aa93c-165">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="aa93c-166">值</span><span class="sxs-lookup"><span data-stu-id="aa93c-166">Value</span></span>|<span data-ttu-id="aa93c-167">描述</span><span class="sxs-lookup"><span data-stu-id="aa93c-167">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aa93c-168">枚举</span><span class="sxs-lookup"><span data-stu-id="aa93c-168">Enumeration</span></span>|<span data-ttu-id="aa93c-169">下列值之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-169">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="aa93c-170">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-170">The default is `CurrentUser`.</span></span> <span data-ttu-id="aa93c-171">如果客户端应用程序在系统帐户下运行，则证书通常位于 `LocalMachine`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-171">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="aa93c-172">如果客户端应用程序在用户帐户下运行，则证书通常位于 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-172">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa93c-173">子元素</span><span class="sxs-lookup"><span data-stu-id="aa93c-173">Child Elements</span></span>  
 <span data-ttu-id="aa93c-174">无。</span><span class="sxs-lookup"><span data-stu-id="aa93c-174">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa93c-175">父元素</span><span class="sxs-lookup"><span data-stu-id="aa93c-175">Parent Elements</span></span>  
  
|<span data-ttu-id="aa93c-176">元素</span><span class="sxs-lookup"><span data-stu-id="aa93c-176">Element</span></span>|<span data-ttu-id="aa93c-177">描述</span><span class="sxs-lookup"><span data-stu-id="aa93c-177">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa93c-178">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="aa93c-178">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="aa93c-179">定义用于针对服务进行客户端身份验证的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="aa93c-179">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa93c-180">备注</span><span class="sxs-lookup"><span data-stu-id="aa93c-180">Remarks</span></span>  
 <span data-ttu-id="aa93c-181">`<authentication>` 元素与 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 类相对应。</span><span class="sxs-lookup"><span data-stu-id="aa93c-181">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="aa93c-182">利用它您可以自定义对客户端进行身份验证的方式。</span><span class="sxs-lookup"><span data-stu-id="aa93c-182">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="aa93c-183">可以将 `certificateValidationMode` 属性设置为 `None`、`ChainTrust`、`PeerOrChainTrust`、`PeerTrust` 或 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-183">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="aa93c-184">默认情况下，该级别设置为`ChainTrust`，它指定每个证书都必须位于证书层次结构中，以在链顶部以*根证书颁发机构*结束。</span><span class="sxs-lookup"><span data-stu-id="aa93c-184">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="aa93c-185">这是最安全的模式。</span><span class="sxs-lookup"><span data-stu-id="aa93c-185">This is the most secure mode.</span></span> <span data-ttu-id="aa93c-186">您还可以将此值设置为 `PeerOrChainTrust`，该值指定受信任的链中的证书以及自行颁发的证书（对等信任）都被接受。</span><span class="sxs-lookup"><span data-stu-id="aa93c-186">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="aa93c-187">因为不需要从受信任的证书颁发机构那里购买自行颁发的证书，所以可以在开发和调试客户端和服务时使用此值。</span><span class="sxs-lookup"><span data-stu-id="aa93c-187">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="aa93c-188">在部署客户端时，请改用 `ChainTrust` 值。</span><span class="sxs-lookup"><span data-stu-id="aa93c-188">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="aa93c-189">还可以将该值设置为 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="aa93c-189">You can also set the value to `Custom`.</span></span> <span data-ttu-id="aa93c-190">当该值设置为 `Custom` 值时，您还必须将 `customCertificateValidatorType` 属性设置为用于验证证书的程序集和类型。</span><span class="sxs-lookup"><span data-stu-id="aa93c-190">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="aa93c-191">若要创建您自己的自定义验证程序，必须从 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 抽象类进行继承。</span><span class="sxs-lookup"><span data-stu-id="aa93c-191">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="aa93c-192">有关详细信息，请参阅[如何：创建使用自定义证书验证](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)程序的服务。</span><span class="sxs-lookup"><span data-stu-id="aa93c-192">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa93c-193">示例</span><span class="sxs-lookup"><span data-stu-id="aa93c-193">Example</span></span>  
 <span data-ttu-id="aa93c-194">下面的代码指定 `<authentication>` 元素中的 X.509 证书和自定义验证类型。</span><span class="sxs-lookup"><span data-stu-id="aa93c-194">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa93c-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa93c-195">See also</span></span>

- <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>
- <xref:System.ServiceModel.Security.X509CertificateValidationMode>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>
- [<span data-ttu-id="aa93c-196">安全行为</span><span class="sxs-lookup"><span data-stu-id="aa93c-196">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="aa93c-197">如何：创建使用自定义证书验证程序的服务</span><span class="sxs-lookup"><span data-stu-id="aa93c-197">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="aa93c-198">使用证书</span><span class="sxs-lookup"><span data-stu-id="aa93c-198">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
