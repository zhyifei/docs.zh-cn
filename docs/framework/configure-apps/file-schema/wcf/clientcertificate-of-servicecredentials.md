---
title: <clientCertificate> 的 <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: a8a78bbfcd9dfbf6975503a845d5bb4e2d24b13d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398139"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="20375-102">\<clientCertificate > \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="20375-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="20375-103">定义一个用于在双工通信模式中对从服务发送到客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="20375-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
<span data-ttu-id="20375-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="20375-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="20375-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="20375-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="20375-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="20375-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="20375-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="20375-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="20375-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="20375-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="20375-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="20375-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="20375-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientCertificate >**</span><span class="sxs-lookup"><span data-stu-id="20375-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20375-111">语法</span><span class="sxs-lookup"><span data-stu-id="20375-111">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20375-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20375-112">Attributes and Elements</span></span>  
 <span data-ttu-id="20375-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="20375-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20375-114">特性</span><span class="sxs-lookup"><span data-stu-id="20375-114">Attributes</span></span>  
 <span data-ttu-id="20375-115">无。</span><span class="sxs-lookup"><span data-stu-id="20375-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20375-116">子元素</span><span class="sxs-lookup"><span data-stu-id="20375-116">Child Elements</span></span>  
  
|<span data-ttu-id="20375-117">元素</span><span class="sxs-lookup"><span data-stu-id="20375-117">Element</span></span>|<span data-ttu-id="20375-118">描述</span><span class="sxs-lookup"><span data-stu-id="20375-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20375-119">\<authentication></span><span class="sxs-lookup"><span data-stu-id="20375-119">\<authentication></span></span>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="20375-120">指定客户端证书的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="20375-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="20375-121">\<certificate></span><span class="sxs-lookup"><span data-stu-id="20375-121">\<certificate></span></span>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="20375-122">指定要使用的证书。</span><span class="sxs-lookup"><span data-stu-id="20375-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20375-123">父元素</span><span class="sxs-lookup"><span data-stu-id="20375-123">Parent Elements</span></span>  
  
|<span data-ttu-id="20375-124">元素</span><span class="sxs-lookup"><span data-stu-id="20375-124">Element</span></span>|<span data-ttu-id="20375-125">描述</span><span class="sxs-lookup"><span data-stu-id="20375-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20375-126">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="20375-126">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="20375-127">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="20375-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20375-128">备注</span><span class="sxs-lookup"><span data-stu-id="20375-128">Remarks</span></span>  
 <span data-ttu-id="20375-129">如果服务必须事先拥有客户端的证书才能与该客户端进行安全通信，则需要使用此元素。</span><span class="sxs-lookup"><span data-stu-id="20375-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="20375-130">使用双工通信模式时，会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="20375-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="20375-131">在更为典型的请求/响应模式中，客户端会将其证书包含在请求中，服务将使用该证书对发送回客户端的响应进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="20375-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="20375-132">但是，在双工通信模式中，服务没有来自客户端的请求，因此服务需要事先具有客户端的证书以确保发送到客户端的消息的安全。</span><span class="sxs-lookup"><span data-stu-id="20375-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="20375-133">因此，您必须通过带外协商来获取客户端的证书，并使用此元素指定该证书。</span><span class="sxs-lookup"><span data-stu-id="20375-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="20375-134">有关双工服务的详细信息， [请参阅如何：创建双工协定](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="20375-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="20375-135">在此元素中设置的证书用于仅针对配置有 `MutualCertificateDuplex` 消息安全身份验证模式的绑定加密发送到客户端的消息。</span><span class="sxs-lookup"><span data-stu-id="20375-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20375-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="20375-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="20375-137">如何：创建双工协定</span><span class="sxs-lookup"><span data-stu-id="20375-137">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="20375-138">安全行为</span><span class="sxs-lookup"><span data-stu-id="20375-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="20375-139">使用证书</span><span class="sxs-lookup"><span data-stu-id="20375-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
