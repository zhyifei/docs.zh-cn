---
title: '&lt;开关&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f046e1142209b519ecf71e67a11592f9aa578f84
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666704"
---
# <a name="ltswitchesgt-element"></a>&lt;开关&gt;元素
包含跟踪开关和对该跟踪开关设置的级别。  
  
 \<configuration>  
\<system.diagnostics>  
\<switches>  
  
## <a name="syntax"></a>语法  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|指定对跟踪开关设置的级别。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`System.diagnostics`|指定用于收集、存储和路由消息的跟踪侦听器以及对跟踪开关设置的级别。|  
  
## <a name="remarks"></a>备注  
 可以通过将它放在配置文件更改跟踪开关的级别。 如果该切换<xref:System.Diagnostics.BooleanSwitch>，您可以将其打开和关闭。 如果该切换<xref:System.Diagnostics.TraceSwitch>，可以将不同级别分配给该代码以指定类型的跟踪或调试消息的应用程序输出。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用**\<切换 >** 元素中设置`General`跟踪切换到<xref:System.Diagnostics.TraceLevel>级别，并启用`Data`布尔型跟踪开关。  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅
- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [跟踪和调试设置架构](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
