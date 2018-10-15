---
title: '&lt;serviceCertificate&gt; 的 &lt;authentication&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 811d54b49d8cd4fddbf196dbb524c5d303805c4f
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316449"
---
# <a name="ltauthenticationgt-of-ltservicecertificategt-element"></a><span data-ttu-id="fa877-102">&lt;serviceCertificate&gt; 的 &lt;authentication&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="fa877-102">&lt;authentication&gt; of &lt;serviceCertificate&gt; Element</span></span>
<span data-ttu-id="fa877-103">指定客户端代理用于对使用 SSL/TLS 协商获取的服务证书进行身份验证的设置。</span><span class="sxs-lookup"><span data-stu-id="fa877-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="fa877-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fa877-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa877-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="fa877-105">\<behaviors></span></span>  
<span data-ttu-id="fa877-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="fa877-106">endpointBehaviors section</span></span>  
<span data-ttu-id="fa877-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="fa877-107">\<behavior></span></span>  
<span data-ttu-id="fa877-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="fa877-108">\<clientCredentials></span></span>  
<span data-ttu-id="fa877-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="fa877-109">\<serviceCertificate></span></span>  
<span data-ttu-id="fa877-110">\<身份验证 ></span><span class="sxs-lookup"><span data-stu-id="fa877-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa877-111">语法</span><span class="sxs-lookup"><span data-stu-id="fa877-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String" certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"   
trustedStoreLocation="LocalMachine/CurrentUser" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa877-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fa877-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fa877-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fa877-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa877-114">特性</span><span class="sxs-lookup"><span data-stu-id="fa877-114">Attributes</span></span>  
  
|<span data-ttu-id="fa877-115">特性</span><span class="sxs-lookup"><span data-stu-id="fa877-115">Attribute</span></span>|<span data-ttu-id="fa877-116">描述</span><span class="sxs-lookup"><span data-stu-id="fa877-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa877-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="fa877-117">customCertificateValidatorType</span></span>|<span data-ttu-id="fa877-118">字符串。</span><span class="sxs-lookup"><span data-stu-id="fa877-118">String.</span></span> <span data-ttu-id="fa877-119">一个用于验证自定义类型的类型和程序集。</span><span class="sxs-lookup"><span data-stu-id="fa877-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="fa877-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="fa877-120">certificateValidationMode</span></span>|<span data-ttu-id="fa877-121">指定用来验证凭据的三种模式之一。</span><span class="sxs-lookup"><span data-stu-id="fa877-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="fa877-122">如果设置为 `Custom`，则还必须提供 customCertificateValidator。</span><span class="sxs-lookup"><span data-stu-id="fa877-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="fa877-123">默认值为 `ChainTrust`。</span><span class="sxs-lookup"><span data-stu-id="fa877-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="fa877-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="fa877-124">revocationMode</span></span>|<span data-ttu-id="fa877-125">用于检查吊销证书列表 (CRL) 的一种模式。</span><span class="sxs-lookup"><span data-stu-id="fa877-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="fa877-126">默认值为 `Online`。</span><span class="sxs-lookup"><span data-stu-id="fa877-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="fa877-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="fa877-127">trustedStoreLocation</span></span>|<span data-ttu-id="fa877-128">两个系统存储位置之一：`LocalMachine` 或 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="fa877-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="fa877-129">在向客户端协商服务证书时使用此值。</span><span class="sxs-lookup"><span data-stu-id="fa877-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="fa877-130">对执行验证**受信任的人员**将存储在指定的存储位置。</span><span class="sxs-lookup"><span data-stu-id="fa877-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="fa877-131">默认值为 `CurrentUser`。</span><span class="sxs-lookup"><span data-stu-id="fa877-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="fa877-132">customCertificateValidator 属性</span><span class="sxs-lookup"><span data-stu-id="fa877-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="fa877-133">值</span><span class="sxs-lookup"><span data-stu-id="fa877-133">Value</span></span>|<span data-ttu-id="fa877-134">描述</span><span class="sxs-lookup"><span data-stu-id="fa877-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa877-135">String</span><span class="sxs-lookup"><span data-stu-id="fa877-135">String</span></span>|<span data-ttu-id="fa877-136">指定类型名称和程序集以及用于查找类型的其他数据。</span><span class="sxs-lookup"><span data-stu-id="fa877-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="fa877-137">certificateValidationMode 属性</span><span class="sxs-lookup"><span data-stu-id="fa877-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="fa877-138">值</span><span class="sxs-lookup"><span data-stu-id="fa877-138">Value</span></span>|<span data-ttu-id="fa877-139">描述</span><span class="sxs-lookup"><span data-stu-id="fa877-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa877-140">枚举</span><span class="sxs-lookup"><span data-stu-id="fa877-140">Enumeration</span></span>|<span data-ttu-id="fa877-141">下列值之一：None、PeerTrust、ChainTrust、PeerOrChainTrust 和 Custom。</span><span class="sxs-lookup"><span data-stu-id="fa877-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="fa877-142">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="fa877-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="fa877-143">revocationMode 属性</span><span class="sxs-lookup"><span data-stu-id="fa877-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="fa877-144">值</span><span class="sxs-lookup"><span data-stu-id="fa877-144">Value</span></span>|<span data-ttu-id="fa877-145">描述</span><span class="sxs-lookup"><span data-stu-id="fa877-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa877-146">枚举</span><span class="sxs-lookup"><span data-stu-id="fa877-146">Enumeration</span></span>|<span data-ttu-id="fa877-147">下列值之一：NoCheck、Online 和 Offline。</span><span class="sxs-lookup"><span data-stu-id="fa877-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="fa877-148">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="fa877-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="fa877-149">trustedStoreLocation 属性</span><span class="sxs-lookup"><span data-stu-id="fa877-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="fa877-150">值</span><span class="sxs-lookup"><span data-stu-id="fa877-150">Value</span></span>|<span data-ttu-id="fa877-151">描述</span><span class="sxs-lookup"><span data-stu-id="fa877-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa877-152">枚举</span><span class="sxs-lookup"><span data-stu-id="fa877-152">Enumeration</span></span>|<span data-ttu-id="fa877-153">下列值之一：LocalMachine 或 CurrentUser。</span><span class="sxs-lookup"><span data-stu-id="fa877-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="fa877-154">默认值为 CurrentUser。</span><span class="sxs-lookup"><span data-stu-id="fa877-154">The default is CurrentUser.</span></span> <span data-ttu-id="fa877-155">如果客户端应用程序在系统帐户下运行，则证书通常位于 LocalMachine 中。</span><span class="sxs-lookup"><span data-stu-id="fa877-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="fa877-156">如果客户端应用程序在用户帐户下运行，则证书通常位于 CurrentUser 中。</span><span class="sxs-lookup"><span data-stu-id="fa877-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa877-157">子元素</span><span class="sxs-lookup"><span data-stu-id="fa877-157">Child Elements</span></span>  
 <span data-ttu-id="fa877-158">无。</span><span class="sxs-lookup"><span data-stu-id="fa877-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa877-159">父元素</span><span class="sxs-lookup"><span data-stu-id="fa877-159">Parent Elements</span></span>  
  
