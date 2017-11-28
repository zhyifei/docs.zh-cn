---
title: '&lt;system.serviceModel&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 563825a92dbdeb90cd17d107795525686b7b4080
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemservicemodelgt"></a><span data-ttu-id="8eb2c-102">&lt;system.serviceModel&gt;</span><span class="sxs-lookup"><span data-stu-id="8eb2c-102">&lt;system.serviceModel&gt;</span></span>
<span data-ttu-id="8eb2c-103">此配置节包含所有 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] ServiceModel 配置元素。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-103">This configuration section contains all the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eb2c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8eb2c-104">Syntax</span></span>  
  
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
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8eb2c-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8eb2c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8eb2c-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8eb2c-107">特性</span><span class="sxs-lookup"><span data-stu-id="8eb2c-107">Attributes</span></span>  
 <span data-ttu-id="8eb2c-108">无</span><span class="sxs-lookup"><span data-stu-id="8eb2c-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8eb2c-109">子元素</span><span class="sxs-lookup"><span data-stu-id="8eb2c-109">Child Elements</span></span>  
  
|<span data-ttu-id="8eb2c-110">元素</span><span class="sxs-lookup"><span data-stu-id="8eb2c-110">Element</span></span>|<span data-ttu-id="8eb2c-111">描述</span><span class="sxs-lookup"><span data-stu-id="8eb2c-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8eb2c-112">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|<span data-ttu-id="8eb2c-113">此节定义名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="8eb2c-114">每个集合分别定义终结点和服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="8eb2c-115">每个行为元素由其唯一的 `name` 属性标识。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="8eb2c-116">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-116">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="8eb2c-117">此节包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="8eb2c-118">每一项均由其唯一的 `name` 进行标识。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="8eb2c-119">服务通过用 `name` 与绑定进行链接来使用绑定。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="8eb2c-120">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-120">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="8eb2c-121">此节包含客户端用来连接到服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="8eb2c-122">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-122">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|<span data-ttu-id="8eb2c-123">此节定义支持 WCF 和 COM 互操作的 COM 协定。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="8eb2c-124">\<commonBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-124">\<commonBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|<span data-ttu-id="8eb2c-125">此节只能在 machine.config 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="8eb2c-126">它定义了名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="8eb2c-127">每个集合分别定义计算机上所有 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 终结点和服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-127">Each collection defines behavior elements consumed by all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="8eb2c-128">如果中都定义一个行为`<commonBehaviors>`和`<behaviors>`部分中的行为\<行为 > 部分优先。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="8eb2c-129">\<扩展 ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-129">\<extensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|<span data-ttu-id="8eb2c-130">此节包含一个扩展集合，这些扩展使用户能够创建扩展的用户定义绑定、行为和其他方面。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-130">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="8eb2c-131">\<诊断 ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-131">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="8eb2c-132">此节包含 WCF 的诊断功能设置。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-132">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="8eb2c-133">用户可以启用/禁用跟踪、性能计数器和 WMI 提供程序，还可以添加自定义消息筛选器。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-133">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="8eb2c-134">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-134">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="8eb2c-135">此节定义一组的传输协议方案 （例如，http、 net.tcp、 net.pipe 等） 和 WCF 绑定之间的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="8eb2c-136">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-136">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="8eb2c-137">此节定义一组路由筛选器，这些筛选器确定计算传入消息时使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 的类型，以及用于定义在筛选器匹配时消息发送到的目标终结点的路由表。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-137">This section defines a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="8eb2c-138">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-138">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="8eb2c-139">此节定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="8eb2c-140">如果此节为空，则使用默认类型。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="8eb2c-141">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-141">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="8eb2c-142">此节包含服务的集合。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-142">The section contains a collection of services.</span></span> <span data-ttu-id="8eb2c-143">对于程序集中定义的每个服务，此元素包含一个为服务指定设置的 `service` 元素。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="8eb2c-144">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="8eb2c-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="8eb2c-145">此节定义一个标准终结点集合，这些终结点是预配置的可重用终结点。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="8eb2c-146">标准终结点具有一个或多个设置为固定值的地址、绑定和协定特性。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="8eb2c-147">例如，发现终结点具有固定的协定。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="8eb2c-148">此外，还可以使用标准终结点用新属性扩展服务终结点，这与定义自定义绑定相似。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8eb2c-149">父元素</span><span class="sxs-lookup"><span data-stu-id="8eb2c-149">Parent Elements</span></span>  
  
|<span data-ttu-id="8eb2c-150">元素</span><span class="sxs-lookup"><span data-stu-id="8eb2c-150">Element</span></span>|<span data-ttu-id="8eb2c-151">描述</span><span class="sxs-lookup"><span data-stu-id="8eb2c-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8eb2c-152">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8eb2c-152">\<configuration></span></span>|<span data-ttu-id="8eb2c-153">.NET 配置文件中的所有配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-153">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eb2c-154">备注</span><span class="sxs-lookup"><span data-stu-id="8eb2c-154">Remarks</span></span>  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="8eb2c-155"> 不会向其他产品的配置节中添加元素。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-155"> does not add elements to the configuration sections of other products.</span></span>  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="8eb2c-156"> 服务是在配置文件的 `services` 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-156"> services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="8eb2c-157">程序集可以包含任意多个服务。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-157">An assembly can contain any number of services.</span></span> <span data-ttu-id="8eb2c-158">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-158">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="8eb2c-159">本节及其内容定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-159">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="8eb2c-160">只有服务的 `name` 属性是必需的。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-160">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="8eb2c-161">默认情况下，服务的名称描述用于实现服务的基础 CLR 类型；但是，您可以更改 <xref:System.ServiceModel.ServiceContractAttribute> 上的 ConfigurationName 属性以重写 CLR 类型要求。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-161">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="8eb2c-162">`behaviorConfiguration` 属性是可选项。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-162">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="8eb2c-163">它标识服务所使用的服务行为。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-163">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="8eb2c-164">此属性指定的行为必须链接到同一配置文件的范围（即，同一文件或父文件）中定义的服务行为。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-164">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="8eb2c-165">每个服务将公开 `endpoint` 元素中定义的一个或多个终结点。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-165">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="8eb2c-166">每个终结点都具有自己的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-166">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="8eb2c-167">配置文件中使用的所有绑定都必须在该文件的范围内定义。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-167">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="8eb2c-168">绑定通过 `name` 和 `bindingConfiguration` 属性的组合链接到终结点。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-168">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="8eb2c-169">`binding` 属性定义在哪个节中定义绑定。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-169">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="8eb2c-170">`bindingConfiguration` 属性定义使用绑定节中的哪个已配置绑定。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-170">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="8eb2c-171">绑定节可以定义若干个已配置的绑定。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-171">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8eb2c-172">示例</span><span class="sxs-lookup"><span data-stu-id="8eb2c-172">Example</span></span>  
 <span data-ttu-id="8eb2c-173">下面是 WCF 配置文件的示例。</span><span class="sxs-lookup"><span data-stu-id="8eb2c-173">This is an example of a WCF configuration file.</span></span>  
  
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
        <diagnostics wmiProviderEnabled="false" performanceCountersEnabled="false" tracingEnabled="false">  
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
  
## <a name="see-also"></a><span data-ttu-id="8eb2c-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8eb2c-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
