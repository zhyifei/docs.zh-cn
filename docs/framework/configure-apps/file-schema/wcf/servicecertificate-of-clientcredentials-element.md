---
title: <serviceCertificate>of <clientCredentials>元素
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399687"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="09fd4-102">\<clientCredentials > 元素\<的 serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="09fd4-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="09fd4-103">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="09fd4-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
<span data-ttu-id="09fd4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="09fd4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="09fd4-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="09fd4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="09fd4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="09fd4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="09fd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="09fd4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="09fd4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="09fd4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="09fd4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="09fd4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="09fd4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**</span><span class="sxs-lookup"><span data-stu-id="09fd4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09fd4-111">语法</span><span class="sxs-lookup"><span data-stu-id="09fd4-111">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09fd4-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="09fd4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="09fd4-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="09fd4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09fd4-114">特性</span><span class="sxs-lookup"><span data-stu-id="09fd4-114">Attributes</span></span>  
 <span data-ttu-id="09fd4-115">无。</span><span class="sxs-lookup"><span data-stu-id="09fd4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="09fd4-116">子元素</span><span class="sxs-lookup"><span data-stu-id="09fd4-116">Child Elements</span></span>  
  
|<span data-ttu-id="09fd4-117">元素</span><span class="sxs-lookup"><span data-stu-id="09fd4-117">Element</span></span>|<span data-ttu-id="09fd4-118">描述</span><span class="sxs-lookup"><span data-stu-id="09fd4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09fd4-119">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="09fd4-119">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="09fd4-120">指定在服务或 STS 未通过协商协议提供证书时要使用的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="09fd4-120">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="09fd4-121">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="09fd4-121">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="09fd4-122">表示特定服务为身份验证提供的 X.509（作用域）证书的集合。</span><span class="sxs-lookup"><span data-stu-id="09fd4-122">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="09fd4-123">此集合通常用于指定联合方案中安全令牌服务的服务证书。</span><span class="sxs-lookup"><span data-stu-id="09fd4-123">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="09fd4-124">\<authentication></span><span class="sxs-lookup"><span data-stu-id="09fd4-124">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="09fd4-125">指定客户端使用的服务证书的身份验证行为。</span><span class="sxs-lookup"><span data-stu-id="09fd4-125">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09fd4-126">父元素</span><span class="sxs-lookup"><span data-stu-id="09fd4-126">Parent Elements</span></span>  
  
|<span data-ttu-id="09fd4-127">元素</span><span class="sxs-lookup"><span data-stu-id="09fd4-127">Element</span></span>|<span data-ttu-id="09fd4-128">描述</span><span class="sxs-lookup"><span data-stu-id="09fd4-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09fd4-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="09fd4-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="09fd4-130">指定客户端用于向服务证明自己的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="09fd4-130">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09fd4-131">备注</span><span class="sxs-lookup"><span data-stu-id="09fd4-131">Remarks</span></span>  
 <span data-ttu-id="09fd4-132">此配置元素指定客户端在验证使用 SSL 身份验证的服务所出示的证书时使用的设置。</span><span class="sxs-lookup"><span data-stu-id="09fd4-132">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="09fd4-133">它还包含在客户端上显式配置为对发送给使用消息安全的服务的消息进行加密的服务的所有证书。</span><span class="sxs-lookup"><span data-stu-id="09fd4-133">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="09fd4-134">`serviceCertificate`元素的特性与[ \<clientCertificate >](clientcertificate-of-clientcredentials-element.md)的特性相同。</span><span class="sxs-lookup"><span data-stu-id="09fd4-134">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fd4-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="09fd4-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="09fd4-136">安全行为</span><span class="sxs-lookup"><span data-stu-id="09fd4-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="09fd4-137">保护客户端</span><span class="sxs-lookup"><span data-stu-id="09fd4-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="09fd4-138">使用证书</span><span class="sxs-lookup"><span data-stu-id="09fd4-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="09fd4-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="09fd4-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
