---
title: 消息筛选器
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- routing [WCF], message filters
ms.assetid: cb33ba49-8b1f-4099-8acb-240404a46d9a
caps.latest.revision: 8
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bd5019668e865d2fea835b450d992d45b5273ed7
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
---
# <a name="message-filters"></a><span data-ttu-id="2eee7-102">消息筛选器</span><span class="sxs-lookup"><span data-stu-id="2eee7-102">Message Filters</span></span>
<span data-ttu-id="2eee7-103">为了实现基于内容的路由，路由服务使用 <xref:System.ServiceModel.Dispatcher.MessageFilter> 实现，这些实现检查消息的特定部分，例如地址、终结点名称或特定 XPath 语句。</span><span class="sxs-lookup"><span data-stu-id="2eee7-103">To implement content-based routing, the Routing Service uses <xref:System.ServiceModel.Dispatcher.MessageFilter> implementations that inspect specific sections of a message, such as the address, endpoint name, or a specific XPath statement.</span></span> <span data-ttu-id="2eee7-104">如果随 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 一起提供的消息筛选器均无法满足您的需求，则您可以通过创建 <xref:System.ServiceModel.Dispatcher.MessageFilter> 基类的新实现来创建自定义筛选器。</span><span class="sxs-lookup"><span data-stu-id="2eee7-104">If none of the message filters provided with [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] meet your needs, you can create a custom filter by creating a new implementation of the base <xref:System.ServiceModel.Dispatcher.MessageFilter> class.</span></span>  
  
 <span data-ttu-id="2eee7-105">配置路由服务时，你必须定义筛选器元素 (<xref:System.ServiceModel.Routing.Configuration.FilterElement>对象) 描述的类型**MessageFilter**以及创建筛选器，例如要搜索的特定字符串值所需的任何支持数据有关消息中。</span><span class="sxs-lookup"><span data-stu-id="2eee7-105">When configuring the Routing Service, you must define filter elements (<xref:System.ServiceModel.Routing.Configuration.FilterElement> objects) that describe the type of **MessageFilter** and any supporting data required to create the filter, such as specific string values to search for within the message.</span></span> <span data-ttu-id="2eee7-106">请注意，创建筛选器元素仅定义了单独的消息筛选器；若要使用筛选器计算和路由消息，还必须定义筛选器表 (<xref:System.ServiceModel.Routing.Configuration.FilterTableEntryCollection>)。</span><span class="sxs-lookup"><span data-stu-id="2eee7-106">Note that creating the filter elements only defines the individual message filters; to use the filters to evaluate and route messages you must also define a filter table (<xref:System.ServiceModel.Routing.Configuration.FilterTableEntryCollection>).</span></span>  
  
 <span data-ttu-id="2eee7-107">筛选器表中的每个条目都引用一个筛选器元素，并指定当消息与筛选器匹配时消息将路由到的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="2eee7-107">Each entry in the filter table references a filter element and specifies the client endpoint that a message will be routed to if the message matches the filter.</span></span> <span data-ttu-id="2eee7-108">通过筛选器表条目，您还可以指定一个备份终结点集合 (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>)，该集合定义在向主终结点发送消息但出现传输故障时，该消息将传输到的目标终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="2eee7-108">The filter table entries also allow you to specify a collection of backup endpoints (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>), which defines a list of endpoints that the message will be transmitted to in the event of a transmission failure when sending to the primary endpoint.</span></span> <span data-ttu-id="2eee7-109">将按指定顺序尝试这些终结点，直至某个终结点成功为止。</span><span class="sxs-lookup"><span data-stu-id="2eee7-109">These endpoints will be tried in the order specified until one succeeds.</span></span>  
  
