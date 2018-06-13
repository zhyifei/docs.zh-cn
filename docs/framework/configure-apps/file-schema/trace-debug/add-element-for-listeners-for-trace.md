---
title: '&lt;添加&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e27187c05b49b7f73ef19243a3286e8c1de71579
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747341"
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="529e8-102">&lt;添加&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;</span><span class="sxs-lookup"><span data-stu-id="529e8-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="529e8-103">将侦听器添加到**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="529e8-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="529e8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="529e8-104">\<configuration></span></span>  
<span data-ttu-id="529e8-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="529e8-105">\<system.diagnostics></span></span>  
<span data-ttu-id="529e8-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="529e8-106">\<trace></span></span>  
<span data-ttu-id="529e8-107">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="529e8-107">\<listeners></span></span>  
<span data-ttu-id="529e8-108">\<add></span><span class="sxs-lookup"><span data-stu-id="529e8-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="529e8-109">语法</span><span class="sxs-lookup"><span data-stu-id="529e8-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="529e8-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="529e8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="529e8-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="529e8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="529e8-112">特性</span><span class="sxs-lookup"><span data-stu-id="529e8-112">Attributes</span></span>  
  
|<span data-ttu-id="529e8-113">特性</span><span class="sxs-lookup"><span data-stu-id="529e8-113">Attribute</span></span>|<span data-ttu-id="529e8-114">描述</span><span class="sxs-lookup"><span data-stu-id="529e8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="529e8-115">**type**</span><span class="sxs-lookup"><span data-stu-id="529e8-115">**type**</span></span>|<span data-ttu-id="529e8-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="529e8-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="529e8-117">指定侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="529e8-117">Specifies the type of the listener.</span></span> <span data-ttu-id="529e8-118">你必须使用满足要求中指定的字符串[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="529e8-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="529e8-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="529e8-119">**initializeData**</span></span>|<span data-ttu-id="529e8-120">可选特性。</span><span class="sxs-lookup"><span data-stu-id="529e8-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="529e8-121">传递给构造函数指定类的字符串。</span><span class="sxs-lookup"><span data-stu-id="529e8-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="529e8-122">**name**</span><span class="sxs-lookup"><span data-stu-id="529e8-122">**name**</span></span>|<span data-ttu-id="529e8-123">可选特性。</span><span class="sxs-lookup"><span data-stu-id="529e8-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="529e8-124">指定侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="529e8-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="529e8-125">子元素</span><span class="sxs-lookup"><span data-stu-id="529e8-125">Child Elements</span></span>  
  
|<span data-ttu-id="529e8-126">元素</span><span class="sxs-lookup"><span data-stu-id="529e8-126">Element</span></span>|<span data-ttu-id="529e8-127">描述</span><span class="sxs-lookup"><span data-stu-id="529e8-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="529e8-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="529e8-128">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="529e8-129">将筛选器添加到中的侦听器`Listeners`跟踪的集合。</span><span class="sxs-lookup"><span data-stu-id="529e8-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="529e8-130">父元素</span><span class="sxs-lookup"><span data-stu-id="529e8-130">Parent Elements</span></span>  
  
