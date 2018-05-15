---
title: '&lt;添加&gt;元素&lt;侦听器&gt;为&lt;源&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ba8ff652003a9167ec370643797ac9300b83889a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="17ec0-102">&lt;添加&gt;元素&lt;侦听器&gt;为&lt;源&gt;</span><span class="sxs-lookup"><span data-stu-id="17ec0-102">&lt;add&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="17ec0-103">将侦听器添加到跟踪源的 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="17ec0-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="17ec0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="17ec0-104">\<configuration></span></span>  
<span data-ttu-id="17ec0-105">\<system.diagnostics ></span><span class="sxs-lookup"><span data-stu-id="17ec0-105">\<system.diagnostics></span></span>  
<span data-ttu-id="17ec0-106">\<源 ></span><span class="sxs-lookup"><span data-stu-id="17ec0-106">\<sources></span></span>  
<span data-ttu-id="17ec0-107">\<源 ></span><span class="sxs-lookup"><span data-stu-id="17ec0-107">\<source></span></span>  
<span data-ttu-id="17ec0-108">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="17ec0-108">\<listeners></span></span>  
<span data-ttu-id="17ec0-109">\<add></span><span class="sxs-lookup"><span data-stu-id="17ec0-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17ec0-110">语法</span><span class="sxs-lookup"><span data-stu-id="17ec0-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17ec0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="17ec0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="17ec0-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="17ec0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17ec0-113">特性</span><span class="sxs-lookup"><span data-stu-id="17ec0-113">Attributes</span></span>  
  