|<span data-ttu-id="fa877-160">元素</span><span class="sxs-lookup"><span data-stu-id="fa877-160">Element</span></span>|<span data-ttu-id="fa877-161">描述</span><span class="sxs-lookup"><span data-stu-id="fa877-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa877-162">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="fa877-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="fa877-163">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="fa877-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa877-164">备注</span><span class="sxs-lookup"><span data-stu-id="fa877-164">Remarks</span></span>  
 <span data-ttu-id="fa877-165">此配置元素的 `certificateValidationMode` 属性指定用于对证书进行身份验证的信任级别。</span><span class="sxs-lookup"><span data-stu-id="fa877-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="fa877-166">默认情况下，该级别设置为 `ChainTrust`，它指定每个证书都必须存在于某个证书层次结构中，而该层次结构以位于证书链顶端的受信任的证书颁发机构结束。</span><span class="sxs-lookup"><span data-stu-id="fa877-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="fa877-167">这是最安全的模式。</span><span class="sxs-lookup"><span data-stu-id="fa877-167">This is the most secure mode.</span></span> <span data-ttu-id="fa877-168">您还可以将此值设置为 `PeerOrChainTrust`，该值指定受信任的链中的证书以及自行颁发的证书（对等信任）都被接受。</span><span class="sxs-lookup"><span data-stu-id="fa877-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="fa877-169">因为不需要从受信任的证书颁发机构那里购买自行颁发的证书，所以可以在开发和调试客户端和服务时使用此值。</span><span class="sxs-lookup"><span data-stu-id="fa877-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="fa877-170">在部署客户端时，请改用 `ChainTrust` 值。</span><span class="sxs-lookup"><span data-stu-id="fa877-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="fa877-171">您也可以将该值设置为 `Custom` 或 `None`。</span><span class="sxs-lookup"><span data-stu-id="fa877-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="fa877-172">若要使用 `Custom` 值，还必须将 `customCertificateValidator` 属性设置为程序集和用于验证证书的类型。</span><span class="sxs-lookup"><span data-stu-id="fa877-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="fa877-173">若要创建您自己的自定义验证程序，必须从 X509CertificateValidator 抽象类进行继承。</span><span class="sxs-lookup"><span data-stu-id="fa877-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="fa877-174">有关详细信息，请参阅[如何： 创建使用自定义证书验证程序的服务](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)。</span><span class="sxs-lookup"><span data-stu-id="fa877-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="fa877-175">`revocationMode` 属性指定检查证书是否已吊销的方式。</span><span class="sxs-lookup"><span data-stu-id="fa877-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="fa877-176">默认值为 `online`，指示将自动检查证书是否已吊销。</span><span class="sxs-lookup"><span data-stu-id="fa877-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="fa877-177">有关详细信息，请参阅[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="fa877-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa877-178">示例</span><span class="sxs-lookup"><span data-stu-id="fa877-178">Example</span></span>  
 <span data-ttu-id="fa877-179">以下示例执行两项任务。</span><span class="sxs-lookup"><span data-stu-id="fa877-179">The following example does two tasks.</span></span> <span data-ttu-id="fa877-180">它首先指定客户端使用其域名与终结点进行通信时所使用的服务证书`www.contoso.com`通过 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="fa877-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is `www.contoso.com` over the HTTP protocol.</span></span> <span data-ttu-id="fa877-181">然后，它指定了在身份验证过程中使用的吊销模式和存储位置。</span><span class="sxs-lookup"><span data-stu-id="fa877-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa877-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa877-182">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>  
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>  
 [<span data-ttu-id="fa877-183">安全行为</span><span class="sxs-lookup"><span data-stu-id="fa877-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="fa877-184">使用证书</span><span class="sxs-lookup"><span data-stu-id="fa877-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="fa877-185">如何：创建使用自定义证书验证程序的服务</span><span class="sxs-lookup"><span data-stu-id="fa877-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="fa877-186">\<authentication></span><span class="sxs-lookup"><span data-stu-id="fa877-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="fa877-187">保护客户端</span><span class="sxs-lookup"><span data-stu-id="fa877-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="fa877-188">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="fa877-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
