---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: 5979cd8ffe0e05b61af01d2aa98c4a2c63fd432c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461060"
---
# <a name="217---clientoperationprepared"></a>217 - ClientOperationPrepared
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|217|  
|关键字|疑难解答，ServiceModel|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 此事件恰好在将操作发送到服务之前由客户端发出。  
  
## <a name="message"></a>消息  
 客户端正在执行与协定“%2”相关联的操作“%1”。 消息将发送到“%3”。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|操作|`xs:string`|传出消息的 SOAP 操作标头。|  
|协定名称|`xs:string`|协定的名称。 示例：ICalculator。|  
|目标|`xs:string`|消息发送到的服务终结点的地址。|  
|HostReference|`xs:string`|对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。 其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。 示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
