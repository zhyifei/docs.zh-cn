---
title: <security> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: acb4d04663d841a9b494153caa180855959c145e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206507"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="23afe-102">\<安全 > 的\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="23afe-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="23afe-103">定义 MSMQ 绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="23afe-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="23afe-104">它指定是否启用传输或 SOAP 安全；如果启用，还指定所使用的身份验证模式和保护级别。</span><span class="sxs-lookup"><span data-stu-id="23afe-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="23afe-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="23afe-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="23afe-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="23afe-106">\<bindings></span></span>  
<span data-ttu-id="23afe-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="23afe-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="23afe-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="23afe-108">\<binding></span></span>  
<span data-ttu-id="23afe-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="23afe-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23afe-110">语法</span><span class="sxs-lookup"><span data-stu-id="23afe-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23afe-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="23afe-111">Attributes and Elements</span></span>  
 <span data-ttu-id="23afe-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="23afe-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23afe-113">特性</span><span class="sxs-lookup"><span data-stu-id="23afe-113">Attributes</span></span>  
  
|<span data-ttu-id="23afe-114">特性</span><span class="sxs-lookup"><span data-stu-id="23afe-114">Attribute</span></span>|<span data-ttu-id="23afe-115">描述</span><span class="sxs-lookup"><span data-stu-id="23afe-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23afe-116">mode</span><span class="sxs-lookup"><span data-stu-id="23afe-116">mode</span></span>|<span data-ttu-id="23afe-117">指定用于控制完整性、保密性和身份验证的安全类型。</span><span class="sxs-lookup"><span data-stu-id="23afe-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="23afe-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="23afe-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="23afe-119">-None:这将禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="23afe-119">-   None: This disables security.</span></span><br /><span data-ttu-id="23afe-120">-传输：保护和身份验证由传输提供。</span><span class="sxs-lookup"><span data-stu-id="23afe-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="23afe-121">这适用于两个队列管理器之间的消息安全性。</span><span class="sxs-lookup"><span data-stu-id="23afe-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="23afe-122">未在应用程序和队列管理器之间提供安全性。</span><span class="sxs-lookup"><span data-stu-id="23afe-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="23afe-123">现有的 Msmq 应用程序与此类型的安全模式功能等效。</span><span class="sxs-lookup"><span data-stu-id="23afe-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="23afe-124">-消息：指定完整应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="23afe-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="23afe-125">未在传输层提供安全性。</span><span class="sxs-lookup"><span data-stu-id="23afe-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="23afe-126">这类似于其他标准绑定提供的安全性。</span><span class="sxs-lookup"><span data-stu-id="23afe-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="23afe-127">-同时：提供了传输和 SOAP 消息传送层的安全性。</span><span class="sxs-lookup"><span data-stu-id="23afe-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="23afe-128">在这两个层上需要相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="23afe-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="23afe-129">默认值为 Transport。</span><span class="sxs-lookup"><span data-stu-id="23afe-129">The default value is Transport.</span></span> <span data-ttu-id="23afe-130">此属性的类型为 <xref:System.ServiceModel.NetMsmqSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="23afe-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23afe-131">子元素</span><span class="sxs-lookup"><span data-stu-id="23afe-131">Child Elements</span></span>  
  
|<span data-ttu-id="23afe-132">元素</span><span class="sxs-lookup"><span data-stu-id="23afe-132">Element</span></span>|<span data-ttu-id="23afe-133">描述</span><span class="sxs-lookup"><span data-stu-id="23afe-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23afe-134">\<message></span><span class="sxs-lookup"><span data-stu-id="23afe-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="23afe-135">定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="23afe-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="23afe-136">此元素的类型为 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>。</span><span class="sxs-lookup"><span data-stu-id="23afe-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="23afe-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="23afe-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="23afe-138">定义 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="23afe-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="23afe-139">此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="23afe-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23afe-140">父元素</span><span class="sxs-lookup"><span data-stu-id="23afe-140">Parent Elements</span></span>  
  
|<span data-ttu-id="23afe-141">元素</span><span class="sxs-lookup"><span data-stu-id="23afe-141">Element</span></span>|<span data-ttu-id="23afe-142">描述</span><span class="sxs-lookup"><span data-stu-id="23afe-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23afe-143">绑定</span><span class="sxs-lookup"><span data-stu-id="23afe-143">binding</span></span>|<span data-ttu-id="23afe-144">绑定元素[ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="23afe-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23afe-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="23afe-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="23afe-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="23afe-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="23afe-147">绑定</span><span class="sxs-lookup"><span data-stu-id="23afe-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="23afe-148">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="23afe-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="23afe-149">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="23afe-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="23afe-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="23afe-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="23afe-151">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="23afe-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