## <a name="message-filters"></a><span data-ttu-id="2eee7-110">消息筛选器</span><span class="sxs-lookup"><span data-stu-id="2eee7-110">Message Filters</span></span>  
 <span data-ttu-id="2eee7-111">路由服务使用的消息筛选器提供常用消息选择功能，例如，计算消息已发送到的终结点的名称、SOAP 操作或消息已发送到的地址或地址前缀。</span><span class="sxs-lookup"><span data-stu-id="2eee7-111">The message filters used by the Routing Service provide common message selection functionality, such as evaluating the name of the endpoint that a message was sent to, the SOAP action, or the address or address prefix that the message was sent to.</span></span> <span data-ttu-id="2eee7-112">也可以使用 `AND` 条件连接筛选器，这样，仅当消息同时与两个筛选器匹配时，才会将消息路由至某个终结点。</span><span class="sxs-lookup"><span data-stu-id="2eee7-112">Filters can also be joined with an `AND` condition, so that messages will only be routed to an endpoint if the message matches both filters.</span></span> <span data-ttu-id="2eee7-113">此外，还可以通过创建您自己的 <xref:System.ServiceModel.Dispatcher.MessageFilter> 实现来创建自定义筛选器。</span><span class="sxs-lookup"><span data-stu-id="2eee7-113">You can also create custom filters by creating your own implementation of <xref:System.ServiceModel.Dispatcher.MessageFilter>.</span></span>  
  
 <span data-ttu-id="2eee7-114">下表列出了路由服务使用的 <xref:System.ServiceModel.Routing.Configuration.FilterType>、实现特定消息筛选器的类，以及所需的 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A> 参数。</span><span class="sxs-lookup"><span data-stu-id="2eee7-114">The following table lists the <xref:System.ServiceModel.Routing.Configuration.FilterType> used by the Routing Service, the class that implements the specific message filter, and the required <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A> parameters.</span></span>  
  
