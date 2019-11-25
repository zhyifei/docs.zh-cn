---
title: <source> 的 <listeners> 的 <remove> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 75db45d4e868ce88e030ec6a43c8bdaf788a1102
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088852"
---
# <a name="remove-element-for-listeners-for-source"></a>\<删除 \<源的 \<侦听器 > > 元素 >
从跟踪源的 `Listeners` 集合中删除侦听器。  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<的 >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](sources-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;[ **&nbsp;&nbsp;\<** ](source-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**侦听器 >** ](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**

## <a name="syntax"></a>语法  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`name`|必需的特性。<br /><br /> 要从 `Listeners` 集合中删除的侦听器的名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`sources`|包含用于启动跟踪消息的跟踪源。|  
|`source`|指定用于启动跟踪消息的跟踪源。|  
|`listeners`|指定用于收集、存储和路由消息的侦听器。|  
  
## <a name="remarks"></a>备注  
 `<remove>` 元素从跟踪源的 `Listeners` 集合中删除指定的侦听器。  
  
 您可以通过对 <xref:System.Diagnostics.TraceSource> 实例的 <xref:System.Diagnostics.TraceSource.Listeners%2A> 属性调用 <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> 方法，以编程方式从跟踪源的 `Listeners` 集合中删除元素。  
  
 此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 `<remove>` 元素，然后再使用 `<add>` 元素将侦听器 `console` 添加到跟踪源 `TraceSourceApp`的 `Listeners` 集合。  
  
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
  
## <a name="see-also"></a>请参阅

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [跟踪和调试设置架构](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [跟踪侦听器](../../../debug-trace-profile/trace-listeners.md)
