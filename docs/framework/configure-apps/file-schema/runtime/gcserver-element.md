---
title: '&lt;gcServer&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 027176bdff644a6ff3314df7484ed88ace93001b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltgcservergt-element"></a><span data-ttu-id="20e2f-102">&lt;gcServer&gt;元素</span><span class="sxs-lookup"><span data-stu-id="20e2f-102">&lt;gcServer&gt; Element</span></span>
<span data-ttu-id="20e2f-103">指定公共语言运行时是否运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="20e2f-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
 <span data-ttu-id="20e2f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="20e2f-104">\<configuration></span></span>  
<span data-ttu-id="20e2f-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="20e2f-105">\<runtime></span></span>  
<span data-ttu-id="20e2f-106">\<gcServer></span><span class="sxs-lookup"><span data-stu-id="20e2f-106">\<gcServer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20e2f-107">语法</span><span class="sxs-lookup"><span data-stu-id="20e2f-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20e2f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20e2f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="20e2f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="20e2f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20e2f-110">特性</span><span class="sxs-lookup"><span data-stu-id="20e2f-110">Attributes</span></span>  
  
|<span data-ttu-id="20e2f-111">特性</span><span class="sxs-lookup"><span data-stu-id="20e2f-111">Attribute</span></span>|<span data-ttu-id="20e2f-112">描述</span><span class="sxs-lookup"><span data-stu-id="20e2f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="20e2f-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="20e2f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="20e2f-114">指定运行时是否运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="20e2f-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="20e2f-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="20e2f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="20e2f-116">值</span><span class="sxs-lookup"><span data-stu-id="20e2f-116">Value</span></span>|<span data-ttu-id="20e2f-117">描述</span><span class="sxs-lookup"><span data-stu-id="20e2f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="20e2f-118">请勿运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="20e2f-118">Does not run server garbage collection.</span></span> <span data-ttu-id="20e2f-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="20e2f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="20e2f-120">运行服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="20e2f-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20e2f-121">子元素</span><span class="sxs-lookup"><span data-stu-id="20e2f-121">Child Elements</span></span>  
 <span data-ttu-id="20e2f-122">无。</span><span class="sxs-lookup"><span data-stu-id="20e2f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20e2f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="20e2f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="20e2f-124">元素</span><span class="sxs-lookup"><span data-stu-id="20e2f-124">Element</span></span>|<span data-ttu-id="20e2f-125">描述</span><span class="sxs-lookup"><span data-stu-id="20e2f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="20e2f-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="20e2f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="20e2f-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="20e2f-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20e2f-128">备注</span><span class="sxs-lookup"><span data-stu-id="20e2f-128">Remarks</span></span>  
 <span data-ttu-id="20e2f-129">公共语言运行时 (CLR) 支持两种类型的垃圾回收：工作站垃圾回收（适用于所有系统）和服务器垃圾回收（适用于多处理器系统）。</span><span class="sxs-lookup"><span data-stu-id="20e2f-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="20e2f-130">使用 `<gcServer>` 元素以控制 CLR 执行的垃圾回收类型。</span><span class="sxs-lookup"><span data-stu-id="20e2f-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="20e2f-131">使用 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> 属性以确定是否启用服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="20e2f-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="20e2f-132">对于单处理器计算机，默认的工作站垃圾回收应该是最快捷的选项。</span><span class="sxs-lookup"><span data-stu-id="20e2f-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="20e2f-133">对于双处理器计算机，最快捷的选项既可以是工作站垃圾回收又可以是服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="20e2f-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="20e2f-134">对于两个以上处理器的计算机，服务器垃圾回收应该是最快捷的选项。</span><span class="sxs-lookup"><span data-stu-id="20e2f-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="20e2f-135">此元素只能在应用程序配置文件中使用；如果此元素在计算机配置文件中，请忽略。</span><span class="sxs-lookup"><span data-stu-id="20e2f-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20e2f-136">在 .NET Framework 4 和更低版本中，启用服务器垃圾回收之后，并发垃圾回收不可用。</span><span class="sxs-lookup"><span data-stu-id="20e2f-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="20e2f-137">自 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] 起，服务器垃圾回收就是并发回收。</span><span class="sxs-lookup"><span data-stu-id="20e2f-137">Starting with the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], server garbage collection is concurrent.</span></span> <span data-ttu-id="20e2f-138">若要使用非并发服务器垃圾回收，设置`<gcServer>`元素`true`和[ \<gcConcurrent > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)到`false`。</span><span class="sxs-lookup"><span data-stu-id="20e2f-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20e2f-139">示例</span><span class="sxs-lookup"><span data-stu-id="20e2f-139">Example</span></span>  
 <span data-ttu-id="20e2f-140">下面的示例启用服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="20e2f-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="20e2f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="20e2f-141">See Also</span></span>  
 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="20e2f-142">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="20e2f-142">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="20e2f-143">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="20e2f-143">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="20e2f-144">如何： 禁用并发垃圾回收</span><span class="sxs-lookup"><span data-stu-id="20e2f-144">How to: Disable Concurrent Garbage Collection</span></span>](http://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)
