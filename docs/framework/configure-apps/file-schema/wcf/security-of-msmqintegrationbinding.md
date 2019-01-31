---
title: <security> 的 <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: ceda00615ae579edb0360006bb70acd11716ce6a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275166"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="8a24d-102">\<安全 > 的\<msmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="8a24d-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="8a24d-103">定义消息队列 (MSMQ) 集成通道的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="8a24d-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="8a24d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8a24d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8a24d-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8a24d-105">\<bindings></span></span>  
<span data-ttu-id="8a24d-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="8a24d-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="8a24d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8a24d-107">\<binding></span></span>  
<span data-ttu-id="8a24d-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="8a24d-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a24d-109">语法</span><span class="sxs-lookup"><span data-stu-id="8a24d-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a24d-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8a24d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8a24d-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8a24d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a24d-112">特性</span><span class="sxs-lookup"><span data-stu-id="8a24d-112">Attributes</span></span>  
  
|<span data-ttu-id="8a24d-113">特性</span><span class="sxs-lookup"><span data-stu-id="8a24d-113">Attribute</span></span>|<span data-ttu-id="8a24d-114">描述</span><span class="sxs-lookup"><span data-stu-id="8a24d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a24d-115">mode</span><span class="sxs-lookup"><span data-stu-id="8a24d-115">mode</span></span>|<span data-ttu-id="8a24d-116">指定使用消息队列集成通道控制完整性、保密性和身份验证的安全类型。</span><span class="sxs-lookup"><span data-stu-id="8a24d-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="8a24d-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="8a24d-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8a24d-118">-None:这将禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="8a24d-118">-   None: This disables security.</span></span><br /><span data-ttu-id="8a24d-119">-传输：保护和身份验证由传输提供。</span><span class="sxs-lookup"><span data-stu-id="8a24d-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="8a24d-120">这适用于两个队列管理器之间的消息安全性。</span><span class="sxs-lookup"><span data-stu-id="8a24d-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="8a24d-121">未在应用程序和队列管理器之间提供安全性。</span><span class="sxs-lookup"><span data-stu-id="8a24d-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="8a24d-122">现有的 Msmq 应用程序与此类型的安全模式功能等效。</span><span class="sxs-lookup"><span data-stu-id="8a24d-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="8a24d-123">默认值为 `Transport`。</span><span class="sxs-lookup"><span data-stu-id="8a24d-123">The default value is `Transport`.</span></span> <span data-ttu-id="8a24d-124">此属性的类型为 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="8a24d-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a24d-125">子元素</span><span class="sxs-lookup"><span data-stu-id="8a24d-125">Child Elements</span></span>  
  
|<span data-ttu-id="8a24d-126">元素</span><span class="sxs-lookup"><span data-stu-id="8a24d-126">Element</span></span>|<span data-ttu-id="8a24d-127">描述</span><span class="sxs-lookup"><span data-stu-id="8a24d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a24d-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="8a24d-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="8a24d-129">定义消息队列集成传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="8a24d-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="8a24d-130">此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="8a24d-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a24d-131">父元素</span><span class="sxs-lookup"><span data-stu-id="8a24d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8a24d-132">元素</span><span class="sxs-lookup"><span data-stu-id="8a24d-132">Element</span></span>|<span data-ttu-id="8a24d-133">描述</span><span class="sxs-lookup"><span data-stu-id="8a24d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a24d-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="8a24d-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8a24d-135">绑定元素[ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="8a24d-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a24d-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a24d-136">See also</span></span>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="8a24d-137">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="8a24d-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="8a24d-138">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="8a24d-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8a24d-139">绑定</span><span class="sxs-lookup"><span data-stu-id="8a24d-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8a24d-140">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="8a24d-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8a24d-141">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="8a24d-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8a24d-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="8a24d-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="8a24d-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="8a24d-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
