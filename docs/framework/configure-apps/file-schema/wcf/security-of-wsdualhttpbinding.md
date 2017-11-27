---
title: "&lt;wsDualHttpBinding&gt; 的 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 72d1c451efe267d098ef4d529194905ee14d6ae3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="3cad5-102">&lt;wsDualHttpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="3cad5-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="3cad5-103">定义的安全功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="3cad5-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="3cad5-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3cad5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3cad5-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3cad5-105">\<bindings></span></span>  
<span data-ttu-id="3cad5-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3cad5-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="3cad5-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3cad5-107">\<binding></span></span>  
<span data-ttu-id="3cad5-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="3cad5-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cad5-109">语法</span><span class="sxs-lookup"><span data-stu-id="3cad5-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cad5-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3cad5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3cad5-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3cad5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cad5-112">特性</span><span class="sxs-lookup"><span data-stu-id="3cad5-112">Attributes</span></span>  
  
|<span data-ttu-id="3cad5-113">特性</span><span class="sxs-lookup"><span data-stu-id="3cad5-113">Attribute</span></span>|<span data-ttu-id="3cad5-114">描述</span><span class="sxs-lookup"><span data-stu-id="3cad5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3cad5-115">mode</span><span class="sxs-lookup"><span data-stu-id="3cad5-115">mode</span></span>|<span data-ttu-id="3cad5-116">-可选。</span><span class="sxs-lookup"><span data-stu-id="3cad5-116">-   Optional.</span></span> <span data-ttu-id="3cad5-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="3cad5-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="3cad5-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="3cad5-118">The default value is `Message`.</span></span> <span data-ttu-id="3cad5-119">此属性的类型为 <xref:System.ServiceModel.WSDualHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="3cad5-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3cad5-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="3cad5-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="3cad5-121">值</span><span class="sxs-lookup"><span data-stu-id="3cad5-121">Value</span></span>|<span data-ttu-id="3cad5-122">描述</span><span class="sxs-lookup"><span data-stu-id="3cad5-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cad5-123">无</span><span class="sxs-lookup"><span data-stu-id="3cad5-123">None</span></span>|<span data-ttu-id="3cad5-124">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="3cad5-124">Security is disabled.</span></span>|  
|<span data-ttu-id="3cad5-125">消息</span><span class="sxs-lookup"><span data-stu-id="3cad5-125">Message</span></span>|<span data-ttu-id="3cad5-126">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="3cad5-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cad5-127">子元素</span><span class="sxs-lookup"><span data-stu-id="3cad5-127">Child Elements</span></span>  
  
|<span data-ttu-id="3cad5-128">元素</span><span class="sxs-lookup"><span data-stu-id="3cad5-128">Element</span></span>|<span data-ttu-id="3cad5-129">描述</span><span class="sxs-lookup"><span data-stu-id="3cad5-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cad5-130">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="3cad5-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="3cad5-131">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="3cad5-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="3cad5-132">此元素的类型为 <xref:System.ServiceModel.MessageSecurityOverHttp>。</span><span class="sxs-lookup"><span data-stu-id="3cad5-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cad5-133">父元素</span><span class="sxs-lookup"><span data-stu-id="3cad5-133">Parent Elements</span></span>  
  
|<span data-ttu-id="3cad5-134">元素</span><span class="sxs-lookup"><span data-stu-id="3cad5-134">Element</span></span>|<span data-ttu-id="3cad5-135">描述</span><span class="sxs-lookup"><span data-stu-id="3cad5-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cad5-136">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3cad5-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="3cad5-137">定义的所有绑定功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="3cad5-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cad5-138">备注</span><span class="sxs-lookup"><span data-stu-id="3cad5-138">Remarks</span></span>  
 <span data-ttu-id="3cad5-139">双向绑定向服务公开客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3cad5-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="3cad5-140">客户端应使用安全来确保仅连接到自己信任的服务。</span><span class="sxs-lookup"><span data-stu-id="3cad5-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cad5-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cad5-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="3cad5-142">保护服务和客户端</span><span class="sxs-lookup"><span data-stu-id="3cad5-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3cad5-143">绑定</span><span class="sxs-lookup"><span data-stu-id="3cad5-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3cad5-144">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="3cad5-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3cad5-145">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="3cad5-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="3cad5-146">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3cad5-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
