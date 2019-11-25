---
title: <source> 的 <listeners> 的 <add> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: c32205310f9fc451a5a55a943f925ee52f65c8a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088991"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="afa5d-102">\<为 \<源的 \<侦听器 > 添加 > 元素 ></span><span class="sxs-lookup"><span data-stu-id="afa5d-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="afa5d-103">将侦听器添加到跟踪源的 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="afa5d-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="afa5d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="afa5d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="afa5d-105">&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="afa5d-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="afa5d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="afa5d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="afa5d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<** ](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="afa5d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="afa5d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**侦听器 >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="afa5d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="afa5d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="afa5d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="afa5d-110">语法</span><span class="sxs-lookup"><span data-stu-id="afa5d-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afa5d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="afa5d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="afa5d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="afa5d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afa5d-113">特性</span><span class="sxs-lookup"><span data-stu-id="afa5d-113">Attributes</span></span>  
  
|<span data-ttu-id="afa5d-114">特性</span><span class="sxs-lookup"><span data-stu-id="afa5d-114">Attribute</span></span>|<span data-ttu-id="afa5d-115">描述</span><span class="sxs-lookup"><span data-stu-id="afa5d-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="afa5d-116">必需的属性，除非你引用 `sharedListeners` 集合中的侦听器，在这种情况下，你只需按名称引用它（请参阅[示例](#example)）。</span><span class="sxs-lookup"><span data-stu-id="afa5d-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="afa5d-117">指定侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="afa5d-117">Specifies the type of the listener.</span></span> <span data-ttu-id="afa5d-118">必须使用满足指定[完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)中指定的要求的字符串。</span><span class="sxs-lookup"><span data-stu-id="afa5d-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="afa5d-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="afa5d-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="afa5d-120">传递到指定类的构造函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="afa5d-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="afa5d-121">如果类不具有采用字符串的构造函数，则会引发 <xref:System.Configuration.ConfigurationException>。</span><span class="sxs-lookup"><span data-stu-id="afa5d-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="afa5d-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="afa5d-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="afa5d-123">指定侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="afa5d-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="afa5d-124">可选特性。</span><span class="sxs-lookup"><span data-stu-id="afa5d-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="afa5d-125">指定跟踪侦听器的 <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> 属性值。</span><span class="sxs-lookup"><span data-stu-id="afa5d-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="afa5d-126">[自定义属性]</span><span class="sxs-lookup"><span data-stu-id="afa5d-126">[custom attributes]</span></span>|<span data-ttu-id="afa5d-127">可选属性。</span><span class="sxs-lookup"><span data-stu-id="afa5d-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="afa5d-128">为该侦听器的 <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> 方法所标识的特定于侦听器的特性指定值。</span><span class="sxs-lookup"><span data-stu-id="afa5d-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="afa5d-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> 是 <xref:System.Diagnostics.DelimitedListTraceListener> 类独有的额外属性的示例。</span><span class="sxs-lookup"><span data-stu-id="afa5d-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afa5d-130">子元素</span><span class="sxs-lookup"><span data-stu-id="afa5d-130">Child Elements</span></span>  
  