|<span data-ttu-id="2eee7-115">筛选器类型</span><span class="sxs-lookup"><span data-stu-id="2eee7-115">Filter  Type</span></span>|<span data-ttu-id="2eee7-116">描述</span><span class="sxs-lookup"><span data-stu-id="2eee7-116">Description</span></span>|<span data-ttu-id="2eee7-117">筛选器数据含义</span><span class="sxs-lookup"><span data-stu-id="2eee7-117">Filter Data Meaning</span></span>|<span data-ttu-id="2eee7-118">示例筛选器</span><span class="sxs-lookup"><span data-stu-id="2eee7-118">Example Filter</span></span>|  
|------------------|-----------------|-------------------------|--------------------|  
|<span data-ttu-id="2eee7-119">操作</span><span class="sxs-lookup"><span data-stu-id="2eee7-119">Action</span></span>|<span data-ttu-id="2eee7-120">使用 <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> 类匹配包含特定操作的消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-120">Uses the <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> class to match messages containing a specific action.</span></span>|<span data-ttu-id="2eee7-121">筛选器基于的操作。</span><span class="sxs-lookup"><span data-stu-id="2eee7-121">The action to filter upon.</span></span>|<span data-ttu-id="2eee7-122">\<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation" /></span><span class="sxs-lookup"><span data-stu-id="2eee7-122">\<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation" /></span></span>|  
|<span data-ttu-id="2eee7-123">EndpointAddress</span><span class="sxs-lookup"><span data-stu-id="2eee7-123">EndpointAddress</span></span>|<span data-ttu-id="2eee7-124">使用<xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter>类，与<xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true`匹配包含特定地址的消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-124">Uses the <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> class, with <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter.IncludeHostNameInComparison%2A> == `true` to match messages containing a specific address.</span></span>|<span data-ttu-id="2eee7-125">筛选器基于的地址（在 To 标头中）。</span><span class="sxs-lookup"><span data-stu-id="2eee7-125">The address to filter upon (in the To header).</span></span>|<span data-ttu-id="2eee7-126">\<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b"  /></span><span class="sxs-lookup"><span data-stu-id="2eee7-126">\<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b"  /></span></span>|  
|<span data-ttu-id="2eee7-127">EndpointAddressPrefix</span><span class="sxs-lookup"><span data-stu-id="2eee7-127">EndpointAddressPrefix</span></span>|<span data-ttu-id="2eee7-128">使用<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>类，与<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true`匹配包含特定地址前缀的消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-128">Uses the <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> class, with <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter.IncludeHostNameInComparison%2A> == `true` to match messages containing a specific address prefix.</span></span>|<span data-ttu-id="2eee7-129">筛选器基于的地址（使用最长的前缀匹配项）。</span><span class="sxs-lookup"><span data-stu-id="2eee7-129">The address to filter upon using longest prefix matching.</span></span>|<span data-ttu-id="2eee7-130">\<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/" /></span><span class="sxs-lookup"><span data-stu-id="2eee7-130">\<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/" /></span></span>|  
|<span data-ttu-id="2eee7-131">And</span><span class="sxs-lookup"><span data-stu-id="2eee7-131">And</span></span>|<span data-ttu-id="2eee7-132">使用始终在返回前计算两个条件的 <xref:System.ServiceModel.Dispatcher.StrictAndMessageFilter> 类。</span><span class="sxs-lookup"><span data-stu-id="2eee7-132">Uses the <xref:System.ServiceModel.Dispatcher.StrictAndMessageFilter> class that always evaluates both conditions before returning.</span></span>|<span data-ttu-id="2eee7-133">不使用 filterData;而 filter1 和 filter2 具有相应消息筛选器的名称 （也在表中），它应**AND**它们连接起来。</span><span class="sxs-lookup"><span data-stu-id="2eee7-133">filterData is not used; instead filter1 and filter2 have the names of the corresponding message filters (also in the table), which should be **AND**ed together.</span></span>|<span data-ttu-id="2eee7-134">\<filter name="and1" filterType="And" filter1="address1" filter2="action1" /></span><span class="sxs-lookup"><span data-stu-id="2eee7-134">\<filter name="and1" filterType="And" filter1="address1" filter2="action1" /></span></span>|  
|<span data-ttu-id="2eee7-135">自定义</span><span class="sxs-lookup"><span data-stu-id="2eee7-135">Custom</span></span>|<span data-ttu-id="2eee7-136">一个用户定义的类型，此类型扩展 <xref:System.ServiceModel.Dispatcher.MessageFilter> 类并具有采用字符串的构造函数。</span><span class="sxs-lookup"><span data-stu-id="2eee7-136">A user-defined type that extends the <xref:System.ServiceModel.Dispatcher.MessageFilter> class and has a constructor taking a string.</span></span>|<span data-ttu-id="2eee7-137">customType 特性是要创建的类的完全限定类型名称；filterData 是在创建筛选器时要传递给构造函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="2eee7-137">The customType attribute is the fully qualified type name of the class to create; filterData is the string to pass to the constructor when creating the filter.</span></span>|<span data-ttu-id="2eee7-138">\<filter name="custom1" filterType="Custom" customType="CustomAssembly.CustomMsgFilter, CustomAssembly" filterData="Custom Data" /></span><span class="sxs-lookup"><span data-stu-id="2eee7-138">\<filter name="custom1" filterType="Custom" customType="CustomAssembly.CustomMsgFilter, CustomAssembly" filterData="Custom Data" /></span></span>|  
|<span data-ttu-id="2eee7-139">EndpointName</span><span class="sxs-lookup"><span data-stu-id="2eee7-139">EndpointName</span></span>|<span data-ttu-id="2eee7-140">使用 <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> 类根据消息已到达的服务终结点的名称来匹配消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-140">Uses the <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> class to match messages based on the name of the service endpoint they arrived on.</span></span>|<span data-ttu-id="2eee7-141">名称的服务终结点，例如:"serviceEndpoint1"。</span><span class="sxs-lookup"><span data-stu-id="2eee7-141">The name of the service endpoint, for example: "serviceEndpoint1".</span></span>  <span data-ttu-id="2eee7-142">该终结点应为在路由服务上公开的终结点之一。</span><span class="sxs-lookup"><span data-stu-id="2eee7-142">This should be one of the endpoints exposed on the Routing Service.</span></span>|<span data-ttu-id="2eee7-143">\<filter name="stock1" filterType="Endpoint" filterData="SvcEndpoint" /></span><span class="sxs-lookup"><span data-stu-id="2eee7-143">\<filter name="stock1" filterType="Endpoint" filterData="SvcEndpoint" /></span></span>|  
|<span data-ttu-id="2eee7-144">MatchAll</span><span class="sxs-lookup"><span data-stu-id="2eee7-144">MatchAll</span></span>|<span data-ttu-id="2eee7-145">使用 <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> 类。</span><span class="sxs-lookup"><span data-stu-id="2eee7-145">Uses the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> class.</span></span> <span data-ttu-id="2eee7-146">该筛选器匹配所有到达的消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-146">This filter matches all arriving messages.</span></span>|<span data-ttu-id="2eee7-147">不使用 filterData。</span><span class="sxs-lookup"><span data-stu-id="2eee7-147">filterData is not used.</span></span> <span data-ttu-id="2eee7-148">该筛选器将始终匹配所有消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-148">This filter will always match all messages.</span></span>|<span data-ttu-id="2eee7-149">\<filter name="matchAll1" filterType="MatchAll" /></span><span class="sxs-lookup"><span data-stu-id="2eee7-149">\<filter name="matchAll1" filterType="MatchAll" /></span></span>|  
|<span data-ttu-id="2eee7-150">XPath</span><span class="sxs-lookup"><span data-stu-id="2eee7-150">XPath</span></span>|<span data-ttu-id="2eee7-151">使用 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> 类匹配消息中的特定 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="2eee7-151">Uses the <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> class to match specific XPath queries within the message.</span></span>|<span data-ttu-id="2eee7-152">在匹配消息时要使用的 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="2eee7-152">The XPath query to use when matching messages.</span></span>|<span data-ttu-id="2eee7-153">\<filter name="XPath1" filterType="XPath" filterData="//ns:element" /></span><span class="sxs-lookup"><span data-stu-id="2eee7-153">\<filter name="XPath1" filterType="XPath" filterData="//ns:element" /></span></span>|  
  
 <span data-ttu-id="2eee7-154">下面的示例定义使用 XPath、EndpointName 和 PrefixEndpointAddress 消息筛选器的筛选器条目。</span><span class="sxs-lookup"><span data-stu-id="2eee7-154">The following example defines filter entries that use the XPath, EndpointName, and PrefixEndpointAddress message filters.</span></span> <span data-ttu-id="2eee7-155">该示例还演示如何对 RoundRobinFilter1 和 RoundRobinFilter2 条目使用自定义筛选器。</span><span class="sxs-lookup"><span data-stu-id="2eee7-155">This example also demonstrates using a custom filter for the RoundRobinFilter1 and RoundRobinFilter2 entries.</span></span>  
  
