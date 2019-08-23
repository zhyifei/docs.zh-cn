---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 4fa6916437bb569029efe270ba8296703d89c539
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938909"
---
# <a name="systemservicemodel"></a><span data-ttu-id="d82d5-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d82d5-102">\<system.serviceModel></span></span>
<span data-ttu-id="d82d5-103">此配置节包含所有 Windows Communication Foundation (WCF) 配置元素。</span><span class="sxs-lookup"><span data-stu-id="d82d5-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d82d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="d82d5-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d82d5-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d82d5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d82d5-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d82d5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d82d5-107">特性</span><span class="sxs-lookup"><span data-stu-id="d82d5-107">Attributes</span></span>  
 <span data-ttu-id="d82d5-108">无</span><span class="sxs-lookup"><span data-stu-id="d82d5-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d82d5-109">子元素</span><span class="sxs-lookup"><span data-stu-id="d82d5-109">Child Elements</span></span>  
  
|<span data-ttu-id="d82d5-110">元素</span><span class="sxs-lookup"><span data-stu-id="d82d5-110">Element</span></span>|<span data-ttu-id="d82d5-111">描述</span><span class="sxs-lookup"><span data-stu-id="d82d5-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d82d5-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d82d5-112">\<behaviors></span></span>](behaviors.md)|<span data-ttu-id="d82d5-113">此节定义名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="d82d5-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="d82d5-114">每个集合分别定义终结点和服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="d82d5-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="d82d5-115">每个行为元素由其唯一的 `name` 属性标识。</span><span class="sxs-lookup"><span data-stu-id="d82d5-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="d82d5-116">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d82d5-116">\<bindings></span></span>](bindings.md)|<span data-ttu-id="d82d5-117">此节包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="d82d5-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="d82d5-118">每一项均由其唯一的 `name` 进行标识。</span><span class="sxs-lookup"><span data-stu-id="d82d5-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="d82d5-119">服务通过用 `name` 与绑定进行链接来使用绑定。</span><span class="sxs-lookup"><span data-stu-id="d82d5-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="d82d5-120">\<client></span><span class="sxs-lookup"><span data-stu-id="d82d5-120">\<client></span></span>](client.md)|<span data-ttu-id="d82d5-121">此节包含客户端用来连接到服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="d82d5-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="d82d5-122">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="d82d5-122">\<comContracts></span></span>](comcontracts.md)|<span data-ttu-id="d82d5-123">此节定义支持 WCF 和 COM 互操作的 COM 协定。</span><span class="sxs-lookup"><span data-stu-id="d82d5-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="d82d5-124">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="d82d5-124">\<commonBehaviors></span></span>](commonbehaviors.md)|<span data-ttu-id="d82d5-125">此节只能在 machine.config 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="d82d5-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="d82d5-126">它定义了名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="d82d5-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="d82d5-127">每个集合分别定义计算机上所有 WCF 终结点和服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="d82d5-127">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="d82d5-128">如果在`<commonBehaviors>`和`<behaviors>`节中定义了某个行为, 则会优先使用\<"行为" > 部分中的行为。</span><span class="sxs-lookup"><span data-stu-id="d82d5-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="d82d5-129">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="d82d5-129">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="d82d5-130">此节包含 WCF 的诊断功能设置。</span><span class="sxs-lookup"><span data-stu-id="d82d5-130">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="d82d5-131">用户可以启用/禁用跟踪、性能计数器和 WMI 提供程序，还可以添加自定义消息筛选器。</span><span class="sxs-lookup"><span data-stu-id="d82d5-131">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="d82d5-132">\<扩展 ></span><span class="sxs-lookup"><span data-stu-id="d82d5-132">\<extensions></span></span>](extensions-section.md)|<span data-ttu-id="d82d5-133">此节包含一个扩展集合，这些扩展使用户能够创建扩展的用户定义绑定、行为和其他方面。</span><span class="sxs-lookup"><span data-stu-id="d82d5-133">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="d82d5-134">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="d82d5-134">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="d82d5-135">本部分定义传输协议方案 (例如, http、net.tcp、net.pipe 等) 和 WCF 绑定之间的一组默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="d82d5-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="d82d5-136">\<routing></span><span class="sxs-lookup"><span data-stu-id="d82d5-136">\<routing></span></span>](routing.md)|<span data-ttu-id="d82d5-137">本节定义一组路由筛选器, 这些筛选器确定计算传入消息时要使用<xref:System.ServiceModel.Dispatcher.MessageFilter>的 Windows Communication Foundation (WCF) 的类型, 以及用于定义在筛选器匹配项。</span><span class="sxs-lookup"><span data-stu-id="d82d5-137">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="d82d5-138">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="d82d5-138">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="d82d5-139">此节定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="d82d5-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="d82d5-140">如果此节为空，则使用默认类型。</span><span class="sxs-lookup"><span data-stu-id="d82d5-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="d82d5-141">\<services></span><span class="sxs-lookup"><span data-stu-id="d82d5-141">\<services></span></span>](services.md)|<span data-ttu-id="d82d5-142">此节包含服务的集合。</span><span class="sxs-lookup"><span data-stu-id="d82d5-142">The section contains a collection of services.</span></span> <span data-ttu-id="d82d5-143">对于程序集中定义的每个服务，此元素包含一个为服务指定设置的 `service` 元素。</span><span class="sxs-lookup"><span data-stu-id="d82d5-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="d82d5-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d82d5-144">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d82d5-145">此节定义一个标准终结点集合，这些终结点是预配置的可重用终结点。</span><span class="sxs-lookup"><span data-stu-id="d82d5-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="d82d5-146">标准终结点具有一个或多个设置为固定值的地址、绑定和协定特性。</span><span class="sxs-lookup"><span data-stu-id="d82d5-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="d82d5-147">例如，发现终结点具有固定的协定。</span><span class="sxs-lookup"><span data-stu-id="d82d5-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="d82d5-148">此外，还可以使用标准终结点用新属性扩展服务终结点，这与定义自定义绑定相似。</span><span class="sxs-lookup"><span data-stu-id="d82d5-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="d82d5-149">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d82d5-149">\<tracking></span></span>](tracking-of-wcf.md)|<span data-ttu-id="d82d5-150">本部分为工作流服务定义跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="d82d5-150">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d82d5-151">父元素</span><span class="sxs-lookup"><span data-stu-id="d82d5-151">Parent Elements</span></span>  
  
