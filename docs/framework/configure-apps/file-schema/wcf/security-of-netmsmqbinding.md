---
title: <security> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: c780b157d0d566e24c6826c253401a51fbfab69d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399842"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="19031-102">\<netMsmqBinding 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="19031-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="19031-103">定义 MSMQ 绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="19031-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="19031-104">它指定是否启用传输或 SOAP 安全；如果启用，还指定所使用的身份验证模式和保护级别。</span><span class="sxs-lookup"><span data-stu-id="19031-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="19031-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19031-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19031-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="19031-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="19031-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="19031-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="19031-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="19031-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="19031-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="19031-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="19031-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<安全 >**</span><span class="sxs-lookup"><span data-stu-id="19031-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19031-111">语法</span><span class="sxs-lookup"><span data-stu-id="19031-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19031-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="19031-112">Attributes and Elements</span></span>  
 <span data-ttu-id="19031-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="19031-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19031-114">特性</span><span class="sxs-lookup"><span data-stu-id="19031-114">Attributes</span></span>  
  
|<span data-ttu-id="19031-115">特性</span><span class="sxs-lookup"><span data-stu-id="19031-115">Attribute</span></span>|<span data-ttu-id="19031-116">描述</span><span class="sxs-lookup"><span data-stu-id="19031-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19031-117">mode</span><span class="sxs-lookup"><span data-stu-id="19031-117">mode</span></span>|<span data-ttu-id="19031-118">指定用于控制完整性、保密性和身份验证的安全类型。</span><span class="sxs-lookup"><span data-stu-id="19031-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="19031-119">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="19031-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="19031-120">内容这将禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="19031-120">-   None: This disables security.</span></span><br /><span data-ttu-id="19031-121">Transport传输提供保护和身份验证。</span><span class="sxs-lookup"><span data-stu-id="19031-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="19031-122">这适用于两个队列管理器之间的消息安全性。</span><span class="sxs-lookup"><span data-stu-id="19031-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="19031-123">未在应用程序和队列管理器之间提供安全性。</span><span class="sxs-lookup"><span data-stu-id="19031-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="19031-124">现有的 Msmq 应用程序与此类型的安全模式功能等效。</span><span class="sxs-lookup"><span data-stu-id="19031-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="19031-125">邮件指定端应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="19031-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="19031-126">未在传输层提供安全性。</span><span class="sxs-lookup"><span data-stu-id="19031-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="19031-127">这类似于其他标准绑定提供的安全性。</span><span class="sxs-lookup"><span data-stu-id="19031-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="19031-128">全部提供传输和 SOAP 消息传送层的安全性。</span><span class="sxs-lookup"><span data-stu-id="19031-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="19031-129">在这两个层上需要相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="19031-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="19031-130">默认值为 Transport。</span><span class="sxs-lookup"><span data-stu-id="19031-130">The default value is Transport.</span></span> <span data-ttu-id="19031-131">此属性的类型为 <xref:System.ServiceModel.NetMsmqSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="19031-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19031-132">子元素</span><span class="sxs-lookup"><span data-stu-id="19031-132">Child Elements</span></span>  
  
|<span data-ttu-id="19031-133">元素</span><span class="sxs-lookup"><span data-stu-id="19031-133">Element</span></span>|<span data-ttu-id="19031-134">描述</span><span class="sxs-lookup"><span data-stu-id="19031-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19031-135">\<message></span><span class="sxs-lookup"><span data-stu-id="19031-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="19031-136">定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="19031-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="19031-137">此元素的类型为 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>。</span><span class="sxs-lookup"><span data-stu-id="19031-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="19031-138">\<transport></span><span class="sxs-lookup"><span data-stu-id="19031-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="19031-139">定义 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="19031-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="19031-140">此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="19031-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19031-141">父元素</span><span class="sxs-lookup"><span data-stu-id="19031-141">Parent Elements</span></span>  
  
|<span data-ttu-id="19031-142">元素</span><span class="sxs-lookup"><span data-stu-id="19031-142">Element</span></span>|<span data-ttu-id="19031-143">描述</span><span class="sxs-lookup"><span data-stu-id="19031-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19031-144">绑定</span><span class="sxs-lookup"><span data-stu-id="19031-144">binding</span></span>|<span data-ttu-id="19031-145">NetMsmqBinding 的 binding 元素 > [ \<](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="19031-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19031-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="19031-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="19031-147">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="19031-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="19031-148">绑定</span><span class="sxs-lookup"><span data-stu-id="19031-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="19031-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="19031-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="19031-150">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="19031-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="19031-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="19031-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="19031-152">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="19031-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
