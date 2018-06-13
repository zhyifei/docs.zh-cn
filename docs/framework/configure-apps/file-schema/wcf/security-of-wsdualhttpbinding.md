---
title: '&lt;wsDualHttpBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 734b6d0625cfda79b600a0920ab39bda25ee2e8b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750487"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="a1fc9-102">&lt;wsDualHttpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="a1fc9-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="a1fc9-103">定义的安全功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="a1fc9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a1fc9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a1fc9-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a1fc9-105">\<bindings></span></span>  
<span data-ttu-id="a1fc9-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a1fc9-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="a1fc9-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a1fc9-107">\<binding></span></span>  
<span data-ttu-id="a1fc9-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="a1fc9-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1fc9-109">语法</span><span class="sxs-lookup"><span data-stu-id="a1fc9-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1fc9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a1fc9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a1fc9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1fc9-112">特性</span><span class="sxs-lookup"><span data-stu-id="a1fc9-112">Attributes</span></span>  
  
|<span data-ttu-id="a1fc9-113">特性</span><span class="sxs-lookup"><span data-stu-id="a1fc9-113">Attribute</span></span>|<span data-ttu-id="a1fc9-114">描述</span><span class="sxs-lookup"><span data-stu-id="a1fc9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1fc9-115">mode</span><span class="sxs-lookup"><span data-stu-id="a1fc9-115">mode</span></span>|<span data-ttu-id="a1fc9-116">-可选。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-116">-   Optional.</span></span> <span data-ttu-id="a1fc9-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a1fc9-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-118">The default value is `Message`.</span></span> <span data-ttu-id="a1fc9-119">此属性的类型为 <xref:System.ServiceModel.WSDualHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a1fc9-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="a1fc9-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="a1fc9-121">值</span><span class="sxs-lookup"><span data-stu-id="a1fc9-121">Value</span></span>|<span data-ttu-id="a1fc9-122">描述</span><span class="sxs-lookup"><span data-stu-id="a1fc9-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1fc9-123">无</span><span class="sxs-lookup"><span data-stu-id="a1fc9-123">None</span></span>|<span data-ttu-id="a1fc9-124">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-124">Security is disabled.</span></span>|  
|<span data-ttu-id="a1fc9-125">消息</span><span class="sxs-lookup"><span data-stu-id="a1fc9-125">Message</span></span>|<span data-ttu-id="a1fc9-126">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1fc9-127">子元素</span><span class="sxs-lookup"><span data-stu-id="a1fc9-127">Child Elements</span></span>  
  
|<span data-ttu-id="a1fc9-128">元素</span><span class="sxs-lookup"><span data-stu-id="a1fc9-128">Element</span></span>|<span data-ttu-id="a1fc9-129">描述</span><span class="sxs-lookup"><span data-stu-id="a1fc9-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1fc9-130">\<message></span><span class="sxs-lookup"><span data-stu-id="a1fc9-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="a1fc9-131">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="a1fc9-132">此元素的类型为 <xref:System.ServiceModel.MessageSecurityOverHttp>。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1fc9-133">父元素</span><span class="sxs-lookup"><span data-stu-id="a1fc9-133">Parent Elements</span></span>  
  
|<span data-ttu-id="a1fc9-134">元素</span><span class="sxs-lookup"><span data-stu-id="a1fc9-134">Element</span></span>|<span data-ttu-id="a1fc9-135">描述</span><span class="sxs-lookup"><span data-stu-id="a1fc9-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1fc9-136">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a1fc9-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a1fc9-137">定义的所有绑定功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1fc9-138">备注</span><span class="sxs-lookup"><span data-stu-id="a1fc9-138">Remarks</span></span>  
 <span data-ttu-id="a1fc9-139">双向绑定向服务公开客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="a1fc9-140">客户端应使用安全来确保仅连接到自己信任的服务。</span><span class="sxs-lookup"><span data-stu-id="a1fc9-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fc9-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1fc9-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="a1fc9-142">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="a1fc9-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a1fc9-143">绑定</span><span class="sxs-lookup"><span data-stu-id="a1fc9-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a1fc9-144">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a1fc9-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a1fc9-145">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a1fc9-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a1fc9-146">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a1fc9-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
