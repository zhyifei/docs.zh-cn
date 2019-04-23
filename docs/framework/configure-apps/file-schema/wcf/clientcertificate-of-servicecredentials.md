---
title: <clientCertificate> 的 <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 26ebac6439a90959e3a926e6a36c9044251a4aae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107975"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="6745d-102">\<clientCertificate> of \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="6745d-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="6745d-103">定义一个用于在双工通信模式中对从服务发送到客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="6745d-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="6745d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6745d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6745d-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="6745d-105">\<behaviors></span></span>  
<span data-ttu-id="6745d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6745d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6745d-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6745d-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="6745d-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6745d-108">\<behavior></span></span>  
<span data-ttu-id="6745d-109">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="6745d-109">\<serviceCredentials></span></span>  
<span data-ttu-id="6745d-110">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="6745d-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6745d-111">语法</span><span class="sxs-lookup"><span data-stu-id="6745d-111">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6745d-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6745d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6745d-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6745d-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6745d-114">特性</span><span class="sxs-lookup"><span data-stu-id="6745d-114">Attributes</span></span>  
 <span data-ttu-id="6745d-115">无。</span><span class="sxs-lookup"><span data-stu-id="6745d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6745d-116">子元素</span><span class="sxs-lookup"><span data-stu-id="6745d-116">Child Elements</span></span>  
  
|<span data-ttu-id="6745d-117">元素</span><span class="sxs-lookup"><span data-stu-id="6745d-117">Element</span></span>|<span data-ttu-id="6745d-118">描述</span><span class="sxs-lookup"><span data-stu-id="6745d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6745d-119">\<authentication></span><span class="sxs-lookup"><span data-stu-id="6745d-119">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|<span data-ttu-id="6745d-120">指定客户端证书的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="6745d-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="6745d-121">\<certificate></span><span class="sxs-lookup"><span data-stu-id="6745d-121">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|<span data-ttu-id="6745d-122">指定要使用的证书。</span><span class="sxs-lookup"><span data-stu-id="6745d-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6745d-123">父元素</span><span class="sxs-lookup"><span data-stu-id="6745d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6745d-124">元素</span><span class="sxs-lookup"><span data-stu-id="6745d-124">Element</span></span>|<span data-ttu-id="6745d-125">描述</span><span class="sxs-lookup"><span data-stu-id="6745d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6745d-126">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="6745d-126">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="6745d-127">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="6745d-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6745d-128">备注</span><span class="sxs-lookup"><span data-stu-id="6745d-128">Remarks</span></span>  
 <span data-ttu-id="6745d-129">如果服务必须事先拥有客户端的证书才能与该客户端进行安全通信，则需要使用此元素。</span><span class="sxs-lookup"><span data-stu-id="6745d-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="6745d-130">使用双工通信模式时，会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="6745d-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="6745d-131">在更为典型的请求/响应模式中，客户端会将其证书包含在请求中，服务将使用该证书对发送回客户端的响应进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="6745d-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="6745d-132">但是，在双工通信模式中，服务没有来自客户端的请求，因此服务需要事先具有客户端的证书以确保发送到客户端的消息的安全。</span><span class="sxs-lookup"><span data-stu-id="6745d-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="6745d-133">因此，您必须通过带外协商来获取客户端的证书，并使用此元素指定该证书。</span><span class="sxs-lookup"><span data-stu-id="6745d-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="6745d-134">有关双工服务的详细信息，请参阅[如何：创建双工协定](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="6745d-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="6745d-135">在此元素中设置的证书用于仅针对配置有 `MutualCertificateDuplex` 消息安全身份验证模式的绑定加密发送到客户端的消息。</span><span class="sxs-lookup"><span data-stu-id="6745d-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6745d-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="6745d-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="6745d-137">如何：创建双工协定</span><span class="sxs-lookup"><span data-stu-id="6745d-137">How to: Create a Duplex Contract</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="6745d-138">安全行为</span><span class="sxs-lookup"><span data-stu-id="6745d-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6745d-139">使用证书</span><span class="sxs-lookup"><span data-stu-id="6745d-139">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
