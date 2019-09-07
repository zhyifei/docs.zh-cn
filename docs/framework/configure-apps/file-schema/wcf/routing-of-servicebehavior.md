---
title: <routing> 的 <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 0998f4fc61de7099879ba6e122eed1e64588baec
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397735"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="36349-102">\<serviceBehavior > 的\<路由 ></span><span class="sxs-lookup"><span data-stu-id="36349-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="36349-103">提供对路由服务的运行时访问以允许对路由配置进行动态修改。</span><span class="sxs-lookup"><span data-stu-id="36349-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
<span data-ttu-id="36349-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36349-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36349-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="36349-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="36349-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="36349-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="36349-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="36349-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="36349-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="36349-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="36349-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<路由 >**</span><span class="sxs-lookup"><span data-stu-id="36349-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36349-110">语法</span><span class="sxs-lookup"><span data-stu-id="36349-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36349-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="36349-111">Attributes and Elements</span></span>  
 <span data-ttu-id="36349-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="36349-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36349-113">特性</span><span class="sxs-lookup"><span data-stu-id="36349-113">Attributes</span></span>  
  
|<span data-ttu-id="36349-114">特性</span><span class="sxs-lookup"><span data-stu-id="36349-114">Attribute</span></span>|<span data-ttu-id="36349-115">描述</span><span class="sxs-lookup"><span data-stu-id="36349-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36349-116">filterTable</span><span class="sxs-lookup"><span data-stu-id="36349-116">filterTable</span></span>|<span data-ttu-id="36349-117">一个字符串，指定路由服务要计算的筛选器所在的路由表的名称。</span><span class="sxs-lookup"><span data-stu-id="36349-117">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="36349-118">此值必须与`name` [filterTables > 部分中 filterTable > 元素的属性相匹配。 \<](filtertables.md) [ \<](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="36349-118">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="36349-119">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="36349-119">routeOnHeaderOnly</span></span>|<span data-ttu-id="36349-120">一个布尔值，指定筛选器将同时检查消息正文和标头，还是仅检查标头。</span><span class="sxs-lookup"><span data-stu-id="36349-120">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="36349-121">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="36349-121">The default is `true`.</span></span>|  
|<span data-ttu-id="36349-122">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="36349-122">soapProcessingEnabled</span></span>|<span data-ttu-id="36349-123">一个布尔值，指定是否应进行 SOAP 处理。</span><span class="sxs-lookup"><span data-stu-id="36349-123">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36349-124">子元素</span><span class="sxs-lookup"><span data-stu-id="36349-124">Child Elements</span></span>  
 <span data-ttu-id="36349-125">无。</span><span class="sxs-lookup"><span data-stu-id="36349-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36349-126">父元素</span><span class="sxs-lookup"><span data-stu-id="36349-126">Parent Elements</span></span>  
  
|<span data-ttu-id="36349-127">元素</span><span class="sxs-lookup"><span data-stu-id="36349-127">Element</span></span>|<span data-ttu-id="36349-128">描述</span><span class="sxs-lookup"><span data-stu-id="36349-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36349-129">\<behavior></span><span class="sxs-lookup"><span data-stu-id="36349-129">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="36349-130">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="36349-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36349-131">备注</span><span class="sxs-lookup"><span data-stu-id="36349-131">Remarks</span></span>  
 <span data-ttu-id="36349-132">将此配置元素添加到服务的行为配置中后，此配置元素将对该服务启用路由。</span><span class="sxs-lookup"><span data-stu-id="36349-132">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="36349-133">您可以在此元素中指定服务要使用的实际路由表。</span><span class="sxs-lookup"><span data-stu-id="36349-133">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="36349-134">通过使用此配置节，您可以在部署模式发生更改时动态更改路由设置。</span><span class="sxs-lookup"><span data-stu-id="36349-134">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="36349-135">在运行时，您可以使用新的路由设置注册自己的路由扩展，路由服务将开始对新消息和会话使用更新后的配置信息，而使正在实施的消息/会话使用启动时的任何现有规则。</span><span class="sxs-lookup"><span data-stu-id="36349-135">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="36349-136">这样，您可以在运行时对路由服务进行会话安全的无回收重新配置。</span><span class="sxs-lookup"><span data-stu-id="36349-136">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
