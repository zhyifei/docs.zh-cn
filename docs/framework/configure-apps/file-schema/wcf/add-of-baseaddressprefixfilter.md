---
title: <add> 的 <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: 8fdae02b558708a9b3f4535123752dce12dd5cf5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153135"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="fdfb9-102">\<添加>的\<基地址前缀筛选器></span><span class="sxs-lookup"><span data-stu-id="fdfb9-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="fdfb9-103">表示指定直通筛选器的配置元素，该筛选器提供了在 IIS 中托管 Windows 通信基础 （WCF） 应用程序时选择相应 Internet 信息服务 （IIS） 绑定的机制。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
<span data-ttu-id="fdfb9-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fdfb9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fdfb9-105">&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fdfb9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fdfb9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<服务托管环境>**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="fdfb9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="fdfb9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<基本地址前缀筛选器>**](baseaddressprefixfilters.md)</span><span class="sxs-lookup"><span data-stu-id="fdfb9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)</span></span>\
<span data-ttu-id="fdfb9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**</span><span class="sxs-lookup"><span data-stu-id="fdfb9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdfb9-109">语法</span><span class="sxs-lookup"><span data-stu-id="fdfb9-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdfb9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fdfb9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fdfb9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdfb9-112">属性</span><span class="sxs-lookup"><span data-stu-id="fdfb9-112">Attributes</span></span>  
  
|<span data-ttu-id="fdfb9-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="fdfb9-113">Attribute</span></span>|<span data-ttu-id="fdfb9-114">说明</span><span class="sxs-lookup"><span data-stu-id="fdfb9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fdfb9-115">前缀</span><span class="sxs-lookup"><span data-stu-id="fdfb9-115">prefix</span></span>|<span data-ttu-id="fdfb9-116">用于与基址的一部分进行匹配的 URI。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-116">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fdfb9-117">子元素</span><span class="sxs-lookup"><span data-stu-id="fdfb9-117">Child Elements</span></span>  
 <span data-ttu-id="fdfb9-118">无。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fdfb9-119">父元素</span><span class="sxs-lookup"><span data-stu-id="fdfb9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fdfb9-120">元素</span><span class="sxs-lookup"><span data-stu-id="fdfb9-120">Element</span></span>|<span data-ttu-id="fdfb9-121">说明</span><span class="sxs-lookup"><span data-stu-id="fdfb9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdfb9-122">\<基本地址前缀筛选器></span><span class="sxs-lookup"><span data-stu-id="fdfb9-122">\<baseAddressPrefixFilters></span></span>](baseaddressprefixfilters.md)|<span data-ttu-id="fdfb9-123">指定传递筛选器的配置元素的集合，这些元素提供了在 IIS 中托管 Windows 通信基础 （WCF） 应用程序时选择适当 IIS 绑定的机制。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-123">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdfb9-124">备注</span><span class="sxs-lookup"><span data-stu-id="fdfb9-124">Remarks</span></span>  
 <span data-ttu-id="fdfb9-125">前缀筛选器为共享的宿主提供程序提供一种指定服务要使用的 URI 的方法。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-125">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="fdfb9-126">它使得共享主机可以在同一站点上通过同一方案的不同基址承载多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-126">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="fdfb9-127">IIS 网站是包含虚拟目录的虚拟应用程序的容器。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-127">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="fdfb9-128">可通过一个或多个 IIS 绑定访问站点上的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-128">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="fdfb9-129">IIS 绑定提供两条信息：绑定协议和绑定信息。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-129">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="fdfb9-130">绑定协议（例如 HTTP）定义发生通信所基于的方案，而绑定信息（例如 IP 地址、端口、主机头）包含用于访问站点的数据。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-130">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="fdfb9-131">IIS 支持为每个站点指定多个 IIS 绑定，这会导致每个方案有多个基址。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-131">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="fdfb9-132">由于站点下托管的 WCF 服务允许为每个方案仅绑定到一个基本地址，因此可以使用前缀筛选器功能来选择托管服务所需的基本地址。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-132">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="fdfb9-133">根据可选前缀列表筛选器筛选 IIS 提供的传入基址。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-133">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="fdfb9-134">例如，您的网站可以包含以下基本地址：</span><span class="sxs-lookup"><span data-stu-id="fdfb9-134">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="fdfb9-135">可以使用下面的配置文件在 appdomain 级指定前缀筛选器。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-135">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="fdfb9-136">在此示例中，`net.tcp://test1.fabrikam.com:8000` 和 `http://test2.fabrikam.com:9000` 是允许传递的各自方案的唯一基址。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-136">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="fdfb9-137">默认情况下，未指定前缀时，将传递所有地址。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-137">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="fdfb9-138">而指定前缀后，将只允许传递该方案的匹配基址。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-138">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdfb9-139">筛选器不支持任何通配符。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-139">The filter does not support any wildcards.</span></span> <span data-ttu-id="fdfb9-140">此外，IIS 提供的基址可能有绑定到在 `baseAddressPrefixFilters` 列表中未列出的其他方案的地址。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-140">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="fdfb9-141">不会筛选出这些地址。</span><span class="sxs-lookup"><span data-stu-id="fdfb9-141">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfb9-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdfb9-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="fdfb9-143">承载</span><span class="sxs-lookup"><span data-stu-id="fdfb9-143">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
