---
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: f70dc235e037b4f490a25866940fe2bccceae2a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460390"
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|224|  
|关键字|EndToEndMonitoring、HealthMonitoring、疑难解答、ServiceModel|  
|级别|警告|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 当超出某个主服务中止值时，将发出 `MessageThrottleExceeded` 事件。 当活动峰值变慢且当前中止值达到当前限制值的 70% 时，将发出此事件。 请注意，仅在活动变慢时才发出一次此事件。 如果当前值在 70% 标记的附近波动（例如，70,69,70,71,70,69），则只有第一次出现的 70% 会导致发出事件。 在发出此事件后，如果将来出现超出中止值的情况，则也会导致发出 `MessageThrottleExceeded` 事件。  
  
## <a name="message"></a>消息  
 “%2”的“%1”中止值为 70%%。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|中止值名称|`xs:string`|超过的中止值的名称。 `MaxConcurrentCalls`、`MaxConcurrentInstances` 或 `MaxConcurrentSessions`。|  
|限制值|`xs:long`|当前配置的中止值限制。|  
|HostReference|`xs:string`|对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。 其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。 示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
