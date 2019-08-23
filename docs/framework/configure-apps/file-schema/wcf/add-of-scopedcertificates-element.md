---
title: <add>of <scopedCertificates>元素
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 9756d37527fcf888cad930b24677ae8e6a2c8fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920045"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="e0704-102">\<添加 scopedCertificates > \<元素的 ></span><span class="sxs-lookup"><span data-stu-id="e0704-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="e0704-103">向作用域证书集合添加 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e0704-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
 <span data-ttu-id="e0704-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e0704-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e0704-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e0704-105">\<behaviors></span></span>  
<span data-ttu-id="e0704-106">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="e0704-106">endpointBehaviors section</span></span>  
<span data-ttu-id="e0704-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e0704-107">\<behavior></span></span>  
<span data-ttu-id="e0704-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e0704-108">\<clientCredentials></span></span>  
<span data-ttu-id="e0704-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e0704-109">\<serviceCertificate></span></span>  
<span data-ttu-id="e0704-110">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="e0704-110">\<scopedCertificates></span></span>  
<span data-ttu-id="e0704-111">\<添加 scopedCertificates 的\<> 元素 ></span><span class="sxs-lookup"><span data-stu-id="e0704-111">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0704-112">语法</span><span class="sxs-lookup"><span data-stu-id="e0704-112">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0704-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e0704-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e0704-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e0704-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0704-115">特性</span><span class="sxs-lookup"><span data-stu-id="e0704-115">Attributes</span></span>  
  
|<span data-ttu-id="e0704-116">特性</span><span class="sxs-lookup"><span data-stu-id="e0704-116">Attribute</span></span>|<span data-ttu-id="e0704-117">描述</span><span class="sxs-lookup"><span data-stu-id="e0704-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0704-118">targetUri</span><span class="sxs-lookup"><span data-stu-id="e0704-118">targetUri</span></span>|<span data-ttu-id="e0704-119">字符串。</span><span class="sxs-lookup"><span data-stu-id="e0704-119">String.</span></span> <span data-ttu-id="e0704-120">指定与证书相关的服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="e0704-120">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="e0704-121">findValue</span><span class="sxs-lookup"><span data-stu-id="e0704-121">findValue</span></span>|<span data-ttu-id="e0704-122">字符串。</span><span class="sxs-lookup"><span data-stu-id="e0704-122">String.</span></span> <span data-ttu-id="e0704-123">要搜索的值。</span><span class="sxs-lookup"><span data-stu-id="e0704-123">The value to search for.</span></span>|  
|<span data-ttu-id="e0704-124">x509FindType</span><span class="sxs-lookup"><span data-stu-id="e0704-124">x509FindType</span></span>|<span data-ttu-id="e0704-125">枚举。</span><span class="sxs-lookup"><span data-stu-id="e0704-125">Enumeration.</span></span> <span data-ttu-id="e0704-126">要搜索的证书字段之一。</span><span class="sxs-lookup"><span data-stu-id="e0704-126">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="e0704-127">storeLocation</span><span class="sxs-lookup"><span data-stu-id="e0704-127">storeLocation</span></span>|<span data-ttu-id="e0704-128">枚举。</span><span class="sxs-lookup"><span data-stu-id="e0704-128">Enumeration.</span></span> <span data-ttu-id="e0704-129">要搜索的两个存储位置之一。</span><span class="sxs-lookup"><span data-stu-id="e0704-129">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="e0704-130">storeName</span><span class="sxs-lookup"><span data-stu-id="e0704-130">storeName</span></span>|<span data-ttu-id="e0704-131">枚举。</span><span class="sxs-lookup"><span data-stu-id="e0704-131">Enumeration.</span></span> <span data-ttu-id="e0704-132">要搜索的系统存储之一。</span><span class="sxs-lookup"><span data-stu-id="e0704-132">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="e0704-133">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="e0704-133">findValue Attribute</span></span>  
  
