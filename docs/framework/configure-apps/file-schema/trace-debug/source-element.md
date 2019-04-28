---
title: <source> 元素
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 8860f5d3ed7ee0c04d1e8afd7614f3f73b470808
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673701"
---
# <a name="source-element"></a><span data-ttu-id="3deb2-102">\<源 > 元素</span><span class="sxs-lookup"><span data-stu-id="3deb2-102">\<source> Element</span></span>
<span data-ttu-id="3deb2-103">指定用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="3deb2-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="3deb2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3deb2-104">\<configuration></span></span>  
<span data-ttu-id="3deb2-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="3deb2-105">\<system.diagnostics></span></span>  
<span data-ttu-id="3deb2-106">\<sources></span><span class="sxs-lookup"><span data-stu-id="3deb2-106">\<sources></span></span>  
<span data-ttu-id="3deb2-107">\<source></span><span class="sxs-lookup"><span data-stu-id="3deb2-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3deb2-108">语法</span><span class="sxs-lookup"><span data-stu-id="3deb2-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3deb2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3deb2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3deb2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3deb2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3deb2-111">特性</span><span class="sxs-lookup"><span data-stu-id="3deb2-111">Attributes</span></span>  
  
|<span data-ttu-id="3deb2-112">特性</span><span class="sxs-lookup"><span data-stu-id="3deb2-112">Attribute</span></span>|<span data-ttu-id="3deb2-113">描述</span><span class="sxs-lookup"><span data-stu-id="3deb2-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="3deb2-114">可选特性。</span><span class="sxs-lookup"><span data-stu-id="3deb2-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3deb2-115">指定跟踪源的名称。</span><span class="sxs-lookup"><span data-stu-id="3deb2-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="3deb2-116">可选特性。</span><span class="sxs-lookup"><span data-stu-id="3deb2-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3deb2-117">在应用程序中指定跟踪开关实例的名称。</span><span class="sxs-lookup"><span data-stu-id="3deb2-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="3deb2-118">如果此开关不标识中`<switches>`元素，该值指定开关的级别。</span><span class="sxs-lookup"><span data-stu-id="3deb2-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="3deb2-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="3deb2-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3deb2-120">指定跟踪开关的类型。</span><span class="sxs-lookup"><span data-stu-id="3deb2-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="3deb2-121">如果有，该类型必须是有效的类名称，并不能为空字符串。</span><span class="sxs-lookup"><span data-stu-id="3deb2-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="3deb2-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="3deb2-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3deb2-123">指定由标识跟踪特定于源的属性的值为<xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>方法为该跟踪源。</span><span class="sxs-lookup"><span data-stu-id="3deb2-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3deb2-124">子元素</span><span class="sxs-lookup"><span data-stu-id="3deb2-124">Child Elements</span></span>  
  
|<span data-ttu-id="3deb2-125">元素</span><span class="sxs-lookup"><span data-stu-id="3deb2-125">Element</span></span>|<span data-ttu-id="3deb2-126">描述</span><span class="sxs-lookup"><span data-stu-id="3deb2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3deb2-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="3deb2-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="3deb2-128">包含用于收集、 存储和路由消息的侦听器。</span><span class="sxs-lookup"><span data-stu-id="3deb2-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3deb2-129">父元素</span><span class="sxs-lookup"><span data-stu-id="3deb2-129">Parent Elements</span></span>  
  
|<span data-ttu-id="3deb2-130">元素</span><span class="sxs-lookup"><span data-stu-id="3deb2-130">Element</span></span>|<span data-ttu-id="3deb2-131">描述</span><span class="sxs-lookup"><span data-stu-id="3deb2-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3deb2-132">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3deb2-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3deb2-133">指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。</span><span class="sxs-lookup"><span data-stu-id="3deb2-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="3deb2-134">包含用于启动跟踪消息的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="3deb2-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3deb2-135">备注</span><span class="sxs-lookup"><span data-stu-id="3deb2-135">Remarks</span></span>  
 <span data-ttu-id="3deb2-136">计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="3deb2-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3deb2-137">示例</span><span class="sxs-lookup"><span data-stu-id="3deb2-137">Example</span></span>  
 <span data-ttu-id="3deb2-138">下面的示例演示如何使用`<source>`要添加的跟踪源元素`mySource`，并设置源开关的级别命名为`sourceSwitch`。</span><span class="sxs-lookup"><span data-stu-id="3deb2-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="3deb2-139">控制台跟踪侦听器添加的跟踪信息写入控制台。</span><span class="sxs-lookup"><span data-stu-id="3deb2-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3deb2-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="3deb2-140">See also</span></span>

- [<span data-ttu-id="3deb2-141">跟踪和调试设置架构</span><span class="sxs-lookup"><span data-stu-id="3deb2-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="3deb2-142">跟踪开关</span><span class="sxs-lookup"><span data-stu-id="3deb2-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