```xml  
<filters>  
     <filter name="XPathFilter" filterType="XPath"   
             filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
     <filter name="EndpointNameFilter" filterType="EndpointName"   
             filterData="calculatorEndpoint"/>  
     <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"   
             filterData="http://localhost/routingservice/router/rounding/"/>  
     <filter name="RoundRobinFilter1" filterType="Custom"   
             customType="RoutingServiceFilters.RoundRobinMessageFilter,   
             RoutingService" filterData="group1"/>  
     <filter name="RoundRobinFilter2" filterType="Custom"   
             customType="RoutingServiceFilters.RoundRobinMessageFilter,   
             RoutingService" filterData="group1"/>  
</filters>  
```  
  
> [!NOTE]
>  <span data-ttu-id="2eee7-156">仅定义筛选器不会导致根据筛选器计算消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-156">Simply defining a filter does not cause messages to be evaluated against the filter.</span></span> <span data-ttu-id="2eee7-157">必须将筛选器添加到筛选器表中，然后会将该筛选器与路由服务公开的服务终结点相关联。</span><span class="sxs-lookup"><span data-stu-id="2eee7-157">The filter must be added to a filter table, which is then associated with the service endpoint exposed by the Routing Service.</span></span>  
  
### <a name="namespace-table"></a><span data-ttu-id="2eee7-158">命名空间表</span><span class="sxs-lookup"><span data-stu-id="2eee7-158">Namespace Table</span></span>  
 <span data-ttu-id="2eee7-159">当使用 XPath 筛选器时，包含 XPath 查询的筛选器数据可能会因使用了命名空间而变得非常大。</span><span class="sxs-lookup"><span data-stu-id="2eee7-159">When using an XPath filter, the filter data that contains the XPath query can become extremely large due to the use of namespaces.</span></span> <span data-ttu-id="2eee7-160">为了解决此问题，路由服务提供使用命名空间表定义您自己的命名空间前缀的功能。</span><span class="sxs-lookup"><span data-stu-id="2eee7-160">To alleviate this problem the Routing Service provides the ability to define your own namespace prefixes by using the namespace table.</span></span>  
  
 <span data-ttu-id="2eee7-161">命名空间表是 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement> 对象的集合，用于定义可在 XPath 中使用的常用命名空间的命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="2eee7-161">The namespace table is a collection of <xref:System.ServiceModel.Routing.Configuration.NamespaceElement> objects that defines the namespace prefixes for common namespaces that can be used in an XPath.</span></span> <span data-ttu-id="2eee7-162">下面列出了命名空间表中包含的默认命名空间和命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="2eee7-162">The following are the default namespaces and namespace prefixes that are contained in the namespace table.</span></span>  
  
