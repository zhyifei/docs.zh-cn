---
title: <trace> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153161"
---
# <a name="trace-element"></a>\<跟踪>元素
包含用于收集、存储和路由跟踪消息的侦听器。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<跟踪>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`autoflush`|可选特性。<br /><br /> 指定跟踪侦听器在每个写入操作后是否自动刷新输出缓冲区。|  
|`indentsize`|可选特性。<br /><br /> 指定缩进空格数。|  
|`useGlobalLock`|可选特性。<br /><br /> 指示是否应使用全局锁。|  
  
## <a name="autoflush-attribute"></a>自动刷新属性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|不会自动刷新输出缓冲区。 这是默认值。|  
|`true`|自动刷新输出缓冲区。|  
  
## <a name="usegloballock-attribute"></a>使用全局锁定属性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|如果侦听器是线程安全的，则不使用全局锁;否则，使用全局锁。|  
|`true`|无论侦听器是否安全，都使用全局锁。 这是默认值。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<听众>](listeners-element-for-trace.md)|指定收集、存储和路由消息的侦听器。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 元素`<trace>`将侦听器`MyListener`添加到`Listeners`集合中。 `MyListener`创建命名`MyListener.log`的文件并将输出写入该文件。 属性`useGlobalLock`设置为`false`，这将导致在跟踪侦听器是线程安全的时不使用全局锁。 属性`autoflush`设置为`true`，这将导致跟踪侦听器写入文件，而不考虑是否调用<xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType>该方法。 属性`indentsize`设置为 0（零），这将导致调用<xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType>方法时侦听器缩进零空格。  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [跟踪和调试设置架构](index.md)
