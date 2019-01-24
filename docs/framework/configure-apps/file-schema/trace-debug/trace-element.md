---
title: '&lt;跟踪&gt;元素'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 86cd4e7db5aa79ff85e5079813844d2af1598f4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642800"
---
# <a name="lttracegt-element"></a><span data-ttu-id="2f23c-102">&lt;跟踪&gt;元素</span><span class="sxs-lookup"><span data-stu-id="2f23c-102">&lt;trace&gt; Element</span></span>
<span data-ttu-id="2f23c-103">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="2f23c-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="2f23c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2f23c-104">\<configuration></span></span>  
<span data-ttu-id="2f23c-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="2f23c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="2f23c-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="2f23c-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f23c-107">语法</span><span class="sxs-lookup"><span data-stu-id="2f23c-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f23c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2f23c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2f23c-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2f23c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f23c-110">特性</span><span class="sxs-lookup"><span data-stu-id="2f23c-110">Attributes</span></span>  
  
|<span data-ttu-id="2f23c-111">特性</span><span class="sxs-lookup"><span data-stu-id="2f23c-111">Attribute</span></span>|<span data-ttu-id="2f23c-112">描述</span><span class="sxs-lookup"><span data-stu-id="2f23c-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="2f23c-113">可选特性。</span><span class="sxs-lookup"><span data-stu-id="2f23c-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2f23c-114">指定的跟踪侦听器是否在每个写入操作后会自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2f23c-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="2f23c-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="2f23c-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2f23c-116">指定要缩进空格的数。</span><span class="sxs-lookup"><span data-stu-id="2f23c-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="2f23c-117">可选特性。</span><span class="sxs-lookup"><span data-stu-id="2f23c-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2f23c-118">指示是否应使用全局锁。</span><span class="sxs-lookup"><span data-stu-id="2f23c-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="2f23c-119">自动刷新属性</span><span class="sxs-lookup"><span data-stu-id="2f23c-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="2f23c-120">值</span><span class="sxs-lookup"><span data-stu-id="2f23c-120">Value</span></span>|<span data-ttu-id="2f23c-121">描述</span><span class="sxs-lookup"><span data-stu-id="2f23c-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2f23c-122">不自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2f23c-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="2f23c-123">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2f23c-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2f23c-124">自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2f23c-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="2f23c-125">useGlobalLock Attribute</span><span class="sxs-lookup"><span data-stu-id="2f23c-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="2f23c-126">值</span><span class="sxs-lookup"><span data-stu-id="2f23c-126">Value</span></span>|<span data-ttu-id="2f23c-127">描述</span><span class="sxs-lookup"><span data-stu-id="2f23c-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2f23c-128">侦听器是线程安全; 如果不使用全局锁否则，将使用全局锁。</span><span class="sxs-lookup"><span data-stu-id="2f23c-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="2f23c-129">使用全局锁，而不管侦听器是线程安全。</span><span class="sxs-lookup"><span data-stu-id="2f23c-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="2f23c-130">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2f23c-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f23c-131">子元素</span><span class="sxs-lookup"><span data-stu-id="2f23c-131">Child Elements</span></span>  
  
|<span data-ttu-id="2f23c-132">元素</span><span class="sxs-lookup"><span data-stu-id="2f23c-132">Element</span></span>|<span data-ttu-id="2f23c-133">描述</span><span class="sxs-lookup"><span data-stu-id="2f23c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f23c-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="2f23c-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="2f23c-135">指定的侦听器，可收集、 存储，并将消息路由。</span><span class="sxs-lookup"><span data-stu-id="2f23c-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f23c-136">父元素</span><span class="sxs-lookup"><span data-stu-id="2f23c-136">Parent Elements</span></span>  
  
|<span data-ttu-id="2f23c-137">元素</span><span class="sxs-lookup"><span data-stu-id="2f23c-137">Element</span></span>|<span data-ttu-id="2f23c-138">描述</span><span class="sxs-lookup"><span data-stu-id="2f23c-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2f23c-139">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2f23c-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2f23c-140">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="2f23c-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f23c-141">示例</span><span class="sxs-lookup"><span data-stu-id="2f23c-141">Example</span></span>  
 <span data-ttu-id="2f23c-142">下面的示例演示如何使用`<trace>`元素添加侦听器`MyListener`到`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="2f23c-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="2f23c-143">`MyListener` 创建一个名为的文件`MyListener.log`并将输出写入到该文件。</span><span class="sxs-lookup"><span data-stu-id="2f23c-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="2f23c-144">`useGlobalLock`属性设置为`false`，这将导致非用于如果跟踪侦听器是线程安全的全局锁。</span><span class="sxs-lookup"><span data-stu-id="2f23c-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="2f23c-145">`autoflush`属性设置为`true`，这将导致跟踪侦听器写入到文件而不考虑是否<xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType>调用方法。</span><span class="sxs-lookup"><span data-stu-id="2f23c-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="2f23c-146">`indentsize`属性设置为 0 （零），这会导致要缩进没有任何空间的侦听器时<xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType>调用方法。</span><span class="sxs-lookup"><span data-stu-id="2f23c-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f23c-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f23c-147">See also</span></span>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="2f23c-148">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="2f23c-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
