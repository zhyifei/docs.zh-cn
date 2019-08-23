---
title: <add><listeners>的元素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: d4ff919991ab1505b2845a225706d32cc1e57d0a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920574"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="8c776-102">\<为\<跟踪 > 添加\<侦听器 > > 元素</span><span class="sxs-lookup"><span data-stu-id="8c776-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="8c776-103">向**侦听器**集合添加侦听器。</span><span class="sxs-lookup"><span data-stu-id="8c776-103">Adds a listener to the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="8c776-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8c776-104">\<configuration></span></span>  
<span data-ttu-id="8c776-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="8c776-105">\<system.diagnostics></span></span>  
<span data-ttu-id="8c776-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="8c776-106">\<trace></span></span>  
<span data-ttu-id="8c776-107">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="8c776-107">\<listeners></span></span>  
<span data-ttu-id="8c776-108">\<add></span><span class="sxs-lookup"><span data-stu-id="8c776-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c776-109">语法</span><span class="sxs-lookup"><span data-stu-id="8c776-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c776-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8c776-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8c776-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8c776-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c776-112">特性</span><span class="sxs-lookup"><span data-stu-id="8c776-112">Attributes</span></span>  
  
|<span data-ttu-id="8c776-113">特性</span><span class="sxs-lookup"><span data-stu-id="8c776-113">Attribute</span></span>|<span data-ttu-id="8c776-114">描述</span><span class="sxs-lookup"><span data-stu-id="8c776-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c776-115">**type**</span><span class="sxs-lookup"><span data-stu-id="8c776-115">**type**</span></span>|<span data-ttu-id="8c776-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="8c776-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="8c776-117">指定侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="8c776-117">Specifies the type of the listener.</span></span> <span data-ttu-id="8c776-118">必须使用满足指定[完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)中指定的要求的字符串。</span><span class="sxs-lookup"><span data-stu-id="8c776-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="8c776-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="8c776-119">**initializeData**</span></span>|<span data-ttu-id="8c776-120">可选特性。</span><span class="sxs-lookup"><span data-stu-id="8c776-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8c776-121">传递到指定类的构造函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="8c776-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="8c776-122">**名称**</span><span class="sxs-lookup"><span data-stu-id="8c776-122">**name**</span></span>|<span data-ttu-id="8c776-123">可选特性。</span><span class="sxs-lookup"><span data-stu-id="8c776-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8c776-124">指定侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="8c776-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c776-125">子元素</span><span class="sxs-lookup"><span data-stu-id="8c776-125">Child Elements</span></span>  
  
|<span data-ttu-id="8c776-126">元素</span><span class="sxs-lookup"><span data-stu-id="8c776-126">Element</span></span>|<span data-ttu-id="8c776-127">描述</span><span class="sxs-lookup"><span data-stu-id="8c776-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c776-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="8c776-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="8c776-129">将筛选器添加到跟踪的`Listeners`集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="8c776-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c776-130">父元素</span><span class="sxs-lookup"><span data-stu-id="8c776-130">Parent Elements</span></span>  
  
