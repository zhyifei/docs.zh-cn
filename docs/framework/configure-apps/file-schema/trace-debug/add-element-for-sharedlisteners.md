---
title: <sharedListeners> 的 <add> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153602"
---
# <a name="add-element-for-sharedlisteners"></a>\<添加 sharedListeners 的\<> 元素>
将侦听器添加到 `sharedListeners` 集合中。 `sharedListeners`是任何[ \<源>](source-element.md)或[ \<跟踪>](trace-element.md)都可以引用的侦听器的集合。  默认情况下，集合中`sharedListeners`的侦听器不会放置在`Listeners`集合中。 必须按名称将它们添加到[ \<源>](source-element.md)或[ \<跟踪>](trace-element.md)。 在运行时，不能在代码中获取`sharedListeners`集合中的侦听器。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<诊断>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**

## <a name="syntax"></a>语法  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`name`|必需的特性。<br /><br /> 指定用于将共享侦听器添加到`Listeners`集合中的侦听器的名称。|  
|`type`|必需的特性。<br /><br /> 指定侦听器的类型。 必须使用满足指定[完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)中指定的要求的字符串。|  
|`initializeData`|可选特性。<br /><br /> 传递到指定类的构造函数的字符串。|  
|`traceOutputOptions`|可选特性。<br/><br/>指示要写入跟踪输出的数据<xref:System.Diagnostics.TraceOptions>的一个或多个枚举成员的字符串表示形式。 多个项之间以逗号分隔。 默认值为 "None"。|

### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<筛选>](filter-element-for-add-for-sharedlisteners.md)|将筛选器添加到 `sharedListeners` 集合中的侦听器。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`sharedListeners`|任何源或跟踪元素都可以引用的侦听器的集合。|  
  
## <a name="remarks"></a>备注  
 随 .NET Framework 附带的侦听器类派生自<xref:System.Diagnostics.TraceListener>类。 `name`特性的值用于将共享侦听器添加到跟踪源或跟踪源`Listeners`的集合中。 该`initializeData`属性的值取决于所创建的侦听器的类型。 并非所有跟踪侦听器都要求您指定`initializeData`。  
  
> [!NOTE]
> 使用`initializeData`属性时，可能会收到编译器警告 "未声明 ' initializeData ' 特性"。 之所以出现此警告<xref:System.Diagnostics.TraceListener>，是因为配置设置是针对抽象基类验证的，后者不识别`initializeData`属性。 通常，对于具有采用参数的构造函数的跟踪侦听器实现，你可以忽略此警告。  
  
 下表显示了 .NET Framework 附带的跟踪侦听器，并描述了其`initializeData`属性的值。  
  
|跟踪侦听器类|initializeData 特性值|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>构造函数的`useErrorStream`值。  将`initializeData`属性设置为 "`true`" 可将跟踪和调试输出写入标准错误流;将其设置为`false`"" 即可写入标准输出流。|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<xref:System.Diagnostics.DelimitedListTraceListener> 写入的文件名。|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|现有的事件日志源的名称。|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.EventSchemaTraceListener>写入的文件的名称。|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.TextWriterTraceListener>写入的文件的名称。|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<xref:System.Diagnostics.XmlWriterTraceListener>写入的文件的名称。|  
  
## <a name="configuration-file"></a>配置文件  
 此元素可在计算机配置文件（Machine.config）和应用程序配置文件中使用。  
  
## <a name="example"></a>示例  
 下面的示例`<add>`演示如何使用元素将添加<xref:System.Diagnostics.TextWriterTraceListener> `textListener`到`sharedListeners`集合中。   `textListener`按名称添加到跟踪源`Listeners` `TraceSourceApp`的集合中。 `textListener`侦听器将跟踪输出写入文件 myListener。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [跟踪和调试设置架构](index.md)
- [跟踪侦听器](../../../debug-trace-profile/trace-listeners.md)
