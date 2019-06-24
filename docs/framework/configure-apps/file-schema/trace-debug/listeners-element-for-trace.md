---
title: <trace> 的 <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: f9f12d9e61e2472b897169727bbb4fbf9833efd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701341"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="b80eb-102">\<侦听器 > 元素\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="b80eb-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="b80eb-103">指定的侦听器，可收集、 存储，并将消息路由。</span><span class="sxs-lookup"><span data-stu-id="b80eb-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="b80eb-104">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="b80eb-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="b80eb-105">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="b80eb-105">\<configuration> Element</span></span>  
<span data-ttu-id="b80eb-106">\<system.diagnostics > 元素</span><span class="sxs-lookup"><span data-stu-id="b80eb-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="b80eb-107">\<跟踪 > 元素</span><span class="sxs-lookup"><span data-stu-id="b80eb-107">\<trace> Element</span></span>  
<span data-ttu-id="b80eb-108">\<侦听器 > 元素\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="b80eb-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80eb-109">语法</span><span class="sxs-lookup"><span data-stu-id="b80eb-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b80eb-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b80eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b80eb-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b80eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b80eb-112">特性</span><span class="sxs-lookup"><span data-stu-id="b80eb-112">Attributes</span></span>  
 <span data-ttu-id="b80eb-113">无。</span><span class="sxs-lookup"><span data-stu-id="b80eb-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b80eb-114">子元素</span><span class="sxs-lookup"><span data-stu-id="b80eb-114">Child Elements</span></span>  
  
|<span data-ttu-id="b80eb-115">元素</span><span class="sxs-lookup"><span data-stu-id="b80eb-115">Element</span></span>|<span data-ttu-id="b80eb-116">描述</span><span class="sxs-lookup"><span data-stu-id="b80eb-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b80eb-117">\<add></span><span class="sxs-lookup"><span data-stu-id="b80eb-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="b80eb-118">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="b80eb-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="b80eb-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="b80eb-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="b80eb-120">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="b80eb-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="b80eb-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="b80eb-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="b80eb-122">删除从侦听器`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="b80eb-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b80eb-123">父元素</span><span class="sxs-lookup"><span data-stu-id="b80eb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b80eb-124">元素</span><span class="sxs-lookup"><span data-stu-id="b80eb-124">Element</span></span>|<span data-ttu-id="b80eb-125">描述</span><span class="sxs-lookup"><span data-stu-id="b80eb-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b80eb-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b80eb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b80eb-127">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="b80eb-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="b80eb-128">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="b80eb-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b80eb-129">备注</span><span class="sxs-lookup"><span data-stu-id="b80eb-129">Remarks</span></span>  
 <span data-ttu-id="b80eb-130"><xref:System.Diagnostics.Debug>并<xref:System.Diagnostics.Trace>类将共享相同**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="b80eb-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="b80eb-131">如果将侦听器对象添加到在其中一个类的集合，其他类将使用相同的侦听器。</span><span class="sxs-lookup"><span data-stu-id="b80eb-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="b80eb-132">.NET Framework 附带的侦听器类派生<xref:System.Diagnostics.TraceListener>类。</span><span class="sxs-lookup"><span data-stu-id="b80eb-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b80eb-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="b80eb-133">Configuration File</span></span>  
 <span data-ttu-id="b80eb-134">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="b80eb-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b80eb-135">示例</span><span class="sxs-lookup"><span data-stu-id="b80eb-135">Example</span></span>  
 <span data-ttu-id="b80eb-136">下面的示例演示如何使用 **\<侦听器>** 元素添加侦听器`MyListener`并`MyEventListener`到**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="b80eb-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="b80eb-137">`MyListener` 创建一个名为文件`MyListener.log`并将输出写入到该文件。</span><span class="sxs-lookup"><span data-stu-id="b80eb-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="b80eb-138">`MyEventListener` 事件日志中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="b80eb-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b80eb-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b80eb-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="b80eb-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="b80eb-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