|<span data-ttu-id="529e8-131">元素</span><span class="sxs-lookup"><span data-stu-id="529e8-131">Element</span></span>|<span data-ttu-id="529e8-132">描述</span><span class="sxs-lookup"><span data-stu-id="529e8-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="529e8-133">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="529e8-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="529e8-134">指定收集，侦听器存储区，并将消息路由。</span><span class="sxs-lookup"><span data-stu-id="529e8-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="529e8-135">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="529e8-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="529e8-136">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="529e8-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="529e8-137">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="529e8-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="529e8-138">备注</span><span class="sxs-lookup"><span data-stu-id="529e8-138">Remarks</span></span>  
 <span data-ttu-id="529e8-139"><xref:System.Diagnostics.Debug>和<xref:System.Diagnostics.Trace>类共用同一个**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="529e8-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="529e8-140">如果你将侦听器对象添加到这些类之一中的集合，其他类将使用相同的侦听器。</span><span class="sxs-lookup"><span data-stu-id="529e8-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="529e8-141">侦听器类派生自<xref:System.Diagnostics.TraceListener>。</span><span class="sxs-lookup"><span data-stu-id="529e8-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="529e8-142">如果不指定`name`特性，则跟踪侦听器，<xref:System.Diagnostics.TraceListener.Name%2A>的跟踪侦听器默认值为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="529e8-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="529e8-143">如果你的应用程序具有一个侦听器，可以将其添加而无需指定一个名称，并将其删除通过指定名称为空字符串。</span><span class="sxs-lookup"><span data-stu-id="529e8-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="529e8-144">但是，如果你的应用程序具有多个侦听器，则应指定为每个跟踪侦听器，这样就可以识别和管理各个跟踪侦听器中的唯一名称<xref:System.Diagnostics.Debug.Listeners%2A>和<xref:System.Diagnostics.Trace.Listeners%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="529e8-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="529e8-145">添加多个跟踪侦听器的相同类型条件且具有相同名称只有一个跟踪侦听器中的该类型的结果和名称添加到`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="529e8-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="529e8-146">但是，你可以以编程方式添加到多个完全相同的侦听器`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="529e8-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="529e8-147">值**initializeData**属性取决于你创建的侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="529e8-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="529e8-148">并非所有的跟踪侦听器需要你指定**initializeData**。</span><span class="sxs-lookup"><span data-stu-id="529e8-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="529e8-149">当你使用`initializeData`属性中，你可能会收到编译器警告"未声明 initializeData 特性。"</span><span class="sxs-lookup"><span data-stu-id="529e8-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="529e8-150">因为配置设置验证针对的抽象基类，会出现此警告<xref:System.Diagnostics.TraceListener>，这不能识别`initializeData`属性。</span><span class="sxs-lookup"><span data-stu-id="529e8-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="529e8-151">通常情况下，你可以忽略此警告的具有构造函数采用参数的跟踪侦听器实现。</span><span class="sxs-lookup"><span data-stu-id="529e8-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="529e8-152">下表显示.NET Framework 附带的跟踪侦听器，并描述的值的其**initializeData**属性。</span><span class="sxs-lookup"><span data-stu-id="529e8-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="529e8-153">跟踪侦听器类</span><span class="sxs-lookup"><span data-stu-id="529e8-153">Trace listener class</span></span>|<span data-ttu-id="529e8-154">initializeData 特性值</span><span class="sxs-lookup"><span data-stu-id="529e8-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="529e8-155">`useErrorStream`值<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="529e8-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="529e8-156">设置`initializeData`属性设为"`true`"编写跟踪和调试输出到<xref:System.Console.Error%2A?displayProperty=nameWithType>;"`false`"写入<xref:System.Console.Out%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="529e8-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="529e8-157">文件的名称<xref:System.Diagnostics.DelimitedListTraceListener>写入。</span><span class="sxs-lookup"><span data-stu-id="529e8-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="529e8-158">现有的事件日志源的名称的名称。</span><span class="sxs-lookup"><span data-stu-id="529e8-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="529e8-159">文件的名称，<xref:System.Diagnostics.EventSchemaTraceListener>写入。</span><span class="sxs-lookup"><span data-stu-id="529e8-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="529e8-160">文件的名称，<xref:System.Diagnostics.TextWriterTraceListener>写入。</span><span class="sxs-lookup"><span data-stu-id="529e8-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="529e8-161">文件的名称，<xref:System.Diagnostics.XmlWriterTraceListener>写入。</span><span class="sxs-lookup"><span data-stu-id="529e8-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="529e8-162">示例</span><span class="sxs-lookup"><span data-stu-id="529e8-162">Example</span></span>  
 <span data-ttu-id="529e8-163">下面的示例演示如何使用**\<添加 >** 元素将侦听器`MyListener`和`MyEventListener`到**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="529e8-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="529e8-164">`MyListener` 创建名为的文件`MyListener.log`并将输出写入文件。</span><span class="sxs-lookup"><span data-stu-id="529e8-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="529e8-165">`MyEventListener` 事件日志中创建的项。</span><span class="sxs-lookup"><span data-stu-id="529e8-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="529e8-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="529e8-166">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [<span data-ttu-id="529e8-167">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="529e8-167">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="529e8-168">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="529e8-168">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
