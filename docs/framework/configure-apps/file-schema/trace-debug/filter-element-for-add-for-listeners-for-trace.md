---
title: <filter><add> 的<listeners>的的元素<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: afde5381a7dd7dfe6a1a9d238a2029511bd9bae2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927132"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a>\<筛选用于\<添加\<侦听器的 > > 元素 > \<跟踪 >
将筛选器添加到跟踪的`Listeners`集合中的侦听器。  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
\<侦听器 >  
\<add>  
\<filter>  
  
## <a name="syntax"></a>语法  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`type`|必需的特性。<br /><br /> 指定筛选器的类型, 该类型应继承自<xref:System.Diagnostics.TraceFilter>类。 你可以使用类型的命名空间限定名称, 该名称与类型的<xref:System.Type.FullName%2A>属性相对应, 或者你可以使用包含程序集信息 (与<xref:System.Type.AssemblyQualifiedName%2A>属性相对应) 的完全限定的类型名称。 有关完全限定类型名称的信息, 请参阅[指定完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)。|  
|`initializeData`|可选特性。<br /><br /> 传递给指定筛选器类的构造函数的字符串。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`trace`|包含用于收集、存储和路由跟踪消息的侦听器。|  
|`listeners`|包含收集、存储和路由消息的侦听器。 侦听器将跟踪输出定向到适当的目标。|  
|`add`|将侦听器添加到 `Listeners` 集合中。|  
  
## <a name="remarks"></a>备注  
 元素必须包含`<add>`在指定侦听器类型的跟踪侦听器的元素中, 而不只是在[ \<sharedListeners >](sharedlisteners-element.md)中定义的侦听器的名称。 `<filter>` 如果侦听器是在[ \<sharedListeners >](sharedlisteners-element.md)中定义的, 则必须在该元素中定义该侦听器的筛选器。  
  
 此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示`<filter>`如何使用元素将筛选器添加到跟踪的`Listeners`集合中`console`的侦听器, 并将筛选器事件级别指定为`Error`。  
  
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
  
## <a name="see-also"></a>请参阅

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [跟踪和调试设置架构](index.md)
