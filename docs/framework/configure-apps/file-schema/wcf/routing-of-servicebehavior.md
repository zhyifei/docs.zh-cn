---
title: <routing> 的 <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 3f23cbb45aa72b1aae18c845e68b426a4214d499
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261771"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="60320-102">\<路由 > 的\<serviceBehavior ></span><span class="sxs-lookup"><span data-stu-id="60320-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="60320-103">提供对路由服务的运行时访问以允许对路由配置进行动态修改。</span><span class="sxs-lookup"><span data-stu-id="60320-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="60320-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="60320-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="60320-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="60320-105">\<behaviors></span></span>  
<span data-ttu-id="60320-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="60320-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="60320-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="60320-107">\<behavior></span></span>  
<span data-ttu-id="60320-108">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="60320-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60320-109">语法</span><span class="sxs-lookup"><span data-stu-id="60320-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60320-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="60320-110">Attributes and Elements</span></span>  
 <span data-ttu-id="60320-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="60320-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60320-112">特性</span><span class="sxs-lookup"><span data-stu-id="60320-112">Attributes</span></span>  
  
|<span data-ttu-id="60320-113">特性</span><span class="sxs-lookup"><span data-stu-id="60320-113">Attribute</span></span>|<span data-ttu-id="60320-114">描述</span><span class="sxs-lookup"><span data-stu-id="60320-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60320-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="60320-115">filterTable</span></span>|<span data-ttu-id="60320-116">一个字符串，指定路由服务要计算的筛选器所在的路由表的名称。</span><span class="sxs-lookup"><span data-stu-id="60320-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="60320-117">此值必须匹配`name`的属性[ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md)中的元素[ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md)部分。</span><span class="sxs-lookup"><span data-stu-id="60320-117">This value must match the `name` attribute of a [\<filterTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element in the [\<filterTables>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) section.</span></span>|  
|<span data-ttu-id="60320-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="60320-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="60320-119">一个布尔值，指定筛选器将同时检查消息正文和标头，还是仅检查标头。</span><span class="sxs-lookup"><span data-stu-id="60320-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="60320-120">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="60320-120">The default is `true`.</span></span>|  
|<span data-ttu-id="60320-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="60320-121">soapProcessingEnabled</span></span>|<span data-ttu-id="60320-122">一个布尔值，指定是否应进行 SOAP 处理。</span><span class="sxs-lookup"><span data-stu-id="60320-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60320-123">子元素</span><span class="sxs-lookup"><span data-stu-id="60320-123">Child Elements</span></span>  
 <span data-ttu-id="60320-124">无。</span><span class="sxs-lookup"><span data-stu-id="60320-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60320-125">父元素</span><span class="sxs-lookup"><span data-stu-id="60320-125">Parent Elements</span></span>  
  
|<span data-ttu-id="60320-126">元素</span><span class="sxs-lookup"><span data-stu-id="60320-126">Element</span></span>|<span data-ttu-id="60320-127">描述</span><span class="sxs-lookup"><span data-stu-id="60320-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60320-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="60320-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="60320-129">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="60320-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60320-130">备注</span><span class="sxs-lookup"><span data-stu-id="60320-130">Remarks</span></span>  
 <span data-ttu-id="60320-131">将此配置元素添加到服务的行为配置中后，此配置元素将对该服务启用路由。</span><span class="sxs-lookup"><span data-stu-id="60320-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="60320-132">您可以在此元素中指定服务要使用的实际路由表。</span><span class="sxs-lookup"><span data-stu-id="60320-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="60320-133">通过使用此配置节，您可以在部署模式发生更改时动态更改路由设置。</span><span class="sxs-lookup"><span data-stu-id="60320-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="60320-134">在运行时，您可以使用新的路由设置注册自己的路由扩展，路由服务将开始对新消息和会话使用更新后的配置信息，而使正在实施的消息/会话使用启动时的任何现有规则。</span><span class="sxs-lookup"><span data-stu-id="60320-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="60320-135">这样，您可以在运行时对路由服务进行会话安全的无回收重新配置。</span><span class="sxs-lookup"><span data-stu-id="60320-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
  
