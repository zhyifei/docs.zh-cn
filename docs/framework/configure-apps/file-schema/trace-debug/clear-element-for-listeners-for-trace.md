---
title: <trace> 的 @no__t <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 0361580724351f8f42d058d5e20354e3335bac2f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699371"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<clear > 元素，用于 2trace @no__t 的 \<listeners >
清除跟踪的 `Listeners` 集合。  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<trace >** ](trace-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<clear >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`trace`|包含用于收集、存储和路由跟踪消息的侦听器。|  
|`listeners`|包含收集、存储和路由消息的侦听器。 侦听器将跟踪输出定向到适当的目标。|  
  
## <a name="remarks"></a>备注  
 @No__t-0 元素从 trace 的 @no__t 集合中删除所有侦听器。 你可以使用 `<clear>` 元素，然后才能使用 @no__t 元素，以确定集合中没有其他活动的侦听器。  
  
 可以通过在 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> 属性（`System.Diagnostics.Trace.Listeners.Clear()`）上调用 <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 方法，以编程方式清除 `Listeners` 收集。  
  
 此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。  
  
> [!NOTE]
> @No__t-0 元素从 `Listeners` 集合中删除 <xref:System.Diagnostics.DefaultTraceListener>，改变 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>、@no__t、@no__t 和 @no__t 方法的行为。 调用 @no__t 0 或 @no__t 方法通常会导致显示消息框。 但是，如果 <xref:System.Diagnostics.DefaultTraceListener> 不在 @no__t 集合中，则不会显示消息框。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 `<clear>` 元素，然后再使用 @no__t，将侦听器 `console` 添加到 trace 的 @no__t 集合。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [跟踪和调试设置架构](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [跟踪侦听器](../../../debug-trace-profile/trace-listeners.md)
