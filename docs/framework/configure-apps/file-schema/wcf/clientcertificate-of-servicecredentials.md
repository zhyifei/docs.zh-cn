---
title: "&lt;serviceCredentials&gt; 的 &lt;clientCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc4b3251a85a6926c93f418c154b4eabbd44092f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a><span data-ttu-id="f9f47-102">&lt;serviceCredentials&gt; 的 &lt;clientCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="f9f47-102">&lt;clientCertificate&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="f9f47-103">定义一个用于在双工通信模式中对从服务发送到客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="f9f47-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="f9f47-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f9f47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f9f47-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="f9f47-105">\<behaviors></span></span>  
<span data-ttu-id="f9f47-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f9f47-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f9f47-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f9f47-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="f9f47-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="f9f47-108">\<behavior></span></span>  
<span data-ttu-id="f9f47-109">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="f9f47-109">\<serviceCredentials></span></span>  
<span data-ttu-id="f9f47-110">\<t i a l ></span><span class="sxs-lookup"><span data-stu-id="f9f47-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f47-111">语法</span><span class="sxs-lookup"><span data-stu-id="f9f47-111">Syntax</span></span>  
  
```xml  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9f47-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f9f47-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f9f47-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f9f47-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9f47-114">特性</span><span class="sxs-lookup"><span data-stu-id="f9f47-114">Attributes</span></span>  
 <span data-ttu-id="f9f47-115">无。</span><span class="sxs-lookup"><span data-stu-id="f9f47-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f9f47-116">子元素</span><span class="sxs-lookup"><span data-stu-id="f9f47-116">Child Elements</span></span>  
  
|<span data-ttu-id="f9f47-117">元素</span><span class="sxs-lookup"><span data-stu-id="f9f47-117">Element</span></span>|<span data-ttu-id="f9f47-118">描述</span><span class="sxs-lookup"><span data-stu-id="f9f47-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9f47-119">\<身份验证 ></span><span class="sxs-lookup"><span data-stu-id="f9f47-119">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|<span data-ttu-id="f9f47-120">指定客户端证书的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="f9f47-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="f9f47-121">\<证书 ></span><span class="sxs-lookup"><span data-stu-id="f9f47-121">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|<span data-ttu-id="f9f47-122">指定要使用的证书。</span><span class="sxs-lookup"><span data-stu-id="f9f47-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9f47-123">父元素</span><span class="sxs-lookup"><span data-stu-id="f9f47-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f9f47-124">元素</span><span class="sxs-lookup"><span data-stu-id="f9f47-124">Element</span></span>|<span data-ttu-id="f9f47-125">描述</span><span class="sxs-lookup"><span data-stu-id="f9f47-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9f47-126">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="f9f47-126">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="f9f47-127">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="f9f47-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9f47-128">备注</span><span class="sxs-lookup"><span data-stu-id="f9f47-128">Remarks</span></span>  
 <span data-ttu-id="f9f47-129">如果服务必须事先拥有客户端的证书才能与该客户端进行安全通信，则需要使用此元素。</span><span class="sxs-lookup"><span data-stu-id="f9f47-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="f9f47-130">使用双工通信模式时，会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="f9f47-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="f9f47-131">在更为典型的请求/响应模式中，客户端会将其证书包含在请求中，服务将使用该证书对发送回客户端的响应进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="f9f47-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="f9f47-132">但是，在双工通信模式中，服务没有来自客户端的请求，因此服务需要事先具有客户端的证书以确保发送到客户端的消息的安全。</span><span class="sxs-lookup"><span data-stu-id="f9f47-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="f9f47-133">因此，您必须通过带外协商来获取客户端的证书，并使用此元素指定该证书。</span><span class="sxs-lookup"><span data-stu-id="f9f47-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="f9f47-134">有关双工服务的详细信息，请参阅[如何： 创建双工协定](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="f9f47-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="f9f47-135">在此元素中设置的证书用于仅针对配置有 `MutualCertificateDuplex` 消息安全身份验证模式的绑定加密发送到客户端的消息。</span><span class="sxs-lookup"><span data-stu-id="f9f47-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9f47-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9f47-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>  
 [<span data-ttu-id="f9f47-137">如何： 创建双工协定</span><span class="sxs-lookup"><span data-stu-id="f9f47-137">How to: Create a Duplex Contract</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="f9f47-138">安全行为</span><span class="sxs-lookup"><span data-stu-id="f9f47-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="f9f47-139">使用证书</span><span class="sxs-lookup"><span data-stu-id="f9f47-139">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
