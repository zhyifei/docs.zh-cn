---
title: <source> 的 <listeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153407"
---
# <a name="listeners-element-for-source"></a>\<源>的侦\<听器>元素
添加或删除 集合中的<xref:System.Diagnostics.TraceSource.Listeners%2A>侦听器。 <xref:System.Diagnostics.TraceSource> 侦听器将跟踪输出定向到适当的目标，如日志、窗口或文本文件。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<源>**](source-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<听众>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<添加>](add-element-for-listeners-for-source.md)|将侦听器添加到 `Listeners` 集合中。|  
|[\<删除>](remove-element-for-listeners-for-source.md)|从`Listeners`集合中删除侦听器。|  
|[\<明确>](clear-element-for-listeners-for-source.md)|清除跟踪源的 `Listeners` 集合。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`sources`|包含用于启动跟踪消息的跟踪源。|  
|`source`|指定用于启动跟踪消息的跟踪源。|  
  
## <a name="remarks"></a>备注  
  
## <a name="configuration-file"></a>配置文件  
 此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 元素`<listeners>`向`mySource`源添加控制台跟踪侦听器并删除默认跟踪侦听器。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.TraceListener>
- [跟踪和调试设置架构](index.md)
- [跟踪侦听器](../../../debug-trace-profile/trace-listeners.md)