|<span data-ttu-id="2eee7-163">前缀</span><span class="sxs-lookup"><span data-stu-id="2eee7-163">Prefix</span></span>|<span data-ttu-id="2eee7-164">命名空间</span><span class="sxs-lookup"><span data-stu-id="2eee7-164">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="2eee7-165">s11</span><span class="sxs-lookup"><span data-stu-id="2eee7-165">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="2eee7-166">s12</span><span class="sxs-lookup"><span data-stu-id="2eee7-166">s12</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="2eee7-167">wsaAugust2004</span><span class="sxs-lookup"><span data-stu-id="2eee7-167">wsaAugust2004</span></span>|http://schemas.xmlsoap.org/ws/2004/08/addressing|  
|<span data-ttu-id="2eee7-168">wsa10</span><span class="sxs-lookup"><span data-stu-id="2eee7-168">wsa10</span></span>|http://www.w3.org/2005/08/addressing|  
|<span data-ttu-id="2eee7-169">sm</span><span class="sxs-lookup"><span data-stu-id="2eee7-169">sm</span></span>|http://schemas.microsoft.com/serviceModel/2004/05/xpathfunctions|  
|<span data-ttu-id="2eee7-170">tempuri</span><span class="sxs-lookup"><span data-stu-id="2eee7-170">tempuri</span></span>|http://tempuri.org|  
|<span data-ttu-id="2eee7-171">ser</span><span class="sxs-lookup"><span data-stu-id="2eee7-171">ser</span></span>|http://schemas.microsoft.com/2003/10/Serialization|  
  
 <span data-ttu-id="2eee7-172">如果您确定您将在 XPath 查询中使用特定命名空间，则可以将此命名空间和唯一的命名空间前缀添加到命名空间表中，并在所有 XPath 查询中使用该前缀而不是使用完整命名空间。</span><span class="sxs-lookup"><span data-stu-id="2eee7-172">When you know that you will be using a specific namespace in your XPath queries, you can add it to the namespace table along with a unique namespace prefix and use the prefix in any XPath query instead of the full namespace.</span></span> <span data-ttu-id="2eee7-173">下面的示例定义的命名空间的前缀"custom""http://my.custom.namespace"，然后在 filterData 包含的 XPath 查询中使用。</span><span class="sxs-lookup"><span data-stu-id="2eee7-173">The following example defines a prefix of "custom" for the namespace "http://my.custom.namespace", which is then used in the XPath query contained in filterData.</span></span>  
  
```xml  
<namespaceTable>  
     <add prefix="custom" namespace="http://my.custom.namespace/"/>  
</namespaceTable>  
<filters>  
     <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
</filters>  
```  
  
## <a name="filter-tables"></a><span data-ttu-id="2eee7-174">筛选器表</span><span class="sxs-lookup"><span data-stu-id="2eee7-174">Filter Tables</span></span>  
 <span data-ttu-id="2eee7-175">各筛选器元素定义可应用于消息的逻辑比较，而筛选器表提供筛选器元素和目标客户端终结点之间的关联。</span><span class="sxs-lookup"><span data-stu-id="2eee7-175">While each filter element defines a logical comparison that can be applied to a message, the filter table provides the association between the filter element and the destination client endpoint.</span></span> <span data-ttu-id="2eee7-176">筛选器表是 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement> 对象的命名集合，用于定义筛选器、主目标终结点和替代备份终结点列表之间的关联。</span><span class="sxs-lookup"><span data-stu-id="2eee7-176">A filter table is a named collection of <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement> objects that define the association between a filter, a primary destination endpoint, and a list of alternative backup endpoints.</span></span> <span data-ttu-id="2eee7-177">筛选器表条目还允许您为每个筛选条件指定可选优先级。</span><span class="sxs-lookup"><span data-stu-id="2eee7-177">The filter table entries also allow you to specify an optional priority for each filter condition.</span></span> <span data-ttu-id="2eee7-178">下面的示例定义两个筛选器，然后定义一个用于将每个筛选器与目标终结点相关联的筛选器表。</span><span class="sxs-lookup"><span data-stu-id="2eee7-178">The following example defines two filters and then defines a filter table that associates each filter with a destination endpoint.</span></span>  
  
