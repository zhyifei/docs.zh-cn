---
title: <系统.诊断>元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153202"
---
# <a name="systemdiagnostics-element"></a>\<系统.诊断>元素
指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;**\<系统.诊断>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<断言>](assert-element.md)|指定调用 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 方法时是否显示消息框；另外指定要写入消息的文件的名称。|  
|[\<性能计数器>](performancecounters-element.md)|指定由性能计数器共享的全局内存的大小。|  
|[\<共享侦听器>](sharedlisteners-element.md)|包含任何源或跟踪元素可以引用的侦听器。 标识为共享侦听器的侦听器可以按名称添加到源或跟踪中。|  
|[\<来源>](sources-element.md)|指定启动跟踪消息的跟踪源。|  
|[\<开关>](switches-element.md)|包含跟踪开关和设置跟踪开关的级别。|  
|[\<跟踪>](trace-element.md)|包含用于收集、存储和路由跟踪消息的侦听器。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
  
## <a name="example"></a>示例  
 下面的示例演示如何在**\<系统**中嵌入跟踪开关和跟踪侦听器>。 跟踪`General`开关设置为级别<xref:System.Diagnostics.TraceLevel>。 跟踪侦听`myListener`器创建一个`MyListener.log`文件，并将输出写入该文件。  
  
> [!NOTE]
> 在 .NET Framework 2.0 版中，你可以使用文本指定开关值。 例如，`true`可以为 指定 或使用<xref:System.Diagnostics.BooleanSwitch>表示枚举值（如 的 枚`Error`<xref:System.Diagnostics.TraceSwitch>举值）的文本指定或使用 文本。 行 `<add name="myTraceSwitch" value="Error" />` 等于 `<add name="myTraceSwitch" value="1" />`。  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [跟踪和调试设置架构](index.md)
