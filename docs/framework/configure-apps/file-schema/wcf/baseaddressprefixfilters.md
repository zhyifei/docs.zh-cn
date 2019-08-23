---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 8a59f651318e18411b1485fc4eebeb7a550afca0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919859"
---
# <a name="baseaddressprefixfilters"></a><span data-ttu-id="b80cd-101">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="b80cd-101">\<baseAddressPrefixFilters></span></span>
<span data-ttu-id="b80cd-102">表示配置元素的集合, 这些元素指定通过筛选器, 这些筛选器提供一种机制, 用于在 IIS 中承载 Windows Communication Foundation (WCF) 应用程序时选择适当的 Internet Information Services (IIS) 绑定。</span><span class="sxs-lookup"><span data-stu-id="b80cd-102">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b80cd-103">\<baseAddressPrefixFilters > 无法识别 "localhost", 请改为使用完全限定的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="b80cd-103">\<baseAddressPrefixFilters> does not recognize "localhost", use the fully qualified machine name instead.</span></span>  
  
 <span data-ttu-id="b80cd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b80cd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b80cd-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="b80cd-105">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80cd-106">语法</span><span class="sxs-lookup"><span data-stu-id="b80cd-106">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b80cd-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b80cd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b80cd-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b80cd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b80cd-109">特性</span><span class="sxs-lookup"><span data-stu-id="b80cd-109">Attributes</span></span>  
 <span data-ttu-id="b80cd-110">无。</span><span class="sxs-lookup"><span data-stu-id="b80cd-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b80cd-111">子元素</span><span class="sxs-lookup"><span data-stu-id="b80cd-111">Child Elements</span></span>  
  
|<span data-ttu-id="b80cd-112">元素</span><span class="sxs-lookup"><span data-stu-id="b80cd-112">Element</span></span>|<span data-ttu-id="b80cd-113">描述</span><span class="sxs-lookup"><span data-stu-id="b80cd-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b80cd-114">\<add></span><span class="sxs-lookup"><span data-stu-id="b80cd-114">\<add></span></span>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="b80cd-115">添加一个配置元素，用于指定服务主机所使用的基址的前缀筛选器。</span><span class="sxs-lookup"><span data-stu-id="b80cd-115">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b80cd-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b80cd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b80cd-117">元素</span><span class="sxs-lookup"><span data-stu-id="b80cd-117">Element</span></span>|<span data-ttu-id="b80cd-118">描述</span><span class="sxs-lookup"><span data-stu-id="b80cd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b80cd-119">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="b80cd-119">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="b80cd-120">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="b80cd-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b80cd-121">备注</span><span class="sxs-lookup"><span data-stu-id="b80cd-121">Remarks</span></span>  
 <span data-ttu-id="b80cd-122">前缀筛选器为共享的宿主提供程序提供一种指定服务要使用的 URI 的方法。</span><span class="sxs-lookup"><span data-stu-id="b80cd-122">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="b80cd-123">它使得共享主机可以在同一站点上通过同一方案的不同基址承载多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b80cd-123">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="b80cd-124">IIS 网站是包含虚拟目录的虚拟应用程序的容器。</span><span class="sxs-lookup"><span data-stu-id="b80cd-124">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="b80cd-125">可通过一个或多个 IIS 绑定访问站点上的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b80cd-125">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="b80cd-126">IIS 绑定提供两条信息：绑定协议和绑定信息。</span><span class="sxs-lookup"><span data-stu-id="b80cd-126">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="b80cd-127">绑定协议（例如 HTTP）定义发生通信所基于的方案，而绑定信息（例如 IP 地址、端口、主机头）包含用于访问站点的数据。</span><span class="sxs-lookup"><span data-stu-id="b80cd-127">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="b80cd-128">IIS 支持为每个站点指定多个 IIS 绑定，这会导致每个方案有多个基址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-128">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="b80cd-129">因为在站点下承载的 WCF 服务只允许绑定到每个方案的一个基址, 所以您可以使用前缀筛选器功能选取所需的承载服务的基址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-129">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="b80cd-130">根据可选前缀列表筛选器筛选 IIS 提供的传入基址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-130">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="b80cd-131">例如，您的站点可包含以下基址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-131">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="b80cd-132">可以使用下面的配置文件在 appdomain 级指定前缀筛选器。</span><span class="sxs-lookup"><span data-stu-id="b80cd-132">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="b80cd-133">在此示例中，`net.tcp://test1.fabrikam.com:8000` 和 `http://test2.fabrikam.com:9000` 是允许传递的各自方案的唯一基址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-133">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="b80cd-134">默认情况下，未指定前缀时，将传递所有地址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-134">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="b80cd-135">而指定前缀后，将只允许传递该方案的匹配基址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-135">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b80cd-136">筛选器不支持任何通配符。</span><span class="sxs-lookup"><span data-stu-id="b80cd-136">The filter does not support any wildcards.</span></span> <span data-ttu-id="b80cd-137">此外，IIS 提供的基址可能有绑定到在 `baseAddressPrefixFilters` 列表中未列出的其他方案的地址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-137">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="b80cd-138">不会筛选出这些地址。</span><span class="sxs-lookup"><span data-stu-id="b80cd-138">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80cd-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b80cd-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="b80cd-140">承载</span><span class="sxs-lookup"><span data-stu-id="b80cd-140">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
