---
title: "&lt;GCCpuGroup&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dcead28d7bf66e0626a0108015add4f22c5fa476
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltgccpugroupgt-element"></a><span data-ttu-id="0e379-102">&lt;GCCpuGroup&gt;元素</span><span class="sxs-lookup"><span data-stu-id="0e379-102">&lt;GCCpuGroup&gt; Element</span></span>
<span data-ttu-id="0e379-103">指定垃圾回收是否支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="0e379-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="0e379-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0e379-104">\<configuration></span></span>  
<span data-ttu-id="0e379-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="0e379-105">\<runtime></span></span>  
<span data-ttu-id="0e379-106">\<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="0e379-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e379-107">语法</span><span class="sxs-lookup"><span data-stu-id="0e379-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e379-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0e379-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0e379-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0e379-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e379-110">特性</span><span class="sxs-lookup"><span data-stu-id="0e379-110">Attributes</span></span>  
  
|<span data-ttu-id="0e379-111">特性</span><span class="sxs-lookup"><span data-stu-id="0e379-111">Attribute</span></span>|<span data-ttu-id="0e379-112">描述</span><span class="sxs-lookup"><span data-stu-id="0e379-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0e379-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="0e379-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0e379-114">指定垃圾回收是否支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="0e379-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0e379-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="0e379-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="0e379-116">值</span><span class="sxs-lookup"><span data-stu-id="0e379-116">Value</span></span>|<span data-ttu-id="0e379-117">描述</span><span class="sxs-lookup"><span data-stu-id="0e379-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0e379-118">垃圾回收不支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="0e379-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="0e379-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="0e379-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0e379-120">垃圾回收支持多个 CPU 组，如果启用服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="0e379-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e379-121">子元素</span><span class="sxs-lookup"><span data-stu-id="0e379-121">Child Elements</span></span>  
 <span data-ttu-id="0e379-122">无。</span><span class="sxs-lookup"><span data-stu-id="0e379-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e379-123">父元素</span><span class="sxs-lookup"><span data-stu-id="0e379-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0e379-124">元素</span><span class="sxs-lookup"><span data-stu-id="0e379-124">Element</span></span>|<span data-ttu-id="0e379-125">描述</span><span class="sxs-lookup"><span data-stu-id="0e379-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0e379-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="0e379-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0e379-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="0e379-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e379-128">备注</span><span class="sxs-lookup"><span data-stu-id="0e379-128">Remarks</span></span>  
 <span data-ttu-id="0e379-129">当一台计算机有多个 CPU 组，并启用服务器垃圾回收 (请参阅[ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)元素)，启用此元素跨越所有的 CPU 组将扩展垃圾回收和采用到的所有核心创建和平衡堆时的帐户。</span><span class="sxs-lookup"><span data-stu-id="0e379-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e379-130">此元素仅适用于垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="0e379-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="0e379-131">若要启用运行时，将用户线程分布到所有的 CPU 组，你必须启用[< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="0e379-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e379-132">示例</span><span class="sxs-lookup"><span data-stu-id="0e379-132">Example</span></span>  
 <span data-ttu-id="0e379-133">下面的示例演示如何启用多个 CPU 组的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="0e379-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e379-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e379-134">See Also</span></span>  
 [<span data-ttu-id="0e379-135">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="0e379-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="0e379-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="0e379-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="0e379-137">如何： 禁用并发垃圾回收</span><span class="sxs-lookup"><span data-stu-id="0e379-137">How to: Disable Concurrent Garbage Collection</span></span>](http://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [<span data-ttu-id="0e379-138">工作站和服务器垃圾回收</span><span class="sxs-lookup"><span data-stu-id="0e379-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
