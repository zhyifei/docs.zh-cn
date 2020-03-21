---
title: <remove>用于<listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153330"
---
# <a name="remove-element-for-listeners-for-source"></a>\<删除>源\<>的侦听\<器>元素
从跟踪源的 `Listeners` 集合中删除侦听器。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.诊断>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<来源>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<源>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<听众>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<删除>**

## <a name="syntax"></a>语法  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`name`|必需的特性。<br /><br /> 要从`Listeners`集合中删除的侦听器的名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
|`sources`|包含用于启动跟踪消息的跟踪源。|  
|`source`|指定用于启动跟踪消息的跟踪源。|  
|`listeners`|指定收集、存储和路由消息的侦听器。|  
  
## <a name="remarks"></a>备注  
 该`<remove>`元素从跟踪源的集合中删除`Listeners`指定的侦听器。  
  
 `Listeners`您可以通过调用<xref:System.Diagnostics.TraceListenerCollection.Remove%2A><xref:System.Diagnostics.TraceSource>实例<xref:System.Diagnostics.TraceSource.Listeners%2A>属性上的方法，以编程方式从跟踪源的集合中删除元素。  
  
 此元素可用于计算机配置文件 （Machine.config） 和应用程序配置文件。  
  
## <a name="example"></a>示例  
 下面的`<remove>`示例演示如何在使用`<add>`元素将侦听器`console`添加到跟踪源`Listeners``TraceSourceApp`的集合之前使用 元素。  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [跟踪和调试设置架构](index.md)
- [\<明确>](clear-element-for-listeners-for-source.md)
- [跟踪侦听器](../../../debug-trace-profile/trace-listeners.md)
