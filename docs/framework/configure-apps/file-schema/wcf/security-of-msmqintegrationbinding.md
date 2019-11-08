---
title: <security> 的 <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 2268bf48a2b86c3b3b25db006e6f8f55ea33af73
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738691"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="13f87-102">\<msmqIntegrationBinding 的安全 > \<</span><span class="sxs-lookup"><span data-stu-id="13f87-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="13f87-103">定义消息队列 (MSMQ) 集成通道的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="13f87-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="13f87-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="13f87-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="13f87-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="13f87-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="13f87-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="13f87-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="13f87-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<msmqIntegrationBinding >** ](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="13f87-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="13f87-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="13f87-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="13f87-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<** ></span><span class="sxs-lookup"><span data-stu-id="13f87-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13f87-110">语法</span><span class="sxs-lookup"><span data-stu-id="13f87-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13f87-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13f87-111">Attributes and Elements</span></span>  
 <span data-ttu-id="13f87-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="13f87-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13f87-113">特性</span><span class="sxs-lookup"><span data-stu-id="13f87-113">Attributes</span></span>  
  
|<span data-ttu-id="13f87-114">特性</span><span class="sxs-lookup"><span data-stu-id="13f87-114">Attribute</span></span>|<span data-ttu-id="13f87-115">描述</span><span class="sxs-lookup"><span data-stu-id="13f87-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13f87-116">mode</span><span class="sxs-lookup"><span data-stu-id="13f87-116">mode</span></span>|<span data-ttu-id="13f87-117">指定使用消息队列集成通道控制完整性、保密性和身份验证的安全类型。</span><span class="sxs-lookup"><span data-stu-id="13f87-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="13f87-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="13f87-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="13f87-119">-None：这将禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="13f87-119">-   None: This disables security.</span></span><br /><span data-ttu-id="13f87-120">-Transport：传输提供保护和身份验证。</span><span class="sxs-lookup"><span data-stu-id="13f87-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="13f87-121">这适用于两个队列管理器之间的消息安全性。</span><span class="sxs-lookup"><span data-stu-id="13f87-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="13f87-122">未在应用程序和队列管理器之间提供安全性。</span><span class="sxs-lookup"><span data-stu-id="13f87-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="13f87-123">现有的 Msmq 应用程序与此类型的安全模式功能等效。</span><span class="sxs-lookup"><span data-stu-id="13f87-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="13f87-124">默认值为 `Transport`。</span><span class="sxs-lookup"><span data-stu-id="13f87-124">The default value is `Transport`.</span></span> <span data-ttu-id="13f87-125">此属性的类型为 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="13f87-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13f87-126">子元素</span><span class="sxs-lookup"><span data-stu-id="13f87-126">Child Elements</span></span>  
  
|<span data-ttu-id="13f87-127">元素</span><span class="sxs-lookup"><span data-stu-id="13f87-127">Element</span></span>|<span data-ttu-id="13f87-128">描述</span><span class="sxs-lookup"><span data-stu-id="13f87-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13f87-129">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="13f87-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="13f87-130">定义消息队列集成传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="13f87-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="13f87-131">此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="13f87-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13f87-132">父元素</span><span class="sxs-lookup"><span data-stu-id="13f87-132">Parent Elements</span></span>  
  
|<span data-ttu-id="13f87-133">元素</span><span class="sxs-lookup"><span data-stu-id="13f87-133">Element</span></span>|<span data-ttu-id="13f87-134">描述</span><span class="sxs-lookup"><span data-stu-id="13f87-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13f87-135">\<binding ></span><span class="sxs-lookup"><span data-stu-id="13f87-135">\<binding></span></span>](bindings.md)|<span data-ttu-id="13f87-136">[\<msmqIntegrationBinding >](msmqintegrationbinding.md)的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="13f87-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13f87-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="13f87-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="13f87-138">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="13f87-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="13f87-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="13f87-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="13f87-140">绑定</span><span class="sxs-lookup"><span data-stu-id="13f87-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="13f87-141">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="13f87-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="13f87-142">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="13f87-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="13f87-143">\<binding ></span><span class="sxs-lookup"><span data-stu-id="13f87-143">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="13f87-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="13f87-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)
