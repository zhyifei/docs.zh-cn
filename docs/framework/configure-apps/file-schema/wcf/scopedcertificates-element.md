---
title: <scopedCertificates> 元素
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: ed53a42575a8d57c365f7a329a1a9c1df075d6d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935220"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="1a817-102">\<scopedCertificates > 元素</span><span class="sxs-lookup"><span data-stu-id="1a817-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="1a817-103">表示特定服务为身份验证提供的 X.509（作用域）证书的集合。</span><span class="sxs-lookup"><span data-stu-id="1a817-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="1a817-104">此集合通常用于指定联合方案中安全令牌服务的服务证书。</span><span class="sxs-lookup"><span data-stu-id="1a817-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="1a817-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1a817-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1a817-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1a817-106">\<behaviors></span></span>  
<span data-ttu-id="1a817-107">endpointBehaviors 部分</span><span class="sxs-lookup"><span data-stu-id="1a817-107">endpointBehaviors section</span></span>  
<span data-ttu-id="1a817-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1a817-108">\<behavior></span></span>  
<span data-ttu-id="1a817-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="1a817-109">\<clientCredentials></span></span>  
<span data-ttu-id="1a817-110">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="1a817-110">\<serviceCertificate></span></span>  
<span data-ttu-id="1a817-111">\<scopedCertificates > 元素</span><span class="sxs-lookup"><span data-stu-id="1a817-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="1a817-112">\<添加 scopedCertificates 的\<> 元素 ></span><span class="sxs-lookup"><span data-stu-id="1a817-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a817-113">语法</span><span class="sxs-lookup"><span data-stu-id="1a817-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a817-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1a817-114">Attributes and Elements</span></span>  
 <span data-ttu-id="1a817-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1a817-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a817-116">特性</span><span class="sxs-lookup"><span data-stu-id="1a817-116">Attributes</span></span>  
 <span data-ttu-id="1a817-117">无。</span><span class="sxs-lookup"><span data-stu-id="1a817-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1a817-118">子元素</span><span class="sxs-lookup"><span data-stu-id="1a817-118">Child Elements</span></span>  
  
|<span data-ttu-id="1a817-119">元素</span><span class="sxs-lookup"><span data-stu-id="1a817-119">Element</span></span>|<span data-ttu-id="1a817-120">描述</span><span class="sxs-lookup"><span data-stu-id="1a817-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a817-121">\<add></span><span class="sxs-lookup"><span data-stu-id="1a817-121">\<add></span></span>](add-of-scopedcertificates-element.md)|<span data-ttu-id="1a817-122">向作用域证书集合添加 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="1a817-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a817-123">父元素</span><span class="sxs-lookup"><span data-stu-id="1a817-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1a817-124">元素</span><span class="sxs-lookup"><span data-stu-id="1a817-124">Element</span></span>|<span data-ttu-id="1a817-125">描述</span><span class="sxs-lookup"><span data-stu-id="1a817-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a817-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="1a817-126">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="1a817-127">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="1a817-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a817-128">备注</span><span class="sxs-lookup"><span data-stu-id="1a817-128">Remarks</span></span>  
 <span data-ttu-id="1a817-129">此集合使客户端能够根据与它通信的服务的 URL 来配置要使用的服务证书。</span><span class="sxs-lookup"><span data-stu-id="1a817-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="1a817-130">这在已颁发令牌的方案中尤其有用，在这些方案中，客户端可与多个服务（终端服务以及中间的安全令牌服务）进行通信。</span><span class="sxs-lookup"><span data-stu-id="1a817-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="1a817-131">对于使用基于证书的消息安全的绑定，此证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="1a817-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="1a817-132">如果绑定需要服务的证书，但在 ScopedCertificates 中未找到服务 URL 的特定证书，则使用默认证书。</span><span class="sxs-lookup"><span data-stu-id="1a817-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="1a817-133">有关详细信息, 请参阅[如何:创建联合客户端](../../../wcf/feature-details/how-to-create-a-federated-client.md)。</span><span class="sxs-lookup"><span data-stu-id="1a817-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a817-134">示例</span><span class="sxs-lookup"><span data-stu-id="1a817-134">Example</span></span>  
 <span data-ttu-id="1a817-135">下面的示例指定客户端在其域名与终结点进行通信时要使用的服务证书 `http://www.contoso.com` 通过 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="1a817-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="1a817-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a817-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="1a817-137">使用证书</span><span class="sxs-lookup"><span data-stu-id="1a817-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1a817-138">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="1a817-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="1a817-139">\<add></span><span class="sxs-lookup"><span data-stu-id="1a817-139">\<add></span></span>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="1a817-140">保护客户端</span><span class="sxs-lookup"><span data-stu-id="1a817-140">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="1a817-141">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="1a817-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
