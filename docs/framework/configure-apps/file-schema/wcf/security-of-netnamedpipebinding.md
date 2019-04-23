---
title: <security> 的 <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: fa31dda3274c9768694bdf5232f31554899e1d82
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203387"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="19a14-102">\<安全 > 的\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="19a14-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="19a14-103">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="19a14-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="19a14-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="19a14-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="19a14-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="19a14-105">\<bindings></span></span>  
<span data-ttu-id="19a14-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="19a14-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="19a14-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="19a14-107">\<binding></span></span>  
<span data-ttu-id="19a14-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="19a14-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a14-109">语法</span><span class="sxs-lookup"><span data-stu-id="19a14-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19a14-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="19a14-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19a14-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="19a14-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19a14-112">特性</span><span class="sxs-lookup"><span data-stu-id="19a14-112">Attributes</span></span>  
  
|<span data-ttu-id="19a14-113">特性</span><span class="sxs-lookup"><span data-stu-id="19a14-113">Attribute</span></span>|<span data-ttu-id="19a14-114">描述</span><span class="sxs-lookup"><span data-stu-id="19a14-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19a14-115">mode</span><span class="sxs-lookup"><span data-stu-id="19a14-115">mode</span></span>|<span data-ttu-id="19a14-116">指定应用于此绑定的安全类型。</span><span class="sxs-lookup"><span data-stu-id="19a14-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="19a14-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="19a14-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="19a14-118">-None:这将禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="19a14-118">-   None: This disables security.</span></span><br /><span data-ttu-id="19a14-119">-传输：使用基础传输基于安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="19a14-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="19a14-120">可以通过此模式来控制保护级别。</span><span class="sxs-lookup"><span data-stu-id="19a14-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="19a14-121">-默认值为传输。</span><span class="sxs-lookup"><span data-stu-id="19a14-121">-   The default value is Transport.</span></span> <span data-ttu-id="19a14-122">此属性的类型为 <xref:System.ServiceModel.NetNamedPipeSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="19a14-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19a14-123">子元素</span><span class="sxs-lookup"><span data-stu-id="19a14-123">Child Elements</span></span>  
  
|<span data-ttu-id="19a14-124">元素</span><span class="sxs-lookup"><span data-stu-id="19a14-124">Element</span></span>|<span data-ttu-id="19a14-125">描述</span><span class="sxs-lookup"><span data-stu-id="19a14-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19a14-126">传输</span><span class="sxs-lookup"><span data-stu-id="19a14-126">transport</span></span>|<span data-ttu-id="19a14-127">定义传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="19a14-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="19a14-128">此元素的类型为 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="19a14-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19a14-129">父元素</span><span class="sxs-lookup"><span data-stu-id="19a14-129">Parent Elements</span></span>  
  
|<span data-ttu-id="19a14-130">元素</span><span class="sxs-lookup"><span data-stu-id="19a14-130">Element</span></span>|<span data-ttu-id="19a14-131">描述</span><span class="sxs-lookup"><span data-stu-id="19a14-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19a14-132">绑定</span><span class="sxs-lookup"><span data-stu-id="19a14-132">binding</span></span>|<span data-ttu-id="19a14-133">绑定元素[ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)。</span><span class="sxs-lookup"><span data-stu-id="19a14-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19a14-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="19a14-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="19a14-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="19a14-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="19a14-136">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="19a14-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="19a14-137">绑定</span><span class="sxs-lookup"><span data-stu-id="19a14-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="19a14-138">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="19a14-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="19a14-139">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="19a14-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="19a14-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="19a14-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
