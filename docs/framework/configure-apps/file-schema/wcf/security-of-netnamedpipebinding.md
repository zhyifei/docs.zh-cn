---
title: <security> 的 <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736437"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="09000-102">\<netNamedPipeBinding 的安全 > \<</span><span class="sxs-lookup"><span data-stu-id="09000-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="09000-103">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="09000-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="09000-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="09000-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="09000-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="09000-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="09000-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="09000-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="09000-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netNamedPipeBinding >** ](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="09000-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="09000-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="09000-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="09000-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<** ></span><span class="sxs-lookup"><span data-stu-id="09000-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09000-110">语法</span><span class="sxs-lookup"><span data-stu-id="09000-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09000-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="09000-111">Attributes and Elements</span></span>  
 <span data-ttu-id="09000-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="09000-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09000-113">特性</span><span class="sxs-lookup"><span data-stu-id="09000-113">Attributes</span></span>  
  
|<span data-ttu-id="09000-114">特性</span><span class="sxs-lookup"><span data-stu-id="09000-114">Attribute</span></span>|<span data-ttu-id="09000-115">描述</span><span class="sxs-lookup"><span data-stu-id="09000-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09000-116">mode</span><span class="sxs-lookup"><span data-stu-id="09000-116">mode</span></span>|<span data-ttu-id="09000-117">指定应用于此绑定的安全类型。</span><span class="sxs-lookup"><span data-stu-id="09000-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="09000-118">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="09000-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="09000-119">-None：这将禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="09000-119">-   None: This disables security.</span></span><br /><span data-ttu-id="09000-120">-Transport：使用基于传输的基础安全性提供安全性。</span><span class="sxs-lookup"><span data-stu-id="09000-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="09000-121">可以通过此模式来控制保护级别。</span><span class="sxs-lookup"><span data-stu-id="09000-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="09000-122">-默认值为 Transport。</span><span class="sxs-lookup"><span data-stu-id="09000-122">-   The default value is Transport.</span></span> <span data-ttu-id="09000-123">此属性的类型为 <xref:System.ServiceModel.NetNamedPipeSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="09000-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09000-124">子元素</span><span class="sxs-lookup"><span data-stu-id="09000-124">Child Elements</span></span>  
  
|<span data-ttu-id="09000-125">元素</span><span class="sxs-lookup"><span data-stu-id="09000-125">Element</span></span>|<span data-ttu-id="09000-126">描述</span><span class="sxs-lookup"><span data-stu-id="09000-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09000-127">传输</span><span class="sxs-lookup"><span data-stu-id="09000-127">transport</span></span>|<span data-ttu-id="09000-128">定义传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="09000-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="09000-129">此元素的类型为 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="09000-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09000-130">父元素</span><span class="sxs-lookup"><span data-stu-id="09000-130">Parent Elements</span></span>  
  
|<span data-ttu-id="09000-131">元素</span><span class="sxs-lookup"><span data-stu-id="09000-131">Element</span></span>|<span data-ttu-id="09000-132">描述</span><span class="sxs-lookup"><span data-stu-id="09000-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09000-133">绑定</span><span class="sxs-lookup"><span data-stu-id="09000-133">binding</span></span>|<span data-ttu-id="09000-134">[\<netNamedPipeBinding >](netnamedpipebinding.md)的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="09000-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09000-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="09000-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="09000-136">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="09000-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="09000-137">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="09000-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="09000-138">绑定</span><span class="sxs-lookup"><span data-stu-id="09000-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="09000-139">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="09000-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="09000-140">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="09000-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="09000-141">\<binding ></span><span class="sxs-lookup"><span data-stu-id="09000-141">\<binding></span></span>](bindings.md)
