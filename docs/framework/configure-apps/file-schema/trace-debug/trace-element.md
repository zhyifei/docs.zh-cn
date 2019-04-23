---
title: <trace> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 5faf352dce2a459a999b3cf54209f6bd9793bde0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073788"
---
# <a name="trace-element"></a><span data-ttu-id="b3d10-102">\<跟踪 > 元素</span><span class="sxs-lookup"><span data-stu-id="b3d10-102">\<trace> Element</span></span>
<span data-ttu-id="b3d10-103">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="b3d10-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="b3d10-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b3d10-104">\<configuration></span></span>  
<span data-ttu-id="b3d10-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="b3d10-105">\<system.diagnostics></span></span>  
<span data-ttu-id="b3d10-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="b3d10-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3d10-107">语法</span><span class="sxs-lookup"><span data-stu-id="b3d10-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3d10-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b3d10-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b3d10-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b3d10-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3d10-110">特性</span><span class="sxs-lookup"><span data-stu-id="b3d10-110">Attributes</span></span>  
  
|<span data-ttu-id="b3d10-111">特性</span><span class="sxs-lookup"><span data-stu-id="b3d10-111">Attribute</span></span>|<span data-ttu-id="b3d10-112">描述</span><span class="sxs-lookup"><span data-stu-id="b3d10-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="b3d10-113">可选特性。</span><span class="sxs-lookup"><span data-stu-id="b3d10-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b3d10-114">指定的跟踪侦听器是否在每个写入操作后会自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b3d10-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="b3d10-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="b3d10-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b3d10-116">指定要缩进空格的数。</span><span class="sxs-lookup"><span data-stu-id="b3d10-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="b3d10-117">可选特性。</span><span class="sxs-lookup"><span data-stu-id="b3d10-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b3d10-118">指示是否应使用全局锁。</span><span class="sxs-lookup"><span data-stu-id="b3d10-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="b3d10-119">自动刷新属性</span><span class="sxs-lookup"><span data-stu-id="b3d10-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="b3d10-120">“值”</span><span class="sxs-lookup"><span data-stu-id="b3d10-120">Value</span></span>|<span data-ttu-id="b3d10-121">描述</span><span class="sxs-lookup"><span data-stu-id="b3d10-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b3d10-122">不自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b3d10-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="b3d10-123">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="b3d10-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b3d10-124">自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b3d10-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="b3d10-125">useGlobalLock Attribute</span><span class="sxs-lookup"><span data-stu-id="b3d10-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="b3d10-126">“值”</span><span class="sxs-lookup"><span data-stu-id="b3d10-126">Value</span></span>|<span data-ttu-id="b3d10-127">描述</span><span class="sxs-lookup"><span data-stu-id="b3d10-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b3d10-128">侦听器是线程安全; 如果不使用全局锁否则，将使用全局锁。</span><span class="sxs-lookup"><span data-stu-id="b3d10-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="b3d10-129">使用全局锁，而不管侦听器是线程安全。</span><span class="sxs-lookup"><span data-stu-id="b3d10-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="b3d10-130">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="b3d10-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3d10-131">子元素</span><span class="sxs-lookup"><span data-stu-id="b3d10-131">Child Elements</span></span>  
  
|<span data-ttu-id="b3d10-132">元素</span><span class="sxs-lookup"><span data-stu-id="b3d10-132">Element</span></span>|<span data-ttu-id="b3d10-133">描述</span><span class="sxs-lookup"><span data-stu-id="b3d10-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3d10-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="b3d10-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="b3d10-135">指定的侦听器，可收集、 存储，并将消息路由。</span><span class="sxs-lookup"><span data-stu-id="b3d10-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3d10-136">父元素</span><span class="sxs-lookup"><span data-stu-id="b3d10-136">Parent Elements</span></span>  
  
|<span data-ttu-id="b3d10-137">元素</span><span class="sxs-lookup"><span data-stu-id="b3d10-137">Element</span></span>|<span data-ttu-id="b3d10-138">描述</span><span class="sxs-lookup"><span data-stu-id="b3d10-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b3d10-139">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b3d10-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b3d10-140">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="b3d10-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b3d10-141">示例</span><span class="sxs-lookup"><span data-stu-id="b3d10-141">Example</span></span>  
 <span data-ttu-id="b3d10-142">下面的示例演示如何使用`<trace>`元素添加侦听器`MyListener`到`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="b3d10-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="b3d10-143">`MyListener` 创建一个名为的文件`MyListener.log`并将输出写入到该文件。</span><span class="sxs-lookup"><span data-stu-id="b3d10-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="b3d10-144">`useGlobalLock`属性设置为`false`，这将导致非用于如果跟踪侦听器是线程安全的全局锁。</span><span class="sxs-lookup"><span data-stu-id="b3d10-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="b3d10-145">`autoflush`属性设置为`true`，这将导致跟踪侦听器写入到文件而不考虑是否<xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType>调用方法。</span><span class="sxs-lookup"><span data-stu-id="b3d10-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="b3d10-146">`indentsize`属性设置为 0 （零），这会导致要缩进没有任何空间的侦听器时<xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType>调用方法。</span><span class="sxs-lookup"><span data-stu-id="b3d10-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3d10-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3d10-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="b3d10-148">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="b3d10-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
