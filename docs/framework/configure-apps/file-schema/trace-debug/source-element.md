---
title: '&lt;源&gt;元素'
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b7c2a71b129a0ad7d1c2a72b18b8a69a111f9495
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltsourcegt-element"></a>&lt;源&gt;元素
指定用于启动跟踪消息的跟踪源。  
  
 \<configuration>  
\<system.diagnostics >  
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
|`switchName`|可选特性。<br /><br /> 应用程序中指定的跟踪交换机实例的名称。 如果此开关不在中标识`<switches>`元素，值指定为交换机级别。|  
|`switchType`|可选特性。<br /><br /> 指定的一种跟踪开关。 如果存在，类型必须是有效的类名称，并且不能为空字符串。|  
|`extraAttribute`|可选特性。<br /><br /> 指定由跟踪源特定属性的值<xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>为该跟踪源的方法。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|包含收集、 存储和将消息路由的侦听器。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`sources`|包含用于启动跟踪消息的跟踪源。|  
  
## <a name="remarks"></a>备注  
 计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`<source>`要添加的跟踪源元素`mySource`和设置源开关的级别命名`sourceSwitch`。 将控制台跟踪侦听器添加跟踪信息写入控制台。  
  
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
 [跟踪和调试设置架构](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [跟踪开关](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
