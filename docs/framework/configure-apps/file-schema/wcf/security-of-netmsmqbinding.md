---
title: '&lt; netMsmqBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
author: BrucePerlerMS
ms.openlocfilehash: 90293cade964f6559c4783433914e1f858975c3c
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845097"
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="6cf90-102">&lt; netMsmqBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="6cf90-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="6cf90-103">定义 MSMQ 绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="6cf90-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="6cf90-104">它指定是否启用传输或 SOAP 安全；如果启用，还指定所使用的身份验证模式和保护级别。</span><span class="sxs-lookup"><span data-stu-id="6cf90-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="6cf90-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6cf90-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6cf90-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6cf90-106">\<bindings></span></span>  
<span data-ttu-id="6cf90-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="6cf90-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="6cf90-108">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6cf90-108">\<binding></span></span>  
<span data-ttu-id="6cf90-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="6cf90-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cf90-110">语法</span><span class="sxs-lookup"><span data-stu-id="6cf90-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cf90-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6cf90-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6cf90-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6cf90-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cf90-113">特性</span><span class="sxs-lookup"><span data-stu-id="6cf90-113">Attributes</span></span>  
  
|<span data-ttu-id="6cf90-114">特性</span><span class="sxs-lookup"><span data-stu-id="6cf90-114">Attribute</span></span>|<span data-ttu-id="6cf90-115">描述</span><span class="sxs-lookup"><span data-stu-id="6cf90-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6cf90-116">mode</span><span class="sxs-lookup"><span data-stu-id="6cf90-116">mode</span></span>|<span data-ttu-id="6cf90-117">指定用于控制完整性、保密性和身份验证的安全类型。</span><span class="sxs-lookup"><span data-stu-id="6cf90-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="6cf90-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="6cf90-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6cf90-119">-None： 禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="6cf90-119">-   None: This disables security.</span></span><br /><span data-ttu-id="6cf90-120">-传输： 提供保护和身份验证由传输。</span><span class="sxs-lookup"><span data-stu-id="6cf90-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="6cf90-121">这适用于两个队列管理器之间的消息安全性。</span><span class="sxs-lookup"><span data-stu-id="6cf90-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="6cf90-122">未在应用程序和队列管理器之间提供安全性。</span><span class="sxs-lookup"><span data-stu-id="6cf90-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="6cf90-123">现有的 Msmq 应用程序与此类型的安全模式功能等效。</span><span class="sxs-lookup"><span data-stu-id="6cf90-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="6cf90-124">-消息： 指定端端应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="6cf90-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="6cf90-125">未在传输层提供安全性。</span><span class="sxs-lookup"><span data-stu-id="6cf90-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="6cf90-126">这类似于其他标准绑定提供的安全性。</span><span class="sxs-lookup"><span data-stu-id="6cf90-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="6cf90-127">-两者： 提供了传输和 SOAP 消息传送层的安全性。</span><span class="sxs-lookup"><span data-stu-id="6cf90-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="6cf90-128">在这两个层上需要相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="6cf90-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="6cf90-129">默认值为 Transport。</span><span class="sxs-lookup"><span data-stu-id="6cf90-129">The default value is Transport.</span></span> <span data-ttu-id="6cf90-130">此属性的类型为 <xref:System.ServiceModel.NetMsmqSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="6cf90-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6cf90-131">子元素</span><span class="sxs-lookup"><span data-stu-id="6cf90-131">Child Elements</span></span>  
  
|<span data-ttu-id="6cf90-132">元素</span><span class="sxs-lookup"><span data-stu-id="6cf90-132">Element</span></span>|<span data-ttu-id="6cf90-133">描述</span><span class="sxs-lookup"><span data-stu-id="6cf90-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cf90-134">\<message></span><span class="sxs-lookup"><span data-stu-id="6cf90-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="6cf90-135">定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="6cf90-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="6cf90-136">此元素的类型为 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>。</span><span class="sxs-lookup"><span data-stu-id="6cf90-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="6cf90-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="6cf90-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="6cf90-138">定义 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="6cf90-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="6cf90-139">此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="6cf90-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6cf90-140">父元素</span><span class="sxs-lookup"><span data-stu-id="6cf90-140">Parent Elements</span></span>  
  
|<span data-ttu-id="6cf90-141">元素</span><span class="sxs-lookup"><span data-stu-id="6cf90-141">Element</span></span>|<span data-ttu-id="6cf90-142">描述</span><span class="sxs-lookup"><span data-stu-id="6cf90-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6cf90-143">绑定</span><span class="sxs-lookup"><span data-stu-id="6cf90-143">binding</span></span>|<span data-ttu-id="6cf90-144">绑定元素[ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6cf90-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6cf90-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="6cf90-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [<span data-ttu-id="6cf90-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="6cf90-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="6cf90-147">绑定</span><span class="sxs-lookup"><span data-stu-id="6cf90-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6cf90-148">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="6cf90-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="6cf90-149">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="6cf90-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="6cf90-150">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6cf90-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="6cf90-151">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="6cf90-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
