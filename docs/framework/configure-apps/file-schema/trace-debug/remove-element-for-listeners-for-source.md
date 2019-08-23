---
title: <remove><listeners>的元素<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: edd27dd262004aead7db4d81db8ecab0e831dac1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926995"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="8a105-102">\<删除\<源 > 的\<侦听器 > > 元素</span><span class="sxs-lookup"><span data-stu-id="8a105-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="8a105-103">从跟踪源的 `Listeners` 集合中删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="8a105-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="8a105-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8a105-104">\<configuration></span></span>  
<span data-ttu-id="8a105-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="8a105-105">\<system.diagnostics></span></span>  
<span data-ttu-id="8a105-106">\<源 ></span><span class="sxs-lookup"><span data-stu-id="8a105-106">\<sources></span></span>  
<span data-ttu-id="8a105-107">\<源 ></span><span class="sxs-lookup"><span data-stu-id="8a105-107">\<source></span></span>  
<span data-ttu-id="8a105-108">\<侦听器 ></span><span class="sxs-lookup"><span data-stu-id="8a105-108">\<listeners></span></span>  
<span data-ttu-id="8a105-109">\<remove></span><span class="sxs-lookup"><span data-stu-id="8a105-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a105-110">语法</span><span class="sxs-lookup"><span data-stu-id="8a105-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a105-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8a105-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8a105-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8a105-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a105-113">特性</span><span class="sxs-lookup"><span data-stu-id="8a105-113">Attributes</span></span>  
  
|<span data-ttu-id="8a105-114">特性</span><span class="sxs-lookup"><span data-stu-id="8a105-114">Attribute</span></span>|<span data-ttu-id="8a105-115">描述</span><span class="sxs-lookup"><span data-stu-id="8a105-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="8a105-116">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="8a105-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="8a105-117">要从`Listeners`集合中删除的侦听器的名称。</span><span class="sxs-lookup"><span data-stu-id="8a105-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a105-118">子元素</span><span class="sxs-lookup"><span data-stu-id="8a105-118">Child Elements</span></span>  
 <span data-ttu-id="8a105-119">无。</span><span class="sxs-lookup"><span data-stu-id="8a105-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a105-120">父元素</span><span class="sxs-lookup"><span data-stu-id="8a105-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8a105-121">元素</span><span class="sxs-lookup"><span data-stu-id="8a105-121">Element</span></span>|<span data-ttu-id="8a105-122">描述</span><span class="sxs-lookup"><span data-stu-id="8a105-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8a105-123">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="8a105-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8a105-124">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="8a105-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="8a105-125">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="8a105-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="8a105-126">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="8a105-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="8a105-127">指定用于收集、存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="8a105-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a105-128">备注</span><span class="sxs-lookup"><span data-stu-id="8a105-128">Remarks</span></span>  
 <span data-ttu-id="8a105-129">元素从跟踪源的`Listeners`集合中删除指定的侦听器。 `<remove>`</span><span class="sxs-lookup"><span data-stu-id="8a105-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="8a105-130">您`Listeners`可以通过<xref:System.Diagnostics.TraceListenerCollection.Remove%2A> <xref:System.Diagnostics.TraceSource.Listeners%2A>对实例的属性调用方法,以编程方式从跟踪源的集合中移除一个元素。<xref:System.Diagnostics.TraceSource></span><span class="sxs-lookup"><span data-stu-id="8a105-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="8a105-131">此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="8a105-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a105-132">示例</span><span class="sxs-lookup"><span data-stu-id="8a105-132">Example</span></span>  
 <span data-ttu-id="8a105-133">下面的示例演示`<remove>`如何在`<add>`使用元素`Listeners`将侦听器`console`添加到跟踪源`TraceSourceApp`的集合之前使用元素。</span><span class="sxs-lookup"><span data-stu-id="8a105-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="8a105-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a105-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="8a105-135">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="8a105-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8a105-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="8a105-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="8a105-137">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="8a105-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