```xml  
<routing>  
     <filters>  
       <filter name="AddAction" filterType="Action" filterData="Add" />  
       <filter name="SubtractAction" filterType="Action" filterData="Subtract" />  
     </filters>  
     <filterTables>  
       <table name="routingTable1">  
         <filters>  
           <add filterName="AddAction" endpointName="Addition" />  
           <add filterName="SubtractAction" endpointName="Subtraction" />  
         </filters>  
       </table>  
     </filterTables>      
</routing>  
```  
  
### <a name="filter-evaluation-priority"></a><span data-ttu-id="2eee7-179">筛选器计算优先级</span><span class="sxs-lookup"><span data-stu-id="2eee7-179">Filter Evaluation Priority</span></span>  
 <span data-ttu-id="2eee7-180">默认情况下，将同时计算筛选器表中的所有条目，计算的消息将路由至与每个匹配的筛选器条目相关联的终结点。</span><span class="sxs-lookup"><span data-stu-id="2eee7-180">By default, all entries in the filter table are evaluated simultaneously, and the message being evaluated is routed to the endpoint(s) associated with each matching filter entry.</span></span> <span data-ttu-id="2eee7-181">如果多个筛选器的计算结果均为 `true`，并且消息是单向或双工消息，则会将此消息多播到所有匹配筛选器所对应的终结点。</span><span class="sxs-lookup"><span data-stu-id="2eee7-181">If multiple filters evaluate to `true`, and the message is one-way or duplex, the message is multicast to the endpoints for all matching filters.</span></span> <span data-ttu-id="2eee7-182">由于只能向客户端返回一个答复，因此无法多播请求-答复消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-182">Request-reply messages cannot be multicast because only one reply can be returned to the client.</span></span>  
  
 <span data-ttu-id="2eee7-183">通过为各筛选器指定优先级别，可以实现更复杂的路由逻辑；路由服务将首先计算处于最高优先级别的所有筛选器。</span><span class="sxs-lookup"><span data-stu-id="2eee7-183">More complex routing logic can be implemented by specifying priority levels for each filter; the Routing Service evaluates all filters at the highest priority level first.</span></span> <span data-ttu-id="2eee7-184">如果某一消息与此级别的筛选器相匹配，则不会处理较低优先级的筛选器。</span><span class="sxs-lookup"><span data-stu-id="2eee7-184">If a message matches a filter of this level, no filters of a lower priority are processed.</span></span> <span data-ttu-id="2eee7-185">例如，将首先根据优先级为 2 的所有筛选器计算传入的单向消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-185">For example, an incoming one-way message is first evaluated against all filters with a priority of 2.</span></span> <span data-ttu-id="2eee7-186">该消息不与此优先级别的任何筛选器匹配，因此，接着将根据优先级为 1 的筛选器比较此消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-186">The message does not match any filter at this priority level, so next the message is compared against filters with a priority of 1.</span></span> <span data-ttu-id="2eee7-187">有两个优先级为 1 的筛选器与此消息匹配，并且由于该消息是单向消息，因此将被路由至两个目标终结点。</span><span class="sxs-lookup"><span data-stu-id="2eee7-187">Two priority 1 filters match the message, and because it is a one-way message it is routed to both destination endpoints.</span></span>  <span data-ttu-id="2eee7-188">由于已在优先级为 1 的筛选器中找到了匹配项，因此不会计算优先级为 0 的筛选器。</span><span class="sxs-lookup"><span data-stu-id="2eee7-188">Because a match was found among the priority 1 filters, no filters of priority 0 are evaluated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2eee7-189">如果未指定优先级，则使用默认优先级 0。</span><span class="sxs-lookup"><span data-stu-id="2eee7-189">If no priority is specified, the default priority of 0 is used.</span></span>  
  
 <span data-ttu-id="2eee7-190">下面的示例定义一个筛选器表，该筛选器表为其引用的筛选器指定优先级 2、1 和 0。</span><span class="sxs-lookup"><span data-stu-id="2eee7-190">The following example defines a filter table that specifies priorities of 2, 1, and 0 for the filters referenced in the table.</span></span>  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="XPathFilter" endpointName="roundingCalcEndpoint"   
               priority="2"/>  
          <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint"   
               priority="1"/>  
          <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint"   
               priority="1"/>  
          <add filterName="MatchAllMessageFilter" endpointName="defaultCalcEndpoint"   
               priority="0"/>  
     </filterTable>  
