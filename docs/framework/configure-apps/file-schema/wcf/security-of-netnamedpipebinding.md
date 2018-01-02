---
title: "&lt;netNamedPipeBinding&gt; 的 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: fb5d1d3a767a9f4034473baad271c40677cedca5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="bfde0-102">&lt;netNamedPipeBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="bfde0-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="bfde0-103">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="bfde0-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="bfde0-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bfde0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bfde0-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="bfde0-105">\<bindings></span></span>  
<span data-ttu-id="bfde0-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="bfde0-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="bfde0-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="bfde0-107">\<binding></span></span>  
<span data-ttu-id="bfde0-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="bfde0-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfde0-109">语法</span><span class="sxs-lookup"><span data-stu-id="bfde0-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfde0-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bfde0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bfde0-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bfde0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfde0-112">特性</span><span class="sxs-lookup"><span data-stu-id="bfde0-112">Attributes</span></span>  
  
|<span data-ttu-id="bfde0-113">特性</span><span class="sxs-lookup"><span data-stu-id="bfde0-113">Attribute</span></span>|<span data-ttu-id="bfde0-114">描述</span><span class="sxs-lookup"><span data-stu-id="bfde0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bfde0-115">mode</span><span class="sxs-lookup"><span data-stu-id="bfde0-115">mode</span></span>|<span data-ttu-id="bfde0-116">指定应用于此绑定的安全类型。</span><span class="sxs-lookup"><span data-stu-id="bfde0-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="bfde0-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="bfde0-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bfde0-118">-None： 禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="bfde0-118">-   None: This disables security.</span></span><br /><span data-ttu-id="bfde0-119">-传输： 使用基础的基于的传输安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="bfde0-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="bfde0-120">可以通过此模式来控制保护级别。</span><span class="sxs-lookup"><span data-stu-id="bfde0-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="bfde0-121">-默认值为 Transport。</span><span class="sxs-lookup"><span data-stu-id="bfde0-121">-   The default value is Transport.</span></span> <span data-ttu-id="bfde0-122">此属性的类型为 <xref:System.ServiceModel.NetNamedPipeSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="bfde0-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfde0-123">子元素</span><span class="sxs-lookup"><span data-stu-id="bfde0-123">Child Elements</span></span>  
  
|<span data-ttu-id="bfde0-124">元素</span><span class="sxs-lookup"><span data-stu-id="bfde0-124">Element</span></span>|<span data-ttu-id="bfde0-125">描述</span><span class="sxs-lookup"><span data-stu-id="bfde0-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfde0-126">传输</span><span class="sxs-lookup"><span data-stu-id="bfde0-126">transport</span></span>|<span data-ttu-id="bfde0-127">定义传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="bfde0-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="bfde0-128">此元素的类型为 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="bfde0-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bfde0-129">父元素</span><span class="sxs-lookup"><span data-stu-id="bfde0-129">Parent Elements</span></span>  
  
|<span data-ttu-id="bfde0-130">元素</span><span class="sxs-lookup"><span data-stu-id="bfde0-130">Element</span></span>|<span data-ttu-id="bfde0-131">描述</span><span class="sxs-lookup"><span data-stu-id="bfde0-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfde0-132">绑定</span><span class="sxs-lookup"><span data-stu-id="bfde0-132">binding</span></span>|<span data-ttu-id="bfde0-133">绑定元素[ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)。</span><span class="sxs-lookup"><span data-stu-id="bfde0-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfde0-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfde0-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="bfde0-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="bfde0-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="bfde0-136">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="bfde0-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="bfde0-137">绑定</span><span class="sxs-lookup"><span data-stu-id="bfde0-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bfde0-138">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="bfde0-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="bfde0-139">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="bfde0-139">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="bfde0-140">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="bfde0-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
