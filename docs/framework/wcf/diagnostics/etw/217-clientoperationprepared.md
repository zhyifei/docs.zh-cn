---
title: 217 - ClientOperationPrepared
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3e1b4e3aab6a6a7f94bfb3783c9e32f83557db19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
|HostReference|`xs:string`|对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。 其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。 示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
