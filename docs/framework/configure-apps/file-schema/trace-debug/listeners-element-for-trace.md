---
title: '&lt;侦听器&gt;元素&lt;跟踪&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2f0d795d6a8789772ff3fd46648fbc0d683c66e5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748134"
---
# <a name="ltlistenersgt-element-for-lttracegt"></a>&lt;侦听器&gt;元素&lt;跟踪&gt;
指定收集，侦听器存储区，并将消息路由。 侦听器将跟踪输出定向到适当的目标。  
  
 \<配置 > 元素  
\<system.diagnostics > 元素  
\<跟踪 > 元素  
\<侦听器 > 元素\<跟踪 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|将侦听器添加到 `Listeners` 集合中。|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|清除跟踪的 `Listeners` 集合。|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|删除从侦听器`Listeners`集合。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|为 ASP.NET 配置节指定根元素。|  
|`trace`|包含用于收集、存储和路由跟踪消息的侦听器。|  
  
## <a name="remarks"></a>备注  
 <xref:System.Diagnostics.Debug>和<xref:System.Diagnostics.Trace>类共用同一个**侦听器**集合。 如果你将侦听器对象添加到这些类之一中的集合，其他类将使用相同的侦听器。 随.NET Framework 提供的侦听器类派生自<xref:System.Diagnostics.TraceListener>类。  
  
## <a name="configuration-file"></a>配置文件  
 计算机配置文件 (Machine.config) 和应用程序配置文件中，可以使用此元素。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用**\<侦听器 >** 元素将侦听器`MyListener`和`MyEventListener`到**侦听器**集合。 `MyListener` 创建名为的文件`MyListener.log`并将输出写入文件。 `MyEventListener` 事件日志中创建的项。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Diagnostics.TraceListener>  
 [跟踪和调试设置架构](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