|<span data-ttu-id="d82d5-152">元素</span><span class="sxs-lookup"><span data-stu-id="d82d5-152">Element</span></span>|<span data-ttu-id="d82d5-153">描述</span><span class="sxs-lookup"><span data-stu-id="d82d5-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d82d5-154">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d82d5-154">\<configuration></span></span>|<span data-ttu-id="d82d5-155">.NET 配置文件中的所有配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="d82d5-155">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d82d5-156">备注</span><span class="sxs-lookup"><span data-stu-id="d82d5-156">Remarks</span></span>  
 <span data-ttu-id="d82d5-157">WCF 不会向其他产品的配置节添加元素。</span><span class="sxs-lookup"><span data-stu-id="d82d5-157">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="d82d5-158">WCF 服务在配置文件的`services`部分中定义。</span><span class="sxs-lookup"><span data-stu-id="d82d5-158">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="d82d5-159">程序集可以包含任意多个服务。</span><span class="sxs-lookup"><span data-stu-id="d82d5-159">An assembly can contain any number of services.</span></span> <span data-ttu-id="d82d5-160">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="d82d5-160">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="d82d5-161">本节及其内容定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="d82d5-161">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="d82d5-162">只有服务的 `name` 属性是必需的。</span><span class="sxs-lookup"><span data-stu-id="d82d5-162">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="d82d5-163">默认情况下，服务的名称描述用于实现服务的基础 CLR 类型；但是，您可以更改 <xref:System.ServiceModel.ServiceContractAttribute> 上的 ConfigurationName 属性以重写 CLR 类型需求。</span><span class="sxs-lookup"><span data-stu-id="d82d5-163">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="d82d5-164">`behaviorConfiguration` 属性是可选项。</span><span class="sxs-lookup"><span data-stu-id="d82d5-164">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="d82d5-165">它标识服务所使用的服务行为。</span><span class="sxs-lookup"><span data-stu-id="d82d5-165">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="d82d5-166">此属性指定的行为必须链接到同一配置文件的范围（即，同一文件或父文件）中定义的服务行为。</span><span class="sxs-lookup"><span data-stu-id="d82d5-166">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="d82d5-167">每个服务将公开 `endpoint` 元素中定义的一个或多个终结点。</span><span class="sxs-lookup"><span data-stu-id="d82d5-167">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="d82d5-168">每个终结点都具有自己的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="d82d5-168">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="d82d5-169">配置文件中使用的所有绑定都必须在该文件的范围内定义。</span><span class="sxs-lookup"><span data-stu-id="d82d5-169">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="d82d5-170">绑定通过 `name` 和 `bindingConfiguration` 属性的组合链接到终结点。</span><span class="sxs-lookup"><span data-stu-id="d82d5-170">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="d82d5-171">`binding` 属性定义在哪个节中定义绑定。</span><span class="sxs-lookup"><span data-stu-id="d82d5-171">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="d82d5-172">`bindingConfiguration` 属性定义使用绑定节中的哪个已配置绑定。</span><span class="sxs-lookup"><span data-stu-id="d82d5-172">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="d82d5-173">绑定节可以定义若干个已配置的绑定。</span><span class="sxs-lookup"><span data-stu-id="d82d5-173">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d82d5-174">示例</span><span class="sxs-lookup"><span data-stu-id="d82d5-174">Example</span></span>  
 <span data-ttu-id="d82d5-175">下面是 WCF 配置文件的示例。</span><span class="sxs-lookup"><span data-stu-id="d82d5-175">This is an example of a WCF configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="d82d5-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="d82d5-176">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
