---
title: <clear>用于<listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153537"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<清除>元素，\<用于>跟踪\<>的侦听器
清除跟踪的 `Listeners` 集合。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<明确>**

## <a name="syntax"></a>语法  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`trace`|包含用于收集、存储和路由跟踪消息的侦听器。|  
|`listeners`|包含收集、存储和路由消息的侦听器。 侦听器将跟踪输出定向到适当的目标。|  
  
## <a name="remarks"></a>备注  
 该`<clear>`元素从跟踪集合中删除`Listeners`所有侦听器。 在使用 元素`<clear>`之前，`<add>`可以使用 该元素来确定集合中没有其他活动侦听器。  
  
 您可以通过`Listeners`在<xref:System.Diagnostics.TraceListenerCollection.Clear%2A><xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>属性上调用 方法 （）`System.Diagnostics.Trace.Listeners.Clear()`以编程方式清除集合。  
  
 此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。  
  
> [!NOTE]
> 元素`<clear>`从<xref:System.Diagnostics.DefaultTraceListener>`Listeners`集合中删除 ， 更改<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>、 、<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>和<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>方法的行为。 调用`Assert`或`Fail`方法通常会导致显示消息框。 但是，如果 不在<xref:System.Diagnostics.DefaultTraceListener>`Listeners`集合中，则不会显示消息框。  
  
## <a name="example"></a>示例  
 下面的示例`<clear>`演示如何在使用`<add>`元素将侦听器`console`添加到跟踪`Listeners`集合之前使用元素。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [跟踪和调试设置架构](index.md)
- [\<删除>](remove-element-for-listeners-for-trace.md)
- [跟踪侦听器](../../../debug-trace-profile/trace-listeners.md)
