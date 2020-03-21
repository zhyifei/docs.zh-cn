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
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153161"
---
# <a name="trace-element"></a><span data-ttu-id="18f48-102">\<跟踪>元素</span><span class="sxs-lookup"><span data-stu-id="18f48-102">\<trace> Element</span></span>
<span data-ttu-id="18f48-103">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="18f48-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[<span data-ttu-id="18f48-104">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="18f48-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="18f48-105">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="18f48-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="18f48-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<跟踪>**</span><span class="sxs-lookup"><span data-stu-id="18f48-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f48-107">语法</span><span class="sxs-lookup"><span data-stu-id="18f48-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18f48-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="18f48-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18f48-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="18f48-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18f48-110">属性</span><span class="sxs-lookup"><span data-stu-id="18f48-110">Attributes</span></span>  
  
|<span data-ttu-id="18f48-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="18f48-111">Attribute</span></span>|<span data-ttu-id="18f48-112">说明</span><span class="sxs-lookup"><span data-stu-id="18f48-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="18f48-113">可选特性。</span><span class="sxs-lookup"><span data-stu-id="18f48-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="18f48-114">指定跟踪侦听器在每个写入操作后是否自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="18f48-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="18f48-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="18f48-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="18f48-116">指定缩进空格数。</span><span class="sxs-lookup"><span data-stu-id="18f48-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="18f48-117">可选特性。</span><span class="sxs-lookup"><span data-stu-id="18f48-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="18f48-118">指示是否应使用全局锁。</span><span class="sxs-lookup"><span data-stu-id="18f48-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="18f48-119">自动刷新属性</span><span class="sxs-lookup"><span data-stu-id="18f48-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="18f48-120">值</span><span class="sxs-lookup"><span data-stu-id="18f48-120">Value</span></span>|<span data-ttu-id="18f48-121">说明</span><span class="sxs-lookup"><span data-stu-id="18f48-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="18f48-122">不会自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="18f48-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="18f48-123">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="18f48-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="18f48-124">自动刷新输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="18f48-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="18f48-125">使用全局锁定属性</span><span class="sxs-lookup"><span data-stu-id="18f48-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="18f48-126">值</span><span class="sxs-lookup"><span data-stu-id="18f48-126">Value</span></span>|<span data-ttu-id="18f48-127">说明</span><span class="sxs-lookup"><span data-stu-id="18f48-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="18f48-128">如果侦听器是线程安全的，则不使用全局锁;否则，使用全局锁。</span><span class="sxs-lookup"><span data-stu-id="18f48-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="18f48-129">无论侦听器是否安全，都使用全局锁。</span><span class="sxs-lookup"><span data-stu-id="18f48-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="18f48-130">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="18f48-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18f48-131">子元素</span><span class="sxs-lookup"><span data-stu-id="18f48-131">Child Elements</span></span>  
  
|<span data-ttu-id="18f48-132">元素</span><span class="sxs-lookup"><span data-stu-id="18f48-132">Element</span></span>|<span data-ttu-id="18f48-133">说明</span><span class="sxs-lookup"><span data-stu-id="18f48-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18f48-134">\<听众></span><span class="sxs-lookup"><span data-stu-id="18f48-134">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="18f48-135">指定收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="18f48-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18f48-136">父元素</span><span class="sxs-lookup"><span data-stu-id="18f48-136">Parent Elements</span></span>  
  
|<span data-ttu-id="18f48-137">元素</span><span class="sxs-lookup"><span data-stu-id="18f48-137">Element</span></span>|<span data-ttu-id="18f48-138">说明</span><span class="sxs-lookup"><span data-stu-id="18f48-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="18f48-139">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="18f48-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="18f48-140">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="18f48-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="18f48-141">示例</span><span class="sxs-lookup"><span data-stu-id="18f48-141">Example</span></span>  
 <span data-ttu-id="18f48-142">下面的示例演示如何使用 元素`<trace>`将侦听器`MyListener`添加到`Listeners`集合中。</span><span class="sxs-lookup"><span data-stu-id="18f48-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="18f48-143">`MyListener`创建命名`MyListener.log`的文件并将输出写入该文件。</span><span class="sxs-lookup"><span data-stu-id="18f48-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="18f48-144">属性`useGlobalLock`设置为`false`，这将导致在跟踪侦听器是线程安全的时不使用全局锁。</span><span class="sxs-lookup"><span data-stu-id="18f48-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="18f48-145">属性`autoflush`设置为`true`，这将导致跟踪侦听器写入文件，而不考虑是否调用<xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType>该方法。</span><span class="sxs-lookup"><span data-stu-id="18f48-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="18f48-146">属性`indentsize`设置为 0（零），这将导致调用<xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType>方法时侦听器缩进零空格。</span><span class="sxs-lookup"><span data-stu-id="18f48-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="18f48-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18f48-147">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="18f48-148">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="18f48-148">Trace and Debug Settings Schema</span></span>](index.md)
