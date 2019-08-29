---
title: <filter><add>的元素<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 571a3add232f3e4f9747040dc104b85e8cc3085e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920514"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<筛选 sharedListeners 的\< \<add > > 元素 >
将筛选器添加到 `sharedListeners` 集合中的侦听器。  
  
 \<configuration>  
\<system.diagnostics>  
\<sharedListeners > 元素  
\<add>  
\<filter>  
  
## <a name="syntax"></a>语法  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**type**|必需的特性。<br /><br /> 指定筛选器的类型。 您只能使用该类型的完整名称 (采用<xref:System.Type.FullName%2A?displayProperty=nameWithType>属性格式), 也可以使用包含程序集信息 (采用<xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>属性格式) 的完全限定的类型名称。 有关创建完全限定类型名称的信息, 请参阅[指定完全限定的类型](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)名称。|  
|**initializeData**|可选特性。<br /><br /> 传递到指定类的构造函数的字符串。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`sharedListeners`|任何源或跟踪元素都可以引用的侦听器的集合。|  
|`add`|将侦听器添加到**sharedListeners**集合。|  
  
## <a name="remarks"></a>备注  
 `<add>`如果侦听器是在`<sharedListeners>`元素的元素中定义的, 则`<filter>`应在作为`<add>`元素的子元素的元素中定义该侦听器的筛选器。  
  
 此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`<filter>`元素将筛选器添加到`sharedListeners`集合中的跟踪侦听器`console` 。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [跟踪和调试设置架构](index.md)
