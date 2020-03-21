---
title: <filter>用于<add><listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153461"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>\<筛选器>元素，\<用于添加\<>跟踪>的\<侦听器>
将筛选器添加到跟踪集合中的`Listeners`侦听器。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<过滤器>**

## <a name="syntax"></a>语法  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`type`|必需的特性。<br /><br /> 指定筛选器的类型，该筛选器应从<xref:System.Diagnostics.TraceFilter>类继承。 可以使用类型的名称空间限定名称（对应于类型的属性<xref:System.Type.FullName%2A>），也可以使用完全限定的类型名称（包括对应于该属性的<xref:System.Type.AssemblyQualifiedName%2A>程序集信息）。 有关完全限定类型名称的信息，请参阅[指定完全限定类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)。|  
|`initializeData`|可选特性。<br /><br /> 字符串传递给指定筛选器类的构造函数。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`trace`|包含用于收集、存储和路由跟踪消息的侦听器。|  
|`listeners`|包含收集、存储和路由消息的侦听器。 侦听器将跟踪输出定向到适当的目标。|  
|`add`|将侦听器添加到 `Listeners` 集合中。|  
  
## <a name="remarks"></a>备注  
 元素`<filter>`必须包含在指定侦听器`<add>`类型的跟踪侦听器的元素中，而不仅仅是[\<在共享侦听器>](sharedlisteners-element.md)中定义的侦听器的名称。 如果在[\<共享侦听器>](sharedlisteners-element.md)中定义侦听器，则必须在该元素中定义该侦听器的筛选器。  
  
 此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`<filter>`元素向跟踪集合中的`console``Listeners`侦听器添加筛选器，将筛选器事件级别指定为`Error`。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [跟踪和调试设置架构](index.md)