|<span data-ttu-id="8c776-131">元素</span><span class="sxs-lookup"><span data-stu-id="8c776-131">Element</span></span>|<span data-ttu-id="8c776-132">描述</span><span class="sxs-lookup"><span data-stu-id="8c776-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8c776-133">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="8c776-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="8c776-134">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="8c776-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="8c776-135">侦听器将跟踪输出定向到适当的目标。</span><span class="sxs-lookup"><span data-stu-id="8c776-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8c776-136">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="8c776-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="8c776-137">包含用于收集、存储和路由跟踪消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="8c776-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c776-138">备注</span><span class="sxs-lookup"><span data-stu-id="8c776-138">Remarks</span></span>  
 <span data-ttu-id="8c776-139">和类共享相同的侦听器集合。 <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace></span><span class="sxs-lookup"><span data-stu-id="8c776-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="8c776-140">如果将侦听器对象添加到其中一个类的集合中, 则其他类将使用同一侦听器。</span><span class="sxs-lookup"><span data-stu-id="8c776-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="8c776-141">侦听器类派生自<xref:System.Diagnostics.TraceListener>。</span><span class="sxs-lookup"><span data-stu-id="8c776-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="8c776-142">如果未指定`name`跟踪侦听器的属性<xref:System.Diagnostics.TraceListener.Name%2A> , 则跟踪侦听器的默认值为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="8c776-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="8c776-143">如果你的应用程序只有一个侦听器, 则可以在不指定名称的情况下进行添加, 并通过为该名称指定一个空字符串来将其删除。</span><span class="sxs-lookup"><span data-stu-id="8c776-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="8c776-144">但是, 如果应用程序有多个侦听器, 则应为每个跟踪侦听器指定唯一的名称, 以便在<xref:System.Diagnostics.Debug.Listeners%2A>和<xref:System.Diagnostics.Trace.Listeners%2A>集合中标识和管理单个跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="8c776-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c776-145">添加具有相同类型且具有相同名称的多个跟踪侦听器会导致只将该类型和名称的一个跟踪侦听器添加到`Listeners`集合中。</span><span class="sxs-lookup"><span data-stu-id="8c776-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="8c776-146">但是, 可以通过编程方式将多个相同的`Listeners`侦听器添加到集合中。</span><span class="sxs-lookup"><span data-stu-id="8c776-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="8c776-147">**InitializeData**属性的值取决于所创建的侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="8c776-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="8c776-148">并非所有跟踪侦听器都需要指定**initializeData**。</span><span class="sxs-lookup"><span data-stu-id="8c776-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c776-149">使用`initializeData`属性时, 可能会收到编译器警告 "未声明 ' initializeData ' 特性"。</span><span class="sxs-lookup"><span data-stu-id="8c776-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="8c776-150">之所以出现此警告<xref:System.Diagnostics.TraceListener>, 是因为配置设置是针对抽象基类验证的, 后者不`initializeData`识别属性。</span><span class="sxs-lookup"><span data-stu-id="8c776-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="8c776-151">通常, 对于具有采用参数的构造函数的跟踪侦听器实现, 你可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="8c776-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="8c776-152">下表显示了 .NET Framework 附带的跟踪侦听器, 并说明了其**initializeData**属性的值。</span><span class="sxs-lookup"><span data-stu-id="8c776-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="8c776-153">跟踪侦听器类</span><span class="sxs-lookup"><span data-stu-id="8c776-153">Trace listener class</span></span>|<span data-ttu-id="8c776-154">initializeData 特性值</span><span class="sxs-lookup"><span data-stu-id="8c776-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8c776-155"><xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>构造函数的`useErrorStream`值。</span><span class="sxs-lookup"><span data-stu-id="8c776-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="8c776-156">将属性设置为 "`true`" 可将<xref:System.Console.Error%2A?displayProperty=nameWithType>跟踪和调试输出写入; `initializeData``false`要<xref:System.Console.Out%2A?displayProperty=nameWithType>写入的 ""。</span><span class="sxs-lookup"><span data-stu-id="8c776-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8c776-157">写入的<xref:System.Diagnostics.DelimitedListTraceListener>文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8c776-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8c776-158">现有事件日志源的名称。</span><span class="sxs-lookup"><span data-stu-id="8c776-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8c776-159"><xref:System.Diagnostics.EventSchemaTraceListener>写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8c776-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8c776-160"><xref:System.Diagnostics.TextWriterTraceListener>写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8c776-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="8c776-161"><xref:System.Diagnostics.XmlWriterTraceListener>写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8c776-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c776-162">示例</span><span class="sxs-lookup"><span data-stu-id="8c776-162">Example</span></span>  
 <span data-ttu-id="8c776-163">下面的示例演示如何使用 **\<添加>** 元素添加侦听器`MyListener`并`MyEventListener`到**侦听器**集合。</span><span class="sxs-lookup"><span data-stu-id="8c776-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="8c776-164">`MyListener`创建一个名`MyListener.log`为的文件, 并将输出写入文件。</span><span class="sxs-lookup"><span data-stu-id="8c776-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="8c776-165">`MyEventListener`在事件日志中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="8c776-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c776-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c776-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="8c776-167">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="8c776-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8c776-168">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="8c776-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