|<span data-ttu-id="17ec0-114">特性</span><span class="sxs-lookup"><span data-stu-id="17ec0-114">Attribute</span></span>|<span data-ttu-id="17ec0-115">描述</span><span class="sxs-lookup"><span data-stu-id="17ec0-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="17ec0-116">必需属性，除非您要引用中的侦听器`sharedListeners`集合，在其中种情况下，你只需按名称引用它 (请参阅[示例](#example))。</span><span class="sxs-lookup"><span data-stu-id="17ec0-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="17ec0-117">指定侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="17ec0-117">Specifies the type of the listener.</span></span> <span data-ttu-id="17ec0-118">你必须使用满足要求中指定的字符串[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="17ec0-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="17ec0-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="17ec0-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="17ec0-120">传递给构造函数指定类的字符串。</span><span class="sxs-lookup"><span data-stu-id="17ec0-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="17ec0-121">A<xref:System.Configuration.ConfigurationException>如果类没有采用字符串的构造函数引发。</span><span class="sxs-lookup"><span data-stu-id="17ec0-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="17ec0-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="17ec0-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="17ec0-123">指定侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="17ec0-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="17ec0-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="17ec0-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="17ec0-125">指定<xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A>跟踪侦听器的属性值。</span><span class="sxs-lookup"><span data-stu-id="17ec0-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="17ec0-126">[自定义属性]</span><span class="sxs-lookup"><span data-stu-id="17ec0-126">[custom attributes]</span></span>|<span data-ttu-id="17ec0-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="17ec0-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="17ec0-128">指定由标识的特定于侦听器的属性的值<xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A>为该侦听器的方法。</span><span class="sxs-lookup"><span data-stu-id="17ec0-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="17ec0-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> 是一个示例的额外特性的唯一的<xref:System.Diagnostics.DelimitedListTraceListener>类。</span><span class="sxs-lookup"><span data-stu-id="17ec0-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17ec0-130">子元素</span><span class="sxs-lookup"><span data-stu-id="17ec0-130">Child Elements</span></span>  
  
|<span data-ttu-id="17ec0-131">元素</span><span class="sxs-lookup"><span data-stu-id="17ec0-131">Element</span></span>|<span data-ttu-id="17ec0-132">描述</span><span class="sxs-lookup"><span data-stu-id="17ec0-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17ec0-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="17ec0-133">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="17ec0-134">将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="17ec0-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17ec0-135">父元素</span><span class="sxs-lookup"><span data-stu-id="17ec0-135">Parent Elements</span></span>  
  
|<span data-ttu-id="17ec0-136">元素</span><span class="sxs-lookup"><span data-stu-id="17ec0-136">Element</span></span>|<span data-ttu-id="17ec0-137">描述</span><span class="sxs-lookup"><span data-stu-id="17ec0-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="17ec0-138">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="17ec0-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="17ec0-139">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="17ec0-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="17ec0-140">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="17ec0-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="17ec0-141">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="17ec0-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="17ec0-142">指定收集、 存储和将消息路由的侦听器。</span><span class="sxs-lookup"><span data-stu-id="17ec0-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17ec0-143">备注</span><span class="sxs-lookup"><span data-stu-id="17ec0-143">Remarks</span></span>  
 <span data-ttu-id="17ec0-144">随.NET Framework 提供的侦听器类派生自<xref:System.Diagnostics.TraceListener>类。</span><span class="sxs-lookup"><span data-stu-id="17ec0-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="17ec0-145">如果不指定`name`特性，则跟踪侦听器，<xref:System.Diagnostics.TraceListener.Name%2A>的跟踪侦听器的属性默认为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="17ec0-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="17ec0-146">如果你的应用程序具有一个侦听器，而无需指定一个名称，您可以添加它，你可以通过指定名称为空字符串中删除它。</span><span class="sxs-lookup"><span data-stu-id="17ec0-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="17ec0-147">但是，如果你的应用程序具有多个侦听器，则应指定每个跟踪侦听器，这样就可以识别和管理各个跟踪侦听器中的唯一名称<xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType>集合。</span><span class="sxs-lookup"><span data-stu-id="17ec0-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17ec0-148">添加多个跟踪侦听器的相同类型条件且具有相同名称只有一个跟踪侦听器中的该类型的结果和名称添加到`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="17ec0-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="17ec0-149">但是，你可以以编程方式添加到多个完全相同的侦听器`Listeners`集合。</span><span class="sxs-lookup"><span data-stu-id="17ec0-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="17ec0-150">值`initializeData`属性取决于你创建的侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="17ec0-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="17ec0-151">并非所有的跟踪侦听器需要你指定`initializeData`。</span><span class="sxs-lookup"><span data-stu-id="17ec0-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17ec0-152">当你使用`initializeData`属性中，你可能会收到编译器警告"未声明 initializeData 特性。"</span><span class="sxs-lookup"><span data-stu-id="17ec0-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="17ec0-153">因为配置设置验证针对的抽象基类，会出现此警告<xref:System.Diagnostics.TraceListener>，这不能识别`initializeData`属性。</span><span class="sxs-lookup"><span data-stu-id="17ec0-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="17ec0-154">通常情况下，你可以忽略此警告的具有构造函数采用参数的跟踪侦听器实现。</span><span class="sxs-lookup"><span data-stu-id="17ec0-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="17ec0-155">下表显示.NET Framework 附带的跟踪侦听器，并描述的值的其`initializeData`属性。</span><span class="sxs-lookup"><span data-stu-id="17ec0-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="17ec0-156">跟踪侦听器类</span><span class="sxs-lookup"><span data-stu-id="17ec0-156">Trace listener class</span></span>|<span data-ttu-id="17ec0-157">initializeData 特性值</span><span class="sxs-lookup"><span data-stu-id="17ec0-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="17ec0-158">`useErrorStream`值<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="17ec0-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="17ec0-159">设置`initializeData`属性设为"`true`"编写跟踪和调试输出发送到标准错误流; 将其设置为"`false`"要写入到标准输出流。</span><span class="sxs-lookup"><span data-stu-id="17ec0-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="17ec0-160">文件的名称<xref:System.Diagnostics.DelimitedListTraceListener>写入。</span><span class="sxs-lookup"><span data-stu-id="17ec0-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="17ec0-161">现有的事件日志源的名称。</span><span class="sxs-lookup"><span data-stu-id="17ec0-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="17ec0-162">文件的名称，<xref:System.Diagnostics.EventSchemaTraceListener>写入。</span><span class="sxs-lookup"><span data-stu-id="17ec0-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="17ec0-163">文件的名称，<xref:System.Diagnostics.TextWriterTraceListener>写入。</span><span class="sxs-lookup"><span data-stu-id="17ec0-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="17ec0-164">文件的名称，<xref:System.Diagnostics.XmlWriterTraceListener>写入。</span><span class="sxs-lookup"><span data-stu-id="17ec0-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="17ec0-165">配置文件</span><span class="sxs-lookup"><span data-stu-id="17ec0-165">Configuration File</span></span>  
 <span data-ttu-id="17ec0-166">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="17ec0-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17ec0-167">示例</span><span class="sxs-lookup"><span data-stu-id="17ec0-167">Example</span></span>  
 <span data-ttu-id="17ec0-168">下面的示例演示如何使用`<add>`元素将侦听器`console`和`textListener`到`Listeners`跟踪源集合`TraceSourceApp`。</span><span class="sxs-lookup"><span data-stu-id="17ec0-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="17ec0-169">`textListener`侦听器将跟踪输出写入文件 myListener.log。</span><span class="sxs-lookup"><span data-stu-id="17ec0-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="17ec0-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="17ec0-170">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="17ec0-171">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="17ec0-171">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="17ec0-172">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="17ec0-172">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
