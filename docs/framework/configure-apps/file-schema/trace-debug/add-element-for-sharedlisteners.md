---
title: <sharedListeners> 的 <add> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153602"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="eaf21-102">\<添加 sharedListeners 的\<> 元素></span><span class="sxs-lookup"><span data-stu-id="eaf21-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="eaf21-103">将侦听器添加到 `sharedListeners` 集合中。</span><span class="sxs-lookup"><span data-stu-id="eaf21-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="eaf21-104">`sharedListeners`是任何[ \<源>](source-element.md)或[ \<跟踪>](trace-element.md)都可以引用的侦听器的集合。</span><span class="sxs-lookup"><span data-stu-id="eaf21-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="eaf21-105">默认情况下，集合中`sharedListeners`的侦听器不会放置在`Listeners`集合中。</span><span class="sxs-lookup"><span data-stu-id="eaf21-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="eaf21-106">必须按名称将它们添加到[ \<源>](source-element.md)或[ \<跟踪>](trace-element.md)。</span><span class="sxs-lookup"><span data-stu-id="eaf21-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="eaf21-107">在运行时，不能在代码中获取`sharedListeners`集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="eaf21-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

<span data-ttu-id="eaf21-108">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaf21-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eaf21-109">&nbsp;&nbsp;[**\<诊断>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaf21-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="eaf21-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaf21-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="eaf21-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**</span><span class="sxs-lookup"><span data-stu-id="eaf21-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="eaf21-112">语法</span><span class="sxs-lookup"><span data-stu-id="eaf21-112">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaf21-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="eaf21-113">Attributes and Elements</span></span>  
 <span data-ttu-id="eaf21-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="eaf21-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaf21-115">特性</span><span class="sxs-lookup"><span data-stu-id="eaf21-115">Attributes</span></span>  
  
|<span data-ttu-id="eaf21-116">特性</span><span class="sxs-lookup"><span data-stu-id="eaf21-116">Attribute</span></span>|<span data-ttu-id="eaf21-117">描述</span><span class="sxs-lookup"><span data-stu-id="eaf21-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="eaf21-118">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="eaf21-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="eaf21-119">指定用于将共享侦听器添加到`Listeners`集合中的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="eaf21-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="eaf21-120">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="eaf21-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="eaf21-121">指定侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="eaf21-121">Specifies the type of the listener.</span></span> <span data-ttu-id="eaf21-122">必须使用满足指定[完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)中指定的要求的字符串。</span><span class="sxs-lookup"><span data-stu-id="eaf21-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="eaf21-123">可选特性。</span><span class="sxs-lookup"><span data-stu-id="eaf21-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="eaf21-124">传递到指定类的构造函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="eaf21-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="eaf21-125">可选特性。</span><span class="sxs-lookup"><span data-stu-id="eaf21-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="eaf21-126">指示要写入跟踪输出的数据<xref:System.Diagnostics.TraceOptions>的一个或多个枚举成员的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="eaf21-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="eaf21-127">多个项之间以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="eaf21-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="eaf21-128">默认值为 "None"。</span><span class="sxs-lookup"><span data-stu-id="eaf21-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="eaf21-129">子元素</span><span class="sxs-lookup"><span data-stu-id="eaf21-129">Child Elements</span></span>  
  
|<span data-ttu-id="eaf21-130">元素</span><span class="sxs-lookup"><span data-stu-id="eaf21-130">Element</span></span>|<span data-ttu-id="eaf21-131">说明</span><span class="sxs-lookup"><span data-stu-id="eaf21-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaf21-132">\<筛选></span><span class="sxs-lookup"><span data-stu-id="eaf21-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="eaf21-133">将筛选器添加到 `sharedListeners` 集合中的侦听器。</span><span class="sxs-lookup"><span data-stu-id="eaf21-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eaf21-134">父元素</span><span class="sxs-lookup"><span data-stu-id="eaf21-134">Parent Elements</span></span>  
  
