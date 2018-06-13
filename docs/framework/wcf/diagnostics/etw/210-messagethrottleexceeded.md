---
title: 210 - MessageThrottleExceeded
ms.date: 03/30/2017
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
ms.openlocfilehash: 7ba5948b36642085ef44661b3d580e7f1c4102cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460296"
---
# <a name="210---messagethrottleexceeded"></a>210 - MessageThrottleExceeded
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|210|  
|关键字|EndToEndMonitoring、HealthMonitoring、疑难解答、ServiceModel|  
|级别|警告|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 在超过三个主服务控制器中止值之一时，将发出此事件。 请注意，仅在首次超过中止值时才发出此事件。 例如，如果并发调用的中止值为 10，则第 11 个并发调用将导致 `MessageThrottleExceeded` 事件。 第 12 个调用不会再次导致事件。 此外，为避免噪声事件流，在中止值附近波动的活动不会导致其他事件。 在本示例中，如果有 2 个调用完成，则还存在 9 个并发调用。 如果随后再发出了 2 个调用，则当前值再次达到 11。 不过，这不会再次引发事件。 当前值下降到中止值的 70% 时，将发出一个不同的事件以指示活动已减少。 以后超出中止值的活动将导致发出另一个 `MessageThrottleExceeded` 事件。 在本示例中，如果并发调用数下降到 7，然后再次达到 11，则发出另一个 `MessageThrottleExceeded` 事件。  
  
## <a name="message"></a>消息  
 达到了“%2”的中止值“%1”。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|中止值名称|`xs:string`|超过的中止值的名称。 `MaxConcurrentCalls`、`MaxConcurrentInstances` 或 `MaxConcurrentSessions`。|  
|限制值|`xs:long`|当前配置的中止值限制。|  
|HostReference|`xs:string`|对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。 其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。 示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
