---
title: <security> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 1bbc3a460ce707e71b72a469af2e03acd8dc79e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936690"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="20ffa-102">\<netMsmqBinding 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="20ffa-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="20ffa-103">定义 MSMQ 绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="20ffa-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="20ffa-104">它指定是否启用传输或 SOAP 安全；如果启用，还指定所使用的身份验证模式和保护级别。</span><span class="sxs-lookup"><span data-stu-id="20ffa-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="20ffa-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="20ffa-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="20ffa-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="20ffa-106">\<bindings></span></span>  
<span data-ttu-id="20ffa-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="20ffa-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="20ffa-108">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="20ffa-108">\<binding></span></span>  
<span data-ttu-id="20ffa-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="20ffa-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ffa-110">语法</span><span class="sxs-lookup"><span data-stu-id="20ffa-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20ffa-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20ffa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="20ffa-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="20ffa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20ffa-113">特性</span><span class="sxs-lookup"><span data-stu-id="20ffa-113">Attributes</span></span>  
  
|<span data-ttu-id="20ffa-114">特性</span><span class="sxs-lookup"><span data-stu-id="20ffa-114">Attribute</span></span>|<span data-ttu-id="20ffa-115">描述</span><span class="sxs-lookup"><span data-stu-id="20ffa-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20ffa-116">mode</span><span class="sxs-lookup"><span data-stu-id="20ffa-116">mode</span></span>|<span data-ttu-id="20ffa-117">指定用于控制完整性、保密性和身份验证的安全类型。</span><span class="sxs-lookup"><span data-stu-id="20ffa-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="20ffa-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="20ffa-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="20ffa-119">内容这将禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="20ffa-119">-   None: This disables security.</span></span><br /><span data-ttu-id="20ffa-120">Transport传输提供保护和身份验证。</span><span class="sxs-lookup"><span data-stu-id="20ffa-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="20ffa-121">这适用于两个队列管理器之间的消息安全性。</span><span class="sxs-lookup"><span data-stu-id="20ffa-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="20ffa-122">未在应用程序和队列管理器之间提供安全性。</span><span class="sxs-lookup"><span data-stu-id="20ffa-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="20ffa-123">现有的 Msmq 应用程序与此类型的安全模式功能等效。</span><span class="sxs-lookup"><span data-stu-id="20ffa-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="20ffa-124">邮件指定端应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="20ffa-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="20ffa-125">未在传输层提供安全性。</span><span class="sxs-lookup"><span data-stu-id="20ffa-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="20ffa-126">这类似于其他标准绑定提供的安全性。</span><span class="sxs-lookup"><span data-stu-id="20ffa-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="20ffa-127">全部提供传输和 SOAP 消息传送层的安全性。</span><span class="sxs-lookup"><span data-stu-id="20ffa-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="20ffa-128">在这两个层上需要相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="20ffa-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="20ffa-129">默认值为 Transport。</span><span class="sxs-lookup"><span data-stu-id="20ffa-129">The default value is Transport.</span></span> <span data-ttu-id="20ffa-130">此属性的类型为 <xref:System.ServiceModel.NetMsmqSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="20ffa-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20ffa-131">子元素</span><span class="sxs-lookup"><span data-stu-id="20ffa-131">Child Elements</span></span>  
  
|<span data-ttu-id="20ffa-132">元素</span><span class="sxs-lookup"><span data-stu-id="20ffa-132">Element</span></span>|<span data-ttu-id="20ffa-133">描述</span><span class="sxs-lookup"><span data-stu-id="20ffa-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20ffa-134">\<message></span><span class="sxs-lookup"><span data-stu-id="20ffa-134">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="20ffa-135">定义 SOAP 消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="20ffa-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="20ffa-136">此元素的类型为 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>。</span><span class="sxs-lookup"><span data-stu-id="20ffa-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="20ffa-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="20ffa-137">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="20ffa-138">定义 MSMQ 传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="20ffa-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="20ffa-139">此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="20ffa-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20ffa-140">父元素</span><span class="sxs-lookup"><span data-stu-id="20ffa-140">Parent Elements</span></span>  
  
|<span data-ttu-id="20ffa-141">元素</span><span class="sxs-lookup"><span data-stu-id="20ffa-141">Element</span></span>|<span data-ttu-id="20ffa-142">描述</span><span class="sxs-lookup"><span data-stu-id="20ffa-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20ffa-143">绑定</span><span class="sxs-lookup"><span data-stu-id="20ffa-143">binding</span></span>|<span data-ttu-id="20ffa-144">NetMsmqBinding 的 binding 元素 > [ \<](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="20ffa-144">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20ffa-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="20ffa-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="20ffa-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="20ffa-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="20ffa-147">绑定</span><span class="sxs-lookup"><span data-stu-id="20ffa-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="20ffa-148">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="20ffa-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="20ffa-149">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="20ffa-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="20ffa-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="20ffa-150">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="20ffa-151">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="20ffa-151">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