|<span data-ttu-id="eaf21-135">元素</span><span class="sxs-lookup"><span data-stu-id="eaf21-135">Element</span></span>|<span data-ttu-id="eaf21-136">说明</span><span class="sxs-lookup"><span data-stu-id="eaf21-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eaf21-137">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="eaf21-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="eaf21-138">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="eaf21-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="eaf21-139">任何源或跟踪元素都可以引用的侦听器的集合。</span><span class="sxs-lookup"><span data-stu-id="eaf21-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaf21-140">备注</span><span class="sxs-lookup"><span data-stu-id="eaf21-140">Remarks</span></span>  
 <span data-ttu-id="eaf21-141">随 .NET Framework 附带的侦听器类派生自<xref:System.Diagnostics.TraceListener>类。</span><span class="sxs-lookup"><span data-stu-id="eaf21-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="eaf21-142">`name`特性的值用于将共享侦听器添加到跟踪源或跟踪源`Listeners`的集合中。</span><span class="sxs-lookup"><span data-stu-id="eaf21-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="eaf21-143">该`initializeData`属性的值取决于所创建的侦听器的类型。</span><span class="sxs-lookup"><span data-stu-id="eaf21-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="eaf21-144">并非所有跟踪侦听器都要求您指定`initializeData`。</span><span class="sxs-lookup"><span data-stu-id="eaf21-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eaf21-145">使用`initializeData`属性时，可能会收到编译器警告 "未声明 ' initializeData ' 特性"。</span><span class="sxs-lookup"><span data-stu-id="eaf21-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="eaf21-146">之所以出现此警告<xref:System.Diagnostics.TraceListener>，是因为配置设置是针对抽象基类验证的，后者不识别`initializeData`属性。</span><span class="sxs-lookup"><span data-stu-id="eaf21-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="eaf21-147">通常，对于具有采用参数的构造函数的跟踪侦听器实现，你可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="eaf21-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="eaf21-148">下表显示了 .NET Framework 附带的跟踪侦听器，并描述了其`initializeData`属性的值。</span><span class="sxs-lookup"><span data-stu-id="eaf21-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="eaf21-149">跟踪侦听器类</span><span class="sxs-lookup"><span data-stu-id="eaf21-149">Trace listener class</span></span>|<span data-ttu-id="eaf21-150">initializeData 特性值</span><span class="sxs-lookup"><span data-stu-id="eaf21-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="eaf21-151"><xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>构造函数的`useErrorStream`值。</span><span class="sxs-lookup"><span data-stu-id="eaf21-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="eaf21-152">将`initializeData`属性设置为 "`true`" 可将跟踪和调试输出写入标准错误流;将其设置为`false`"" 即可写入标准输出流。</span><span class="sxs-lookup"><span data-stu-id="eaf21-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="eaf21-153"><xref:System.Diagnostics.DelimitedListTraceListener> 写入的文件名。</span><span class="sxs-lookup"><span data-stu-id="eaf21-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="eaf21-154">现有的事件日志源的名称。</span><span class="sxs-lookup"><span data-stu-id="eaf21-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="eaf21-155"><xref:System.Diagnostics.EventSchemaTraceListener>写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="eaf21-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="eaf21-156"><xref:System.Diagnostics.TextWriterTraceListener>写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="eaf21-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="eaf21-157"><xref:System.Diagnostics.XmlWriterTraceListener>写入的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="eaf21-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="eaf21-158">配置文件</span><span class="sxs-lookup"><span data-stu-id="eaf21-158">Configuration File</span></span>  
 <span data-ttu-id="eaf21-159">此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="eaf21-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eaf21-160">示例</span><span class="sxs-lookup"><span data-stu-id="eaf21-160">Example</span></span>  
 <span data-ttu-id="eaf21-161">下面的示例`<add>`演示如何使用元素将添加<xref:System.Diagnostics.TextWriterTraceListener> `textListener`到`sharedListeners`集合中。</span><span class="sxs-lookup"><span data-stu-id="eaf21-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="eaf21-162">`textListener`按名称添加到跟踪源`Listeners` `TraceSourceApp`的集合中。</span><span class="sxs-lookup"><span data-stu-id="eaf21-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="eaf21-163">`textListener`侦听器将跟踪输出写入文件 myListener。</span><span class="sxs-lookup"><span data-stu-id="eaf21-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eaf21-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eaf21-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="eaf21-165">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="eaf21-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eaf21-166">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="eaf21-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
