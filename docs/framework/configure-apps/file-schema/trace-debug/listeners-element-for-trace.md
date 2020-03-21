---
title: <trace> 的 <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: fd12be1b775d7611ef3f16d23147470313bf9866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153368"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="82588-102">\<侦听器>\<元素进行跟踪></span><span class="sxs-lookup"><span data-stu-id="82588-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="82588-103">指定收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="82588-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="82588-104">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="82588-104">Listeners direct the tracing output to an appropriate target.</span></span>  

<span data-ttu-id="82588-105">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="82588-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="82588-106">&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="82588-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="82588-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="82588-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="82588-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<听众>**</span><span class="sxs-lookup"><span data-stu-id="82588-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>

## <a name="syntax"></a><span data-ttu-id="82588-109">语法</span><span class="sxs-lookup"><span data-stu-id="82588-109">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82588-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="82588-110">Attributes and Elements</span></span>  
 <span data-ttu-id="82588-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="82588-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82588-112">属性</span><span class="sxs-lookup"><span data-stu-id="82588-112">Attributes</span></span>  
 <span data-ttu-id="82588-113">无。</span><span class="sxs-lookup"><span data-stu-id="82588-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82588-114">子元素</span><span class="sxs-lookup"><span data-stu-id="82588-114">Child Elements</span></span>  
  
|<span data-ttu-id="82588-115">元素</span><span class="sxs-lookup"><span data-stu-id="82588-115">Element</span></span>|<span data-ttu-id="82588-116">说明</span><span class="sxs-lookup"><span data-stu-id="82588-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82588-117">\<添加></span><span class="sxs-lookup"><span data-stu-id="82588-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="82588-118">将侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="82588-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="82588-119">\<明确></span><span class="sxs-lookup"><span data-stu-id="82588-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="82588-120">清除跟踪的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="82588-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="82588-121">\<删除></span><span class="sxs-lookup"><span data-stu-id="82588-121">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="82588-122">从`Listeners`集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="82588-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82588-123">父元素</span><span class="sxs-lookup"><span data-stu-id="82588-123">Parent Elements</span></span>  
  
|<span data-ttu-id="82588-124">元素</span><span class="sxs-lookup"><span data-stu-id="82588-124">Element</span></span>|<span data-ttu-id="82588-125">说明</span><span class="sxs-lookup"><span data-stu-id="82588-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="82588-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="82588-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="82588-127">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="82588-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="82588-128">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="82588-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82588-129">备注</span><span class="sxs-lookup"><span data-stu-id="82588-129">Remarks</span></span>  
 <span data-ttu-id="82588-130">和 类共享相同的**侦听器**集合。 <xref:System.Diagnostics.Trace> <xref:System.Diagnostics.Debug></span><span class="sxs-lookup"><span data-stu-id="82588-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="82588-131">如果向这些类之一的集合添加侦听器对象，则另一个类使用相同的侦听器。</span><span class="sxs-lookup"><span data-stu-id="82588-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="82588-132">.NET 框架附带的侦听器类派生自<xref:System.Diagnostics.TraceListener>该类。</span><span class="sxs-lookup"><span data-stu-id="82588-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="82588-133">配置文件</span><span class="sxs-lookup"><span data-stu-id="82588-133">Configuration File</span></span>  
 <span data-ttu-id="82588-134">此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="82588-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82588-135">示例</span><span class="sxs-lookup"><span data-stu-id="82588-135">Example</span></span>  
 <span data-ttu-id="82588-136">下面的示例演示如何使用**\<侦听器>** 元素将侦听器`MyListener`和`MyEventListener`**侦听器集合添加到侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="82588-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="82588-137">`MyListener`创建一个称为`MyListener.log`文件并将输出写入该文件。</span><span class="sxs-lookup"><span data-stu-id="82588-137">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="82588-138">`MyEventListener`在事件日志中创建条目。</span><span class="sxs-lookup"><span data-stu-id="82588-138">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82588-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82588-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="82588-140">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="82588-140">Trace and Debug Settings Schema</span></span>](index.md)
