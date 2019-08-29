---
title: <clear><listeners>的元素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 9816ba0f8e4ddd4c38537eb4e014a4240ff20407
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927168"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<为\<跟踪 > 清除\<侦听器 > > 元素
清除跟踪的 `Listeners` 集合。  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
\<侦听器 >  
\<清除 >  
  
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
 元素从跟踪的集合中移除所有侦听器。 `Listeners` `<clear>` 可以在`<clear>` `<add>`使用元素之前使用元素, 以确定集合中没有其他活动的侦听器。  
  
 您可以通过对`Listeners` <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>属性(`System.Diagnostics.Trace.Listeners.Clear()`) 调用方法, 以编程方式清除该集合。  
  
 此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。  
  
> [!NOTE]
> <xref:System.Diagnostics.DefaultTraceListener> <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>元素从`Listeners`集合中移除, 并更改、 、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>和<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>方法的行为。 `<clear>` 通常调用`Fail`或方法会导致显示消息框。 `Assert` 但是, 如果<xref:System.Diagnostics.DefaultTraceListener>不`Listeners`在集合中, 则不会显示消息框。  
  
## <a name="example"></a>示例  
 下面的`<clear>`示例演示如何在`<add>`使用元素`Listeners`将侦听器`console`添加到用于 trace 的集合之前使用元素。  
  
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
