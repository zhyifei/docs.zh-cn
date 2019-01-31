---
title: <security> 的 <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: ee2c4161f70c01dc09ac36bbcf6a234f822682d0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265295"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="02c0c-102">\<安全 > 的\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="02c0c-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="02c0c-103">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="02c0c-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="02c0c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="02c0c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="02c0c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="02c0c-105">\<bindings></span></span>  
<span data-ttu-id="02c0c-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="02c0c-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="02c0c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="02c0c-107">\<binding></span></span>  
<span data-ttu-id="02c0c-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="02c0c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c0c-109">语法</span><span class="sxs-lookup"><span data-stu-id="02c0c-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02c0c-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02c0c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="02c0c-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="02c0c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02c0c-112">特性</span><span class="sxs-lookup"><span data-stu-id="02c0c-112">Attributes</span></span>  
  
|<span data-ttu-id="02c0c-113">特性</span><span class="sxs-lookup"><span data-stu-id="02c0c-113">Attribute</span></span>|<span data-ttu-id="02c0c-114">描述</span><span class="sxs-lookup"><span data-stu-id="02c0c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02c0c-115">mode</span><span class="sxs-lookup"><span data-stu-id="02c0c-115">mode</span></span>|<span data-ttu-id="02c0c-116">指定应用于此绑定的安全类型。</span><span class="sxs-lookup"><span data-stu-id="02c0c-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="02c0c-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="02c0c-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="02c0c-118">-None:这将禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="02c0c-118">-   None: This disables security.</span></span><br /><span data-ttu-id="02c0c-119">-传输：使用基础传输基于安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="02c0c-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="02c0c-120">可以通过此模式来控制保护级别。</span><span class="sxs-lookup"><span data-stu-id="02c0c-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="02c0c-121">-默认值为传输。</span><span class="sxs-lookup"><span data-stu-id="02c0c-121">-   The default value is Transport.</span></span> <span data-ttu-id="02c0c-122">此属性的类型为 <xref:System.ServiceModel.NetNamedPipeSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="02c0c-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02c0c-123">子元素</span><span class="sxs-lookup"><span data-stu-id="02c0c-123">Child Elements</span></span>  
  
|<span data-ttu-id="02c0c-124">元素</span><span class="sxs-lookup"><span data-stu-id="02c0c-124">Element</span></span>|<span data-ttu-id="02c0c-125">描述</span><span class="sxs-lookup"><span data-stu-id="02c0c-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02c0c-126">传输</span><span class="sxs-lookup"><span data-stu-id="02c0c-126">transport</span></span>|<span data-ttu-id="02c0c-127">定义传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="02c0c-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="02c0c-128">此元素的类型为 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="02c0c-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02c0c-129">父元素</span><span class="sxs-lookup"><span data-stu-id="02c0c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="02c0c-130">元素</span><span class="sxs-lookup"><span data-stu-id="02c0c-130">Element</span></span>|<span data-ttu-id="02c0c-131">描述</span><span class="sxs-lookup"><span data-stu-id="02c0c-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02c0c-132">绑定</span><span class="sxs-lookup"><span data-stu-id="02c0c-132">binding</span></span>|<span data-ttu-id="02c0c-133">绑定元素[ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)。</span><span class="sxs-lookup"><span data-stu-id="02c0c-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02c0c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="02c0c-134">See also</span></span>
- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="02c0c-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="02c0c-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="02c0c-136">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="02c0c-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="02c0c-137">绑定</span><span class="sxs-lookup"><span data-stu-id="02c0c-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="02c0c-138">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="02c0c-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="02c0c-139">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="02c0c-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="02c0c-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="02c0c-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