|<span data-ttu-id="e0704-134">值</span><span class="sxs-lookup"><span data-stu-id="e0704-134">Value</span></span>|<span data-ttu-id="e0704-135">描述</span><span class="sxs-lookup"><span data-stu-id="e0704-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0704-136">String</span><span class="sxs-lookup"><span data-stu-id="e0704-136">String</span></span>|<span data-ttu-id="e0704-137">值取决于搜索的字段（由 X509FindType 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="e0704-137">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="e0704-138">例如，如果搜索指纹，则此值必须为十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="e0704-138">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="e0704-139">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="e0704-139">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="e0704-140">值</span><span class="sxs-lookup"><span data-stu-id="e0704-140">Value</span></span>|<span data-ttu-id="e0704-141">描述</span><span class="sxs-lookup"><span data-stu-id="e0704-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0704-142">枚举</span><span class="sxs-lookup"><span data-stu-id="e0704-142">Enumeration</span></span>|<span data-ttu-id="e0704-143">值包括：FindByThumbprint、Findbysubjectname)、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="e0704-143">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="e0704-144">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="e0704-144">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="e0704-145">值</span><span class="sxs-lookup"><span data-stu-id="e0704-145">Value</span></span>|<span data-ttu-id="e0704-146">描述</span><span class="sxs-lookup"><span data-stu-id="e0704-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0704-147">枚举</span><span class="sxs-lookup"><span data-stu-id="e0704-147">Enumeration</span></span>|<span data-ttu-id="e0704-148">CurrentUser 或 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="e0704-148">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="e0704-149">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="e0704-149">storeName Attribute</span></span>  
  
|<span data-ttu-id="e0704-150">值</span><span class="sxs-lookup"><span data-stu-id="e0704-150">Value</span></span>|<span data-ttu-id="e0704-151">描述</span><span class="sxs-lookup"><span data-stu-id="e0704-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e0704-152">枚举</span><span class="sxs-lookup"><span data-stu-id="e0704-152">Enumeration</span></span>|<span data-ttu-id="e0704-153">值包括：通讯簿、AuthRoot、CertificateAuthority、不允许、My、Root、TrustedPeople 和 TrustedPublisher。</span><span class="sxs-lookup"><span data-stu-id="e0704-153">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0704-154">子元素</span><span class="sxs-lookup"><span data-stu-id="e0704-154">Child Elements</span></span>  
 <span data-ttu-id="e0704-155">无。</span><span class="sxs-lookup"><span data-stu-id="e0704-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0704-156">父元素</span><span class="sxs-lookup"><span data-stu-id="e0704-156">Parent Elements</span></span>  
  
|<span data-ttu-id="e0704-157">元素</span><span class="sxs-lookup"><span data-stu-id="e0704-157">Element</span></span>|<span data-ttu-id="e0704-158">描述</span><span class="sxs-lookup"><span data-stu-id="e0704-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0704-159">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="e0704-159">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="e0704-160">表示特定服务为身份验证提供的 X.509（作用域）证书的集合。</span><span class="sxs-lookup"><span data-stu-id="e0704-160">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0704-161">备注</span><span class="sxs-lookup"><span data-stu-id="e0704-161">Remarks</span></span>  
 <span data-ttu-id="e0704-162">此元素使客户端能够根据与它通信的服务的 URL 来配置要使用的服务证书。</span><span class="sxs-lookup"><span data-stu-id="e0704-162">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="e0704-163">这在已颁发令牌的方案中尤其有用，在这些方案中，客户端可与多个服务（终端服务以及中间的安全令牌服务）进行通信。</span><span class="sxs-lookup"><span data-stu-id="e0704-163">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="e0704-164">对于使用基于证书的消息安全的绑定，此证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="e0704-164">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="e0704-165">如果绑定需要服务的证书，但在 ScopedCertificates 中未找到服务 URL 的特定证书，则使用默认证书。</span><span class="sxs-lookup"><span data-stu-id="e0704-165">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="e0704-166">有关详细信息, 请参阅[如何:创建联合客户端](../../../wcf/feature-details/how-to-create-a-federated-client.md)。</span><span class="sxs-lookup"><span data-stu-id="e0704-166">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0704-167">示例</span><span class="sxs-lookup"><span data-stu-id="e0704-167">Example</span></span>  
 <span data-ttu-id="e0704-168">下面的示例向集合中添加一个 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e0704-168">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0704-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0704-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="e0704-170">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="e0704-170">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="e0704-171">使用证书</span><span class="sxs-lookup"><span data-stu-id="e0704-171">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="e0704-172">保护客户端</span><span class="sxs-lookup"><span data-stu-id="e0704-172">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="e0704-173">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="e0704-173">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
