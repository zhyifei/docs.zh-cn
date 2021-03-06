---
title: <filter>用于<add><listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0cb668782de263d5f784691f46cb8b74541d942b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153511"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a>\<筛选器>元素，\<用于为\<\<源>>的侦听器添加>
将筛选器添加到跟踪源的 `Listeners` 集合中的侦听器。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<源>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<过滤器>**

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
|`sources`|包含用于启动跟踪消息的跟踪源。|  
|`source`|指定用于启动跟踪消息的跟踪源。|  
|`listeners`|包含收集、存储和路由消息的侦听器。 侦听器将跟踪输出定向到适当的目标。|  
|`add`|将侦听器添加到跟踪源的 `Listeners` 集合中。|  
  
## <a name="remarks"></a>备注  
 元素`<filter>`必须包含在指定侦听器`<add>`类型的跟踪源侦听器的元素中，而不仅仅是[\<在共享侦听器>](sharedlisteners-element.md)中定义的侦听器的名称。 如果在[\<共享侦听器>](sharedlisteners-element.md)中定义侦听器，则必须在该元素中定义该侦听器的筛选器。  
  
 此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。  
  
## <a name="example"></a>示例  
 下面的示例演示如何`<filter>`使用 元素向跟踪源`console``Listeners``myTraceSource`集合中的侦听器添加筛选器，将筛选器事件级别指定为`Error`。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [跟踪和调试设置架构](index.md)
