---
title: '&lt;netNamedPipeBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
author: BrucePerlerMS
ms.openlocfilehash: e1c93fc344ea4c7dd3b801c876d59c9a799baf44
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48835812"
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="2b654-102">&lt;netNamedPipeBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="2b654-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="2b654-103">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="2b654-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="2b654-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2b654-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2b654-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2b654-105">\<bindings></span></span>  
<span data-ttu-id="2b654-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="2b654-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="2b654-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2b654-107">\<binding></span></span>  
<span data-ttu-id="2b654-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="2b654-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b654-109">语法</span><span class="sxs-lookup"><span data-stu-id="2b654-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b654-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2b654-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2b654-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2b654-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b654-112">特性</span><span class="sxs-lookup"><span data-stu-id="2b654-112">Attributes</span></span>  
  
|<span data-ttu-id="2b654-113">特性</span><span class="sxs-lookup"><span data-stu-id="2b654-113">Attribute</span></span>|<span data-ttu-id="2b654-114">描述</span><span class="sxs-lookup"><span data-stu-id="2b654-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b654-115">mode</span><span class="sxs-lookup"><span data-stu-id="2b654-115">mode</span></span>|<span data-ttu-id="2b654-116">指定应用于此绑定的安全类型。</span><span class="sxs-lookup"><span data-stu-id="2b654-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="2b654-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="2b654-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2b654-118">-None： 禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="2b654-118">-   None: This disables security.</span></span><br /><span data-ttu-id="2b654-119">-传输： 使用基础传输基于安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="2b654-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="2b654-120">可以通过此模式来控制保护级别。</span><span class="sxs-lookup"><span data-stu-id="2b654-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="2b654-121">-默认值为传输。</span><span class="sxs-lookup"><span data-stu-id="2b654-121">-   The default value is Transport.</span></span> <span data-ttu-id="2b654-122">此属性的类型为 <xref:System.ServiceModel.NetNamedPipeSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="2b654-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b654-123">子元素</span><span class="sxs-lookup"><span data-stu-id="2b654-123">Child Elements</span></span>  
  
|<span data-ttu-id="2b654-124">元素</span><span class="sxs-lookup"><span data-stu-id="2b654-124">Element</span></span>|<span data-ttu-id="2b654-125">描述</span><span class="sxs-lookup"><span data-stu-id="2b654-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b654-126">传输</span><span class="sxs-lookup"><span data-stu-id="2b654-126">transport</span></span>|<span data-ttu-id="2b654-127">定义传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="2b654-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="2b654-128">此元素的类型为 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="2b654-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b654-129">父元素</span><span class="sxs-lookup"><span data-stu-id="2b654-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2b654-130">元素</span><span class="sxs-lookup"><span data-stu-id="2b654-130">Element</span></span>|<span data-ttu-id="2b654-131">描述</span><span class="sxs-lookup"><span data-stu-id="2b654-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b654-132">绑定</span><span class="sxs-lookup"><span data-stu-id="2b654-132">binding</span></span>|<span data-ttu-id="2b654-133">绑定元素[ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2b654-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b654-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b654-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="2b654-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="2b654-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="2b654-136">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="2b654-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="2b654-137">绑定</span><span class="sxs-lookup"><span data-stu-id="2b654-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2b654-138">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="2b654-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="2b654-139">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="2b654-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="2b654-140">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2b654-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
