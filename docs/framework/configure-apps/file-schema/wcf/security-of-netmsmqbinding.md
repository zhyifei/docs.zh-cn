---
title: "&lt; netMsmqBinding&gt; 的 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 15ebbd1f0f139ef0d66ed802b990876735074485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="e079a-102">&lt; netMsmqBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="e079a-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="e079a-103">定义 MSMQ 绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="e079a-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="e079a-104">它指定是否启用传输或 SOAP 安全；如果启用，还指定所使用的身份验证模式和保护级别。</span><span class="sxs-lookup"><span data-stu-id="e079a-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="e079a-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e079a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e079a-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e079a-106">\<bindings></span></span>  
<span data-ttu-id="e079a-107">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="e079a-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="e079a-108">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e079a-108">\<binding></span></span>  
<span data-ttu-id="e079a-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="e079a-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e079a-110">语法</span><span class="sxs-lookup"><span data-stu-id="e079a-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e079a-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e079a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e079a-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e079a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e079a-113">特性</span><span class="sxs-lookup"><span data-stu-id="e079a-113">Attributes</span></span>  
  
|<span data-ttu-id="e079a-114">特性</span><span class="sxs-lookup"><span data-stu-id="e079a-114">Attribute</span></span>|<span data-ttu-id="e079a-115">描述</span><span class="sxs-lookup"><span data-stu-id="e079a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e079a-116">mode</span><span class="sxs-lookup"><span data-stu-id="e079a-116">mode</span></span>|<span data-ttu-id="e079a-117">指定用于控制完整性、保密性和身份验证的安全类型。</span><span class="sxs-lookup"><span data-stu-id="e079a-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="e079a-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="e079a-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e079a-119">-None： 禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="e079a-119">-   None: This disables security.</span></span><br /><span data-ttu-id="e079a-120">-传输： 保护和身份验证可以由传输。</span><span class="sxs-lookup"><span data-stu-id="e079a-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="e079a-121">这适用于两个队列管理器之间的消息安全性。</span><span class="sxs-lookup"><span data-stu-id="e079a-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="e079a-122">未在应用程序和队列管理器之间提供安全性。</span><span class="sxs-lookup"><span data-stu-id="e079a-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="e079a-123">现有的 Msmq 应用程序与此类型的安全模式功能等效。</span><span class="sxs-lookup"><span data-stu-id="e079a-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="e079a-124">-消息： 指定端应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="e079a-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="e079a-125">未在传输层提供安全性。</span><span class="sxs-lookup"><span data-stu-id="e079a-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="e079a-126">这类似于其他标准绑定提供的安全性。</span><span class="sxs-lookup"><span data-stu-id="e079a-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="e079a-127">-两者： 提供在传输和 SOAP 消息层安全性。</span><span class="sxs-lookup"><span data-stu-id="e079a-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="e079a-128">在这两个层上需要相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="e079a-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="e079a-129">默认值为 Transport。</span><span class="sxs-lookup"><span data-stu-id="e079a-129">The default value is Transport.</span></span> <span data-ttu-id="e079a-130">此属性的类型为 <xref:System.ServiceModel.NetMsmqSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="e079a-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e079a-131">子元素</span><span class="sxs-lookup"><span data-stu-id="e079a-131">Child Elements</span></span>  
  
|<span data-ttu-id="e079a-132">元素</span><span class="sxs-lookup"><span data-stu-id="e079a-132">Element</span></span>|<span data-ttu-id="e079a-133">描述</span><span class="sxs-lookup"><span data-stu-id="e079a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e079a-134">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="e079a-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="e079a-135">定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="e079a-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="e079a-136">此元素的类型为 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>。</span><span class="sxs-lookup"><span data-stu-id="e079a-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="e079a-137">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="e079a-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="e079a-138">定义 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="e079a-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="e079a-139">此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="e079a-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e079a-140">父元素</span><span class="sxs-lookup"><span data-stu-id="e079a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e079a-141">元素</span><span class="sxs-lookup"><span data-stu-id="e079a-141">Element</span></span>|<span data-ttu-id="e079a-142">描述</span><span class="sxs-lookup"><span data-stu-id="e079a-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e079a-143">绑定</span><span class="sxs-lookup"><span data-stu-id="e079a-143">binding</span></span>|<span data-ttu-id="e079a-144">绑定元素[ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e079a-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e079a-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e079a-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [<span data-ttu-id="e079a-146">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="e079a-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e079a-147">绑定</span><span class="sxs-lookup"><span data-stu-id="e079a-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e079a-148">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="e079a-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e079a-149">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="e079a-149">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e079a-150">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e079a-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="e079a-151">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="e079a-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