|<span data-ttu-id="afa5d-131">元素</span><span class="sxs-lookup"><span data-stu-id="afa5d-131">Element</span></span>|<span data-ttu-id="afa5d-132">描述</span><span class="sxs-lookup"><span data-stu-id="afa5d-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa5d-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="afa5d-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="afa5d-134">将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="afa5d-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afa5d-135">父元素</span><span class="sxs-lookup"><span data-stu-id="afa5d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="afa5d-136">元素</span><span class="sxs-lookup"><span data-stu-id="afa5d-136">Element</span></span>|<span data-ttu-id="afa5d-137">描述</span><span class="sxs-lookup"><span data-stu-id="afa5d-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="afa5d-138">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="afa5d-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="afa5d-139">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="afa5d-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="afa5d-140">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="afa5d-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="afa5d-141">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="afa5d-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="afa5d-142">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="afa5d-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afa5d-143">备注</span><span class="sxs-lookup"><span data-stu-id="afa5d-143">Remarks</span></span>  
 <span data-ttu-id="afa5d-144">附带的侦听器类派生自 <xref:System.Diagnostics.TraceListener> 类 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="afa5d-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="afa5d-145">如果未指定跟踪侦听器的 `name` 属性，则跟踪侦听器的 <xref:System.Diagnostics.TraceListener.Name%2A> 属性默认为空字符串（""）。</span><span class="sxs-lookup"><span data-stu-id="afa5d-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="afa5d-146">如果你的应用程序只有一个侦听器，则可以在不指定名称的情况下添加它，并且可以通过为名称指定空字符串来删除它。</span><span class="sxs-lookup"><span data-stu-id="afa5d-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="afa5d-147">但是，如果应用程序有多个侦听器，则应为每个跟踪侦听器指定唯一的名称，以便在 <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> 集合中标识和管理单个跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="afa5d-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afa5d-148">添加具有相同类型且具有相同名称的多个跟踪侦听器会导致只将该类型和名称的一个跟踪侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="afa5d-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="afa5d-149">但是，可以通过编程方式将多个相同的侦听器添加到 `Listeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="afa5d-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="afa5d-150">`initializeData` 属性的值取决于所创建的侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="afa5d-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="afa5d-151">并非所有跟踪侦听器都要求您指定 `initializeData`。</span><span class="sxs-lookup"><span data-stu-id="afa5d-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afa5d-152">使用 `initializeData` 特性时，可能会收到编译器警告 "未声明 ' initializeData ' 特性"。</span><span class="sxs-lookup"><span data-stu-id="afa5d-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="afa5d-153">出现此警告的原因是，配置设置是根据 <xref:System.Diagnostics.TraceListener>的抽象基类验证的，该基类无法识别 `initializeData` 属性。</span><span class="sxs-lookup"><span data-stu-id="afa5d-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="afa5d-154">通常，对于具有采用参数的构造函数的跟踪侦听器实现，你可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="afa5d-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="afa5d-155">下表显示 .NET Framework 附带的跟踪侦听器，并描述其 `initializeData` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="afa5d-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="afa5d-156">跟踪侦听器类</span><span class="sxs-lookup"><span data-stu-id="afa5d-156">Trace listener class</span></span>|<span data-ttu-id="afa5d-157">initializeData 特性值</span><span class="sxs-lookup"><span data-stu-id="afa5d-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="afa5d-158"><xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 构造函数的 `useErrorStream` 值。</span><span class="sxs-lookup"><span data-stu-id="afa5d-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="afa5d-159">将 `initializeData` 特性设置为 "`true`" 可将跟踪和调试输出写入标准错误流;将其设置为 "`false`"，以写入标准输出流。</span><span class="sxs-lookup"><span data-stu-id="afa5d-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="afa5d-160"><xref:System.Diagnostics.DelimitedListTraceListener> 写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="afa5d-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="afa5d-161">现有事件日志源的名称。</span><span class="sxs-lookup"><span data-stu-id="afa5d-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="afa5d-162"><xref:System.Diagnostics.EventSchemaTraceListener> 写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="afa5d-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="afa5d-163"><xref:System.Diagnostics.TextWriterTraceListener> 写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="afa5d-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="afa5d-164"><xref:System.Diagnostics.XmlWriterTraceListener> 写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="afa5d-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="afa5d-165">配置文件</span><span class="sxs-lookup"><span data-stu-id="afa5d-165">Configuration File</span></span>  
 <span data-ttu-id="afa5d-166">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="afa5d-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afa5d-167">示例</span><span class="sxs-lookup"><span data-stu-id="afa5d-167">Example</span></span>  
 <span data-ttu-id="afa5d-168">下面的示例演示如何使用 `<add>` 元素将侦听器 `console` 和 `textListener` 添加到跟踪源 `TraceSourceApp`的 `Listeners` 集合。</span><span class="sxs-lookup"><span data-stu-id="afa5d-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="afa5d-169">`textListener` 侦听器将跟踪输出写入文件 myListener。</span><span class="sxs-lookup"><span data-stu-id="afa5d-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="afa5d-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="afa5d-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="afa5d-171">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="afa5d-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="afa5d-172">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="afa5d-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
