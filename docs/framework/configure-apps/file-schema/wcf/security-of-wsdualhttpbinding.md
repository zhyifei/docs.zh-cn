---
title: '&lt;wsDualHttpBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
ms.openlocfilehash: 761eb9d111630d64d0fe4450c7a8950a8181366d
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838272"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="922cf-102">&lt;wsDualHttpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="922cf-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="922cf-103">定义的安全功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="922cf-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="922cf-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="922cf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="922cf-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="922cf-105">\<bindings></span></span>  
<span data-ttu-id="922cf-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="922cf-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="922cf-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="922cf-107">\<binding></span></span>  
<span data-ttu-id="922cf-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="922cf-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="922cf-109">语法</span><span class="sxs-lookup"><span data-stu-id="922cf-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="922cf-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="922cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="922cf-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="922cf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="922cf-112">特性</span><span class="sxs-lookup"><span data-stu-id="922cf-112">Attributes</span></span>  
  
|<span data-ttu-id="922cf-113">特性</span><span class="sxs-lookup"><span data-stu-id="922cf-113">Attribute</span></span>|<span data-ttu-id="922cf-114">描述</span><span class="sxs-lookup"><span data-stu-id="922cf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="922cf-115">mode</span><span class="sxs-lookup"><span data-stu-id="922cf-115">mode</span></span>|<span data-ttu-id="922cf-116">-可选。</span><span class="sxs-lookup"><span data-stu-id="922cf-116">-   Optional.</span></span> <span data-ttu-id="922cf-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="922cf-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="922cf-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="922cf-118">The default value is `Message`.</span></span> <span data-ttu-id="922cf-119">此属性的类型为 <xref:System.ServiceModel.WSDualHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="922cf-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="922cf-120">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="922cf-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="922cf-121">值</span><span class="sxs-lookup"><span data-stu-id="922cf-121">Value</span></span>|<span data-ttu-id="922cf-122">描述</span><span class="sxs-lookup"><span data-stu-id="922cf-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="922cf-123">无</span><span class="sxs-lookup"><span data-stu-id="922cf-123">None</span></span>|<span data-ttu-id="922cf-124">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="922cf-124">Security is disabled.</span></span>|  
|<span data-ttu-id="922cf-125">消息</span><span class="sxs-lookup"><span data-stu-id="922cf-125">Message</span></span>|<span data-ttu-id="922cf-126">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="922cf-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="922cf-127">子元素</span><span class="sxs-lookup"><span data-stu-id="922cf-127">Child Elements</span></span>  
  
|<span data-ttu-id="922cf-128">元素</span><span class="sxs-lookup"><span data-stu-id="922cf-128">Element</span></span>|<span data-ttu-id="922cf-129">描述</span><span class="sxs-lookup"><span data-stu-id="922cf-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="922cf-130">\<message></span><span class="sxs-lookup"><span data-stu-id="922cf-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="922cf-131">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="922cf-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="922cf-132">此元素的类型为 <xref:System.ServiceModel.MessageSecurityOverHttp>。</span><span class="sxs-lookup"><span data-stu-id="922cf-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="922cf-133">父元素</span><span class="sxs-lookup"><span data-stu-id="922cf-133">Parent Elements</span></span>  
  
|<span data-ttu-id="922cf-134">元素</span><span class="sxs-lookup"><span data-stu-id="922cf-134">Element</span></span>|<span data-ttu-id="922cf-135">描述</span><span class="sxs-lookup"><span data-stu-id="922cf-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="922cf-136">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="922cf-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="922cf-137">定义的所有绑定功能[ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="922cf-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="922cf-138">备注</span><span class="sxs-lookup"><span data-stu-id="922cf-138">Remarks</span></span>  
 <span data-ttu-id="922cf-139">双向绑定向服务公开客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="922cf-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="922cf-140">客户端应使用安全来确保仅连接到自己信任的服务。</span><span class="sxs-lookup"><span data-stu-id="922cf-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="922cf-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="922cf-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="922cf-142">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="922cf-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="922cf-143">绑定</span><span class="sxs-lookup"><span data-stu-id="922cf-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="922cf-144">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="922cf-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="922cf-145">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="922cf-145">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="922cf-146">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="922cf-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
