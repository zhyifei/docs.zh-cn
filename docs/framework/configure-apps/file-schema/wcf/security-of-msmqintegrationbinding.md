---
title: '&lt;msmqIntegrationBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 574c0d7cba88f724143e642da13cace8c329dea6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199989"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="c37fe-102">&lt;msmqIntegrationBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="c37fe-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="c37fe-103">定义消息队列 (MSMQ) 集成通道的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="c37fe-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="c37fe-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c37fe-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c37fe-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c37fe-105">\<bindings></span></span>  
<span data-ttu-id="c37fe-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="c37fe-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="c37fe-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c37fe-107">\<binding></span></span>  
<span data-ttu-id="c37fe-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="c37fe-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37fe-109">语法</span><span class="sxs-lookup"><span data-stu-id="c37fe-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c37fe-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c37fe-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c37fe-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c37fe-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c37fe-112">特性</span><span class="sxs-lookup"><span data-stu-id="c37fe-112">Attributes</span></span>  
  
|<span data-ttu-id="c37fe-113">特性</span><span class="sxs-lookup"><span data-stu-id="c37fe-113">Attribute</span></span>|<span data-ttu-id="c37fe-114">描述</span><span class="sxs-lookup"><span data-stu-id="c37fe-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c37fe-115">mode</span><span class="sxs-lookup"><span data-stu-id="c37fe-115">mode</span></span>|<span data-ttu-id="c37fe-116">指定使用消息队列集成通道控制完整性、保密性和身份验证的安全类型。</span><span class="sxs-lookup"><span data-stu-id="c37fe-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="c37fe-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c37fe-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c37fe-118">-None： 禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="c37fe-118">-   None: This disables security.</span></span><br /><span data-ttu-id="c37fe-119">-传输： 提供保护和身份验证由传输。</span><span class="sxs-lookup"><span data-stu-id="c37fe-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="c37fe-120">这适用于两个队列管理器之间的消息安全性。</span><span class="sxs-lookup"><span data-stu-id="c37fe-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="c37fe-121">未在应用程序和队列管理器之间提供安全性。</span><span class="sxs-lookup"><span data-stu-id="c37fe-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="c37fe-122">现有的 Msmq 应用程序与此类型的安全模式功能等效。</span><span class="sxs-lookup"><span data-stu-id="c37fe-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="c37fe-123">默认值为 `Transport`。</span><span class="sxs-lookup"><span data-stu-id="c37fe-123">The default value is `Transport`.</span></span> <span data-ttu-id="c37fe-124">此属性的类型为 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="c37fe-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c37fe-125">子元素</span><span class="sxs-lookup"><span data-stu-id="c37fe-125">Child Elements</span></span>  
  
|<span data-ttu-id="c37fe-126">元素</span><span class="sxs-lookup"><span data-stu-id="c37fe-126">Element</span></span>|<span data-ttu-id="c37fe-127">描述</span><span class="sxs-lookup"><span data-stu-id="c37fe-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c37fe-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="c37fe-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="c37fe-129">定义消息队列集成传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="c37fe-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="c37fe-130">此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="c37fe-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c37fe-131">父元素</span><span class="sxs-lookup"><span data-stu-id="c37fe-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c37fe-132">元素</span><span class="sxs-lookup"><span data-stu-id="c37fe-132">Element</span></span>|<span data-ttu-id="c37fe-133">描述</span><span class="sxs-lookup"><span data-stu-id="c37fe-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c37fe-134">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c37fe-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c37fe-135">绑定元素[ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="c37fe-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c37fe-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c37fe-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="c37fe-137">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="c37fe-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="c37fe-138">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="c37fe-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="c37fe-139">绑定</span><span class="sxs-lookup"><span data-stu-id="c37fe-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c37fe-140">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="c37fe-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c37fe-141">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="c37fe-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="c37fe-142">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c37fe-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="c37fe-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="c37fe-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
