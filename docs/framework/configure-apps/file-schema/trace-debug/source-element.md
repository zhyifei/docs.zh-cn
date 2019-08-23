---
title: <source> 元素
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 55120e292ac2a2c822c5510563d1aa167ca921e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920456"
---
# <a name="source-element"></a>\<源 > 元素
指定用于启动跟踪消息的跟踪源。  
  
 \<configuration>  
\<system.diagnostics>  
\<源 >  
\<源 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`name`|可选特性。<br /><br /> 指定跟踪源的名称。|  
|`switchName`|可选特性。<br /><br /> 指定应用程序中的跟踪开关实例的名称。 如果未在`<switches>`元素中标识开关, 则值指定开关的级别。|  
|`switchType`|可选特性。<br /><br /> 指定跟踪开关的类型。 如果存在, 则该类型必须是有效的类名, 并且不能是空字符串。|  
|`extraAttribute`|可选特性。<br /><br /> 指定跟踪源特定属性的值, 该属性由<xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>该跟踪源的方法标识。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|包含收集、存储和路由消息的侦听器。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`sources`|包含用于启动跟踪消息的跟踪源。|  
  
## <a name="remarks"></a>备注  
 此元素可在计算机配置文件 (Machine.config) 和应用程序配置文件中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`<source>`元素添加跟踪源`mySource` , 并设置名`sourceSwitch`为的源开关的级别。 添加了控制台跟踪侦听器, 用于将跟踪信息写入控制台。  
  
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
  
## <a name="see-also"></a>请参阅

- [跟踪和调试设置架构](index.md)
- [跟踪开关](../../../debug-trace-profile/trace-switches.md)
