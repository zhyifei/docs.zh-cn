---
title: <source> 元素
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153290"
---
# <a name="source-element"></a>\<源>元素
指定用于启动跟踪消息的跟踪源。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<源>**

## <a name="syntax"></a>语法  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`name`|可选特性。<br /><br /> 指定跟踪源的名称。|  
|`switchName`|可选特性。<br /><br /> 指定应用程序中跟踪开关实例的名称。 如果在`<switches>`元素中未标识交换机，则值指定交换机的级别。|  
|`switchType`|可选特性。<br /><br /> 指定跟踪开关的类型。 如果存在，则类型必须是有效的类名称，不能为空字符串。|  
|`extraAttribute`|可选特性。<br /><br /> 指定由该跟踪源的方法标识的<xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>特定于跟踪源的属性的值。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<听众>](listeners-element-for-source.md)|包含收集、存储和路由消息的侦听器。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`sources`|包含用于启动跟踪消息的跟踪源。|  
  
## <a name="remarks"></a>备注  
 此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 元素`<source>`添加跟踪源`mySource`，并为名为 的`sourceSwitch`源交换机设置级别。 添加了将跟踪信息写入控制台的控制台跟踪侦听器。  
  
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
  
## <a name="see-also"></a>另请参阅

- [跟踪和调试设置架构](index.md)
- [跟踪开关](../../../debug-trace-profile/trace-switches.md)
