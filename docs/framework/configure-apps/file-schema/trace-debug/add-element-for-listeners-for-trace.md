---
title: '&lt;添加&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e27187c05b49b7f73ef19243a3286e8c1de71579
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;添加&gt;元素&lt;侦听器&gt;为&lt;跟踪&gt;
将侦听器添加到**侦听器**集合。  
  
 \<configuration>  
\<system.diagnostics >  
\<跟踪 >  
\<侦听器 >  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**type**|必需的特性。<br /><br /> 指定侦听器的类型。 你必须使用满足要求中指定的字符串[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。|  
|**initializeData**|可选特性。<br /><br /> 传递给构造函数指定类的字符串。|  
|**name**|可选特性。<br /><br /> 指定侦听器的名称。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|将筛选器添加到中的侦听器`Listeners`跟踪的集合。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`listeners`|指定收集，侦听器存储区，并将消息路由。 侦听器将跟踪输出定向到适当的目标。|  
|`system.diagnostics`|为 ASP.NET 配置节指定根元素。|  
|`trace`|包含用于收集、存储和路由跟踪消息的侦听器。|  
  
## <a name="remarks"></a>备注  
 <xref:System.Diagnostics.Debug>和<xref:System.Diagnostics.Trace>类共用同一个**侦听器**集合。 如果你将侦听器对象添加到这些类之一中的集合，其他类将使用相同的侦听器。 侦听器类派生自<xref:System.Diagnostics.TraceListener>。  
  
 如果不指定`name`特性，则跟踪侦听器，<xref:System.Diagnostics.TraceListener.Name%2A>的跟踪侦听器默认值为空字符串 ("")。 如果你的应用程序具有一个侦听器，可以将其添加而无需指定一个名称，并将其删除通过指定名称为空字符串。 但是，如果你的应用程序具有多个侦听器，则应指定为每个跟踪侦听器，这样就可以识别和管理各个跟踪侦听器中的唯一名称<xref:System.Diagnostics.Debug.Listeners%2A>和<xref:System.Diagnostics.Trace.Listeners%2A>集合。  
  
> [!NOTE]
>  添加多个跟踪侦听器的相同类型条件且具有相同名称只有一个跟踪侦听器中的该类型的结果和名称添加到`Listeners`集合。 但是，你可以以编程方式添加到多个完全相同的侦听器`Listeners`集合。  
  
 值**initializeData**属性取决于你创建的侦听器的类型。 并非所有的跟踪侦听器需要你指定**initializeData**。  
  
> [!NOTE]
>  当你使用`initializeData`属性中，你可能会收到编译器警告"未声明 initializeData 特性。" 因为配置设置验证针对的抽象基类，会出现此警告<xref:System.Diagnostics.TraceListener>，这不能识别`initializeData`属性。 通常情况下，你可以忽略此警告的具有构造函数采用参数的跟踪侦听器实现。  
  
 下表显示.NET Framework 附带的跟踪侦听器，并描述的值的其**initializeData**属性。  
  
|跟踪侦听器类|initializeData 特性值|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream`值<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>构造函数。  设置`initializeData`属性设为"`true`"编写跟踪和调试输出到<xref:System.Console.Error%2A?displayProperty=nameWithType>;"`false`"写入<xref:System.Console.Out%2A?displayProperty=nameWithType>。|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|文件的名称<xref:System.Diagnostics.DelimitedListTraceListener>写入。|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|现有的事件日志源的名称的名称。|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|文件的名称，<xref:System.Diagnostics.EventSchemaTraceListener>写入。|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|文件的名称，<xref:System.Diagnostics.TextWriterTraceListener>写入。|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|文件的名称，<xref:System.Diagnostics.XmlWriterTraceListener>写入。|  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用**\<添加 >** 元素将侦听器`MyListener`和`MyEventListener`到**侦听器**集合。 `MyListener` 创建名为的文件`MyListener.log`并将输出写入文件。 `MyEventListener` 事件日志中创建的项。  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [跟踪和调试设置架构](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [跟踪侦听器](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
