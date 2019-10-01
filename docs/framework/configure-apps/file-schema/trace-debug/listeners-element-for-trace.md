---
title: <trace> 的 <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 84b67532825372e7f69d86e1ef6060f4263587eb
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699356"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="bddf8-102">\<trace 的 @no__t 0listeners > 元素 ></span><span class="sxs-lookup"><span data-stu-id="bddf8-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="bddf8-103">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="bddf8-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="bddf8-104">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="bddf8-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
[<span data-ttu-id="bddf8-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="bddf8-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="bddf8-106">&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="bddf8-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="bddf8-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="bddf8-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="bddf8-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<listeners >**</span><span class="sxs-lookup"><span data-stu-id="bddf8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bddf8-109">语法</span><span class="sxs-lookup"><span data-stu-id="bddf8-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bddf8-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bddf8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bddf8-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bddf8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bddf8-112">特性</span><span class="sxs-lookup"><span data-stu-id="bddf8-112">Attributes</span></span>  
 <span data-ttu-id="bddf8-113">无。</span><span class="sxs-lookup"><span data-stu-id="bddf8-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bddf8-114">子元素</span><span class="sxs-lookup"><span data-stu-id="bddf8-114">Child Elements</span></span>  
  
|<span data-ttu-id="bddf8-115">元素</span><span class="sxs-lookup"><span data-stu-id="bddf8-115">Element</span></span>|<span data-ttu-id="bddf8-116">描述</span><span class="sxs-lookup"><span data-stu-id="bddf8-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bddf8-117">\<add></span><span class="sxs-lookup"><span data-stu-id="bddf8-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="bddf8-118">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="bddf8-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="bddf8-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="bddf8-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="bddf8-120">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="bddf8-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="bddf8-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="bddf8-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="bddf8-122">从 @no__t 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="bddf8-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bddf8-123">父元素</span><span class="sxs-lookup"><span data-stu-id="bddf8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bddf8-124">元素</span><span class="sxs-lookup"><span data-stu-id="bddf8-124">Element</span></span>|<span data-ttu-id="bddf8-125">描述</span><span class="sxs-lookup"><span data-stu-id="bddf8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bddf8-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="bddf8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bddf8-127">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="bddf8-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="bddf8-128">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="bddf8-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bddf8-129">备注</span><span class="sxs-lookup"><span data-stu-id="bddf8-129">Remarks</span></span>  
 <span data-ttu-id="bddf8-130">@No__t 0 和 @no__t 1 类共享相同的**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="bddf8-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="bddf8-131">如果将侦听器对象添加到其中一个类的集合中，则其他类将使用同一侦听器。</span><span class="sxs-lookup"><span data-stu-id="bddf8-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="bddf8-132">随 .NET Framework 附带的侦听器类派生自 @no__t 的类。</span><span class="sxs-lookup"><span data-stu-id="bddf8-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="bddf8-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="bddf8-133">Configuration File</span></span>  
 <span data-ttu-id="bddf8-134">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="bddf8-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bddf8-135">示例</span><span class="sxs-lookup"><span data-stu-id="bddf8-135">Example</span></span>  
 <span data-ttu-id="bddf8-136">下面的示例演示如何使用 **\<侦听器>** 元素添加侦听器`MyListener`并`MyEventListener`到**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="bddf8-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="bddf8-137">@no__t 创建一个名为 @no__t 的文件，并将输出写入文件。</span><span class="sxs-lookup"><span data-stu-id="bddf8-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="bddf8-138">`MyEventListener` 会在事件日志中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="bddf8-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bddf8-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="bddf8-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="bddf8-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="bddf8-140">Trace and Debug Settings Schema</span></span>](index.md)