</filterTables>  
```  
  
 <span data-ttu-id="2eee7-191">在上面的示例中，如果消息与 XPathFilter 匹配，则将该消息路由至 roundingCalcEndpoint，并且不会计算表中的任何其他筛选器，这是因为所有其他筛选器都具有较低的优先级。</span><span class="sxs-lookup"><span data-stu-id="2eee7-191">In the preceding example, if a message matches the XPathFilter, it will be routed to the roundingCalcEndpoint and no further filters in the table will be evaluated because all other filters are of a lower priority.</span></span> <span data-ttu-id="2eee7-192">但是，如果此消息与 XPathFilter 不匹配，则会根据下一较低优先级的所有筛选器（即 EndpointNameFilter 和 PrefixAddressFilter）计算此消息。</span><span class="sxs-lookup"><span data-stu-id="2eee7-192">However, if the message does not match the XPathFilter it will then be evaluated against all filters of the next lower priority, EndpointNameFilter and PrefixAddressFilter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2eee7-193">如有可能，请使用独占筛选器，而不是指定优先级，因为优先级计算可能会导致性能降级。</span><span class="sxs-lookup"><span data-stu-id="2eee7-193">When possible, use exclusive filters instead of specifying a priority because priority evaluation can result in performance degradation.</span></span>  
  
### <a name="backup-lists"></a><span data-ttu-id="2eee7-194">备份列表</span><span class="sxs-lookup"><span data-stu-id="2eee7-194">Backup Lists</span></span>  
 <span data-ttu-id="2eee7-195">筛选器表中的各个筛选器可以选择指定一个备份列表，即终结点的命名集合 (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>)。</span><span class="sxs-lookup"><span data-stu-id="2eee7-195">Each filter in the filter table can optionally specify a backup list, which is a named collection of endpoints (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>).</span></span> <span data-ttu-id="2eee7-196">该集合包含在向主终结点（在 <xref:System.ServiceModel.CommunicationException> 中指定）发送消息期间发生 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.EndpointName%2A> 时，消息将传输到的终结点的有序列表。</span><span class="sxs-lookup"><span data-stu-id="2eee7-196">This collection contains an ordered list of endpoints that the message will be transmitted to in the event of a <xref:System.ServiceModel.CommunicationException> when sending to the primary endpoint specified in <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.EndpointName%2A>.</span></span> <span data-ttu-id="2eee7-197">下面的示例定义一个名为"backupServiceEndpoints"包含两个终结点的备份列表。</span><span class="sxs-lookup"><span data-stu-id="2eee7-197">The following example defines a backup list named "backupServiceEndpoints" that contains two endpoints.</span></span>  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
 <span data-ttu-id="2eee7-198">在前面的示例中，如果向主终结点"Destination"失败，路由服务将尝试向它们列在序列中的每个终结点发送第一个发送到 backupServiceQueue，如果随后发送到 alternateServiceQueue发送到 backupServiceQueue 失败。</span><span class="sxs-lookup"><span data-stu-id="2eee7-198">In the preceding example, if a send to the primary endpoint "Destination" fails, the Routing Service will try sending to each endpoint in the sequence they are listed, first sending to backupServiceQueue and subsequently sending to alternateServiceQueue if the send to backupServiceQueue fails.</span></span> <span data-ttu-id="2eee7-199">如果所有备份终结点均失败，则会返回错误。</span><span class="sxs-lookup"><span data-stu-id="2eee7-199">If all backup endpoints fail, a fault is returned.</span></span>
