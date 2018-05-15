---
title: '&lt;scopedCertificates&gt; 元素'
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: d95e608fa9b94086dac72341eb599f258dae6097
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltscopedcertificatesgt-element"></a><span data-ttu-id="9937d-102">&lt;scopedCertificates&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="9937d-102">&lt;scopedCertificates&gt; Element</span></span>
<span data-ttu-id="9937d-103">表示特定服务为身份验证提供的 X.509（作用域）证书的集合。</span><span class="sxs-lookup"><span data-stu-id="9937d-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="9937d-104">此集合通常用于指定联合方案中安全令牌服务的服务证书。</span><span class="sxs-lookup"><span data-stu-id="9937d-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="9937d-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9937d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9937d-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9937d-106">\<behaviors></span></span>  
<span data-ttu-id="9937d-107">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="9937d-107">endpointBehaviors section</span></span>  
<span data-ttu-id="9937d-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9937d-108">\<behavior></span></span>  
<span data-ttu-id="9937d-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="9937d-109">\<clientCredentials></span></span>  
<span data-ttu-id="9937d-110">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="9937d-110">\<serviceCertificate></span></span>  
<span data-ttu-id="9937d-111">\<scopedCertificates > 元素</span><span class="sxs-lookup"><span data-stu-id="9937d-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="9937d-112">\<添加 > 元素\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="9937d-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9937d-113">语法</span><span class="sxs-lookup"><span data-stu-id="9937d-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>  
      <add findValue="String"  
                storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                targetUri="string"  
            x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />   
</scopedCertificates>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9937d-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9937d-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9937d-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9937d-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9937d-116">特性</span><span class="sxs-lookup"><span data-stu-id="9937d-116">Attributes</span></span>  
 <span data-ttu-id="9937d-117">无。</span><span class="sxs-lookup"><span data-stu-id="9937d-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9937d-118">子元素</span><span class="sxs-lookup"><span data-stu-id="9937d-118">Child Elements</span></span>  
  
|<span data-ttu-id="9937d-119">元素</span><span class="sxs-lookup"><span data-stu-id="9937d-119">Element</span></span>|<span data-ttu-id="9937d-120">描述</span><span class="sxs-lookup"><span data-stu-id="9937d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9937d-121">\<add></span><span class="sxs-lookup"><span data-stu-id="9937d-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|<span data-ttu-id="9937d-122">向作用域证书集合添加 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="9937d-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9937d-123">父元素</span><span class="sxs-lookup"><span data-stu-id="9937d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9937d-124">元素</span><span class="sxs-lookup"><span data-stu-id="9937d-124">Element</span></span>|<span data-ttu-id="9937d-125">描述</span><span class="sxs-lookup"><span data-stu-id="9937d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9937d-126">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="9937d-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="9937d-127">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="9937d-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9937d-128">备注</span><span class="sxs-lookup"><span data-stu-id="9937d-128">Remarks</span></span>  
 <span data-ttu-id="9937d-129">此集合使客户端能够根据与它通信的服务的 URL 来配置要使用的服务证书。</span><span class="sxs-lookup"><span data-stu-id="9937d-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="9937d-130">这在已颁发令牌的方案中尤其有用，在这些方案中，客户端可与多个服务（终端服务以及中间的安全令牌服务）进行通信。</span><span class="sxs-lookup"><span data-stu-id="9937d-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="9937d-131">对于使用基于证书的消息安全的绑定，此证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="9937d-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="9937d-132">如果绑定需要服务的证书，但在 ScopedCertificates 中未找到服务 URL 的特定证书，则使用默认证书。</span><span class="sxs-lookup"><span data-stu-id="9937d-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="9937d-133">有关详细信息，请参阅的"作用域证书"部分[如何： 创建联合客户端](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)。</span><span class="sxs-lookup"><span data-stu-id="9937d-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9937d-134">示例</span><span class="sxs-lookup"><span data-stu-id="9937d-134">Example</span></span>  
 <span data-ttu-id="9937d-135">下面的示例指定客户端在其域名与终结点进行通信时要使用的服务证书http://www.contoso.com通过 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="9937d-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is http://www.contoso.com over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9937d-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="9937d-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [<span data-ttu-id="9937d-137">使用证书</span><span class="sxs-lookup"><span data-stu-id="9937d-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="9937d-138">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="9937d-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="9937d-139">\<add></span><span class="sxs-lookup"><span data-stu-id="9937d-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)  
 [<span data-ttu-id="9937d-140">保护客户端</span><span class="sxs-lookup"><span data-stu-id="9937d-140">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="9937d-141">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="9937d-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
