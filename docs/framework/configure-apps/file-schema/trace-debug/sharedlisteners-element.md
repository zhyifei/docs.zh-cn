---
title: <sharedListeners> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153316"
---
# <a name="sharedlisteners-element"></a>\<共享侦听器>元素
包含任何源或跟踪元素可以引用的侦听器。  默认情况下，这些侦听器不会接收任何跟踪，并且无法在运行时检索这些侦听器。 标识为共享侦听器的侦听器可以按名称添加到源或跟踪中。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<共享侦听器>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<添加>](add-element-for-listeners-for-trace.md)|将侦听器添加到 `sharedListeners` 集合中。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`Configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|为 ASP.NET 配置节指定根元素。|  
  
## <a name="remarks"></a>备注  
 将侦听器添加到共享侦听器集合不会使其成为活动侦听器。 仍必须通过将其添加到该跟踪元素`Listeners`的集合并将其添加到跟踪源或跟踪中。 .NET 框架中的侦听器类派生自<xref:System.Diagnostics.TraceListener>类。  
  
 此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`<sharedListeners>`元素将侦听器`console`添加到 和`Listeners`<xref:System.Diagnostics.TraceSource><xref:System.Diagnostics.Trace>类的集合。 控制台跟踪侦听器通过调用<xref:System.Diagnostics.TraceSource>或<xref:System.Diagnostics.Trace>向 向 控制台写入跟踪信息。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.TraceListener>
- [跟踪和调试设置架构](index.md)
- [跟踪侦听器](../../../debug-trace-profile/trace-listeners.md)
