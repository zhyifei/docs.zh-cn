---
title: <security> 的 <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: b6a1c952b1ae65c8fb6f17237b5c15f3a8d4844a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399753"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="6b665-102">\<wsDualHttpBinding 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="6b665-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="6b665-103">定义[ \<wsDualHttpBinding >](wsdualhttpbinding.md)的安全功能。</span><span class="sxs-lookup"><span data-stu-id="6b665-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
<span data-ttu-id="6b665-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b665-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6b665-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6b665-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6b665-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6b665-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6b665-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsDualHttpBinding >** ](wsdualhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6b665-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)</span></span>\
<span data-ttu-id="6b665-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="6b665-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6b665-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<安全 >**</span><span class="sxs-lookup"><span data-stu-id="6b665-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b665-110">语法</span><span class="sxs-lookup"><span data-stu-id="6b665-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b665-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6b665-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6b665-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6b665-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b665-113">特性</span><span class="sxs-lookup"><span data-stu-id="6b665-113">Attributes</span></span>  
  
|<span data-ttu-id="6b665-114">特性</span><span class="sxs-lookup"><span data-stu-id="6b665-114">Attribute</span></span>|<span data-ttu-id="6b665-115">描述</span><span class="sxs-lookup"><span data-stu-id="6b665-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b665-116">mode</span><span class="sxs-lookup"><span data-stu-id="6b665-116">mode</span></span>|<span data-ttu-id="6b665-117">可有可无.</span><span class="sxs-lookup"><span data-stu-id="6b665-117">-   Optional.</span></span> <span data-ttu-id="6b665-118">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="6b665-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="6b665-119">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="6b665-119">The default value is `Message`.</span></span> <span data-ttu-id="6b665-120">此属性的类型为 <xref:System.ServiceModel.WSDualHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="6b665-120">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="6b665-121">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="6b665-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="6b665-122">值</span><span class="sxs-lookup"><span data-stu-id="6b665-122">Value</span></span>|<span data-ttu-id="6b665-123">描述</span><span class="sxs-lookup"><span data-stu-id="6b665-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6b665-124">无</span><span class="sxs-lookup"><span data-stu-id="6b665-124">None</span></span>|<span data-ttu-id="6b665-125">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="6b665-125">Security is disabled.</span></span>|  
|<span data-ttu-id="6b665-126">消息</span><span class="sxs-lookup"><span data-stu-id="6b665-126">Message</span></span>|<span data-ttu-id="6b665-127">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="6b665-127">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b665-128">子元素</span><span class="sxs-lookup"><span data-stu-id="6b665-128">Child Elements</span></span>  
  
|<span data-ttu-id="6b665-129">元素</span><span class="sxs-lookup"><span data-stu-id="6b665-129">Element</span></span>|<span data-ttu-id="6b665-130">描述</span><span class="sxs-lookup"><span data-stu-id="6b665-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b665-131">\<message></span><span class="sxs-lookup"><span data-stu-id="6b665-131">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="6b665-132">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="6b665-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="6b665-133">此元素的类型为 <xref:System.ServiceModel.MessageSecurityOverHttp>。</span><span class="sxs-lookup"><span data-stu-id="6b665-133">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b665-134">父元素</span><span class="sxs-lookup"><span data-stu-id="6b665-134">Parent Elements</span></span>  
  
|<span data-ttu-id="6b665-135">元素</span><span class="sxs-lookup"><span data-stu-id="6b665-135">Element</span></span>|<span data-ttu-id="6b665-136">描述</span><span class="sxs-lookup"><span data-stu-id="6b665-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b665-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="6b665-137">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="6b665-138">定义[ \<wsDualHttpBinding >](wsdualhttpbinding.md)的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="6b665-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b665-139">备注</span><span class="sxs-lookup"><span data-stu-id="6b665-139">Remarks</span></span>  
 <span data-ttu-id="6b665-140">双向绑定向服务公开客户端的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6b665-140">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="6b665-141">客户端应使用安全来确保仅连接到自己信任的服务。</span><span class="sxs-lookup"><span data-stu-id="6b665-141">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b665-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b665-142">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="6b665-143">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="6b665-143">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6b665-144">绑定</span><span class="sxs-lookup"><span data-stu-id="6b665-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6b665-145">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="6b665-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6b665-146">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="6b665-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6b665-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="6b665-147">\<binding></span></span>](../../../misc/binding.md)
