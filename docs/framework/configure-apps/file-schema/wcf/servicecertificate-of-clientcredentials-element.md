---
title: <serviceCertificate> <clientCredentials>元素
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4fe196ef8737c7abde939e36c2bb7afd5a0d86b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145335"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="74533-102">\<serviceCertificate > 的\<clientCredentials > 元素</span><span class="sxs-lookup"><span data-stu-id="74533-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="74533-103">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="74533-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
 <span data-ttu-id="74533-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="74533-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="74533-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="74533-105">\<behaviors></span></span>  
<span data-ttu-id="74533-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="74533-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="74533-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="74533-107">\<behavior></span></span>  
<span data-ttu-id="74533-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="74533-108">\<clientCredentials></span></span>  
<span data-ttu-id="74533-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="74533-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74533-110">语法</span><span class="sxs-lookup"><span data-stu-id="74533-110">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74533-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="74533-111">Attributes and Elements</span></span>  
 <span data-ttu-id="74533-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="74533-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74533-113">特性</span><span class="sxs-lookup"><span data-stu-id="74533-113">Attributes</span></span>  
 <span data-ttu-id="74533-114">无。</span><span class="sxs-lookup"><span data-stu-id="74533-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="74533-115">子元素</span><span class="sxs-lookup"><span data-stu-id="74533-115">Child Elements</span></span>  
  
|<span data-ttu-id="74533-116">元素</span><span class="sxs-lookup"><span data-stu-id="74533-116">Element</span></span>|<span data-ttu-id="74533-117">描述</span><span class="sxs-lookup"><span data-stu-id="74533-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74533-118">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="74533-118">\<defaultCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|<span data-ttu-id="74533-119">指定在服务或 STS 未通过协商协议提供证书时要使用的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="74533-119">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="74533-120">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="74533-120">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="74533-121">表示特定服务为身份验证提供的 X.509（作用域）证书的集合。</span><span class="sxs-lookup"><span data-stu-id="74533-121">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="74533-122">此集合通常用于指定联合方案中安全令牌服务的服务证书。</span><span class="sxs-lookup"><span data-stu-id="74533-122">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="74533-123">\<authentication></span><span class="sxs-lookup"><span data-stu-id="74533-123">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|<span data-ttu-id="74533-124">指定客户端使用的服务证书的身份验证行为。</span><span class="sxs-lookup"><span data-stu-id="74533-124">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74533-125">父元素</span><span class="sxs-lookup"><span data-stu-id="74533-125">Parent Elements</span></span>  
  
|<span data-ttu-id="74533-126">元素</span><span class="sxs-lookup"><span data-stu-id="74533-126">Element</span></span>|<span data-ttu-id="74533-127">描述</span><span class="sxs-lookup"><span data-stu-id="74533-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74533-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="74533-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="74533-129">指定客户端用于向服务证明自己的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="74533-129">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74533-130">备注</span><span class="sxs-lookup"><span data-stu-id="74533-130">Remarks</span></span>  
 <span data-ttu-id="74533-131">此配置元素指定客户端在验证使用 SSL 身份验证的服务所出示的证书时使用的设置。</span><span class="sxs-lookup"><span data-stu-id="74533-131">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="74533-132">它还包含在客户端上显式配置为对发送给使用消息安全的服务的消息进行加密的服务的所有证书。</span><span class="sxs-lookup"><span data-stu-id="74533-132">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="74533-133">特性`serviceCertificate`元素的特性相等[ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)。</span><span class="sxs-lookup"><span data-stu-id="74533-133">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74533-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="74533-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="74533-135">安全行为</span><span class="sxs-lookup"><span data-stu-id="74533-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="74533-136">保护客户端</span><span class="sxs-lookup"><span data-stu-id="74533-136">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="74533-137">使用证书</span><span class="sxs-lookup"><span data-stu-id="74533-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="74533-138">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="74533-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
