---
title: <add>of <scopedCertificates>元素
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398346"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="5b6ef-102">\<添加 scopedCertificates > \<元素的 ></span><span class="sxs-lookup"><span data-stu-id="5b6ef-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="5b6ef-103">向作用域证书集合添加 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
<span data-ttu-id="5b6ef-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ef-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5b6ef-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ef-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5b6ef-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ef-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5b6ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ef-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="5b6ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ef-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="5b6ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ef-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="5b6ef-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ef-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="5b6ef-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<scopedCertificates >** ](scopedcertificates-element.md)</span><span class="sxs-lookup"><span data-stu-id="5b6ef-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)</span></span>\
<span data-ttu-id="5b6ef-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="5b6ef-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6ef-113">语法</span><span class="sxs-lookup"><span data-stu-id="5b6ef-113">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b6ef-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5b6ef-114">Attributes and Elements</span></span>  
 <span data-ttu-id="5b6ef-115">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b6ef-116">特性</span><span class="sxs-lookup"><span data-stu-id="5b6ef-116">Attributes</span></span>  
  
|<span data-ttu-id="5b6ef-117">特性</span><span class="sxs-lookup"><span data-stu-id="5b6ef-117">Attribute</span></span>|<span data-ttu-id="5b6ef-118">描述</span><span class="sxs-lookup"><span data-stu-id="5b6ef-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b6ef-119">targetUri</span><span class="sxs-lookup"><span data-stu-id="5b6ef-119">targetUri</span></span>|<span data-ttu-id="5b6ef-120">字符串。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-120">String.</span></span> <span data-ttu-id="5b6ef-121">指定与证书相关的服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-121">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="5b6ef-122">findValue</span><span class="sxs-lookup"><span data-stu-id="5b6ef-122">findValue</span></span>|<span data-ttu-id="5b6ef-123">字符串。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-123">String.</span></span> <span data-ttu-id="5b6ef-124">要搜索的值。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-124">The value to search for.</span></span>|  
|<span data-ttu-id="5b6ef-125">x509FindType</span><span class="sxs-lookup"><span data-stu-id="5b6ef-125">x509FindType</span></span>|<span data-ttu-id="5b6ef-126">枚举。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-126">Enumeration.</span></span> <span data-ttu-id="5b6ef-127">要搜索的证书字段之一。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-127">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="5b6ef-128">storeLocation</span><span class="sxs-lookup"><span data-stu-id="5b6ef-128">storeLocation</span></span>|<span data-ttu-id="5b6ef-129">枚举。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-129">Enumeration.</span></span> <span data-ttu-id="5b6ef-130">要搜索的两个存储位置之一。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-130">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="5b6ef-131">storeName</span><span class="sxs-lookup"><span data-stu-id="5b6ef-131">storeName</span></span>|<span data-ttu-id="5b6ef-132">枚举。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-132">Enumeration.</span></span> <span data-ttu-id="5b6ef-133">要搜索的系统存储之一。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-133">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="5b6ef-134">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="5b6ef-134">findValue Attribute</span></span>  
  
|<span data-ttu-id="5b6ef-135">值</span><span class="sxs-lookup"><span data-stu-id="5b6ef-135">Value</span></span>|<span data-ttu-id="5b6ef-136">描述</span><span class="sxs-lookup"><span data-stu-id="5b6ef-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b6ef-137">String</span><span class="sxs-lookup"><span data-stu-id="5b6ef-137">String</span></span>|<span data-ttu-id="5b6ef-138">值取决于搜索的字段（由 X509FindType 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-138">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="5b6ef-139">例如，如果搜索指纹，则此值必须为十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-139">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="5b6ef-140">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="5b6ef-140">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="5b6ef-141">值</span><span class="sxs-lookup"><span data-stu-id="5b6ef-141">Value</span></span>|<span data-ttu-id="5b6ef-142">描述</span><span class="sxs-lookup"><span data-stu-id="5b6ef-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b6ef-143">枚举</span><span class="sxs-lookup"><span data-stu-id="5b6ef-143">Enumeration</span></span>|<span data-ttu-id="5b6ef-144">值包括：FindByThumbprint、Findbysubjectname)、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="5b6ef-144">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="5b6ef-145">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="5b6ef-145">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="5b6ef-146">值</span><span class="sxs-lookup"><span data-stu-id="5b6ef-146">Value</span></span>|<span data-ttu-id="5b6ef-147">描述</span><span class="sxs-lookup"><span data-stu-id="5b6ef-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b6ef-148">枚举</span><span class="sxs-lookup"><span data-stu-id="5b6ef-148">Enumeration</span></span>|<span data-ttu-id="5b6ef-149">CurrentUser 或 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-149">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="5b6ef-150">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="5b6ef-150">storeName Attribute</span></span>  
  
|<span data-ttu-id="5b6ef-151">值</span><span class="sxs-lookup"><span data-stu-id="5b6ef-151">Value</span></span>|<span data-ttu-id="5b6ef-152">描述</span><span class="sxs-lookup"><span data-stu-id="5b6ef-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b6ef-153">枚举</span><span class="sxs-lookup"><span data-stu-id="5b6ef-153">Enumeration</span></span>|<span data-ttu-id="5b6ef-154">值包括：通讯簿、AuthRoot、CertificateAuthority、不允许、My、Root、TrustedPeople 和 TrustedPublisher。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-154">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b6ef-155">子元素</span><span class="sxs-lookup"><span data-stu-id="5b6ef-155">Child Elements</span></span>  
 <span data-ttu-id="5b6ef-156">无。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b6ef-157">父元素</span><span class="sxs-lookup"><span data-stu-id="5b6ef-157">Parent Elements</span></span>  
  
|<span data-ttu-id="5b6ef-158">元素</span><span class="sxs-lookup"><span data-stu-id="5b6ef-158">Element</span></span>|<span data-ttu-id="5b6ef-159">描述</span><span class="sxs-lookup"><span data-stu-id="5b6ef-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b6ef-160">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="5b6ef-160">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="5b6ef-161">表示特定服务为身份验证提供的 X.509（作用域）证书的集合。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-161">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b6ef-162">备注</span><span class="sxs-lookup"><span data-stu-id="5b6ef-162">Remarks</span></span>  
 <span data-ttu-id="5b6ef-163">此元素使客户端能够根据与它通信的服务的 URL 来配置要使用的服务证书。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-163">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="5b6ef-164">这在已颁发令牌的方案中尤其有用，在这些方案中，客户端可与多个服务（终端服务以及中间的安全令牌服务）进行通信。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-164">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="5b6ef-165">对于使用基于证书的消息安全的绑定，此证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-165">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="5b6ef-166">如果绑定需要服务的证书，但在 ScopedCertificates 中未找到服务 URL 的特定证书，则使用默认证书。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-166">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="5b6ef-167">有关详细信息，请参阅[如何：创建联合客户端](../../../wcf/feature-details/how-to-create-a-federated-client.md)。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-167">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b6ef-168">示例</span><span class="sxs-lookup"><span data-stu-id="5b6ef-168">Example</span></span>  
 <span data-ttu-id="5b6ef-169">下面的示例向集合中添加一个 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="5b6ef-169">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="5b6ef-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b6ef-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="5b6ef-171">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="5b6ef-171">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="5b6ef-172">使用证书</span><span class="sxs-lookup"><span data-stu-id="5b6ef-172">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="5b6ef-173">保护客户端</span><span class="sxs-lookup"><span data-stu-id="5b6ef-173">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="5b6ef-174">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="5b6ef-174">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
