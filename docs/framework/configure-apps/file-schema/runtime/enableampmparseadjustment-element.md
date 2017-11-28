---
title: "&lt;EnableAmPmParseAdjustment&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 44bd6297142b6f29d93e9a3bebdb89d32d4bf46a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltenableampmparseadjustmentgt-element"></a>&lt;EnableAmPmParseAdjustment&gt;元素
确定是否日期和事件分析方法使用调整后的一组规则来分析包含日、 月、 小时和 AM/PM 指示符的日期字符串。  
  
 \<configuration>  
 \<运行时 >  
\<EnableAmPmParseAdjustment >  
  
## <a name="syntax"></a>语法  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定是否日期和事件分析方法使用调整后的一组规则来分析包含仅日、 月、 小时和 AM/PM 指示符的日期字符串。|  
  
### <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|0|日期和事件分析方法不使用调整后的规则用于分析包含仅日、 月、 小时和 AM/PM 指示符的日期字符串。|  
|1|日期和事件分析方法使用调整后的规则来分析包含仅日、 月、 小时和 AM/PM 指示符的日期字符串。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 `<EnableAmPmParseAdjustment>`元素控制以下方法如何分析日期字符串包含的一天和月后跟一个小时的时间和 AM/PM 指示符 （如"4/10 6 AM"):  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 没有其他模式会受到影响。  
  
 `<EnableAmPmParseAdjustment>`元素没有任何影响<xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>， <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>， <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>，和<xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType>方法。  
  
> [!IMPORTANT]
>  在.NET 核心和.NET Native，默认情况下启用的调整后的 AM/PM 分析规则。  
  
 如果未启用分析的调整规则，该字符串的第一个数字解释为 12 小时时钟小时和除外 AM/PM 指示符的字符串的其余部分将被忽略。 日期和时间分析方法返回包含当前日期和从日期字符串中提取一天中的小时。  
  
 如果启用了分析的调整规则，分析方法解释的日期和月份为属于当前年份，并解释为 12 小时制的小时的时间。  
  
 下表说明了中的差异<xref:System.DateTime>值时<xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType>方法用于分析字符串""4/10 6 AM"与`<EnableAmPmParseAdjustment>`元素的`enabled`属性设置为"0"或"1"。 它假定今天的日期是 2017 年 1 月 5 日，并显示的日期，就像它使用指定的区域性"G"格式字符串格式设置。  
  
|区域性名称|启用 ="0"|启用 ="1"|  
|------------------|------------------|------------------|  
|en-US|2017 年 1/5/4:00:00 AM|4/10/2017年 6:00:00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>另请参阅  
 [\<运行时 > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [\<configuration> 元素](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
