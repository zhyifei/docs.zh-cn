---
title: 404 - ResumeSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 395cc7ca-f35f-4295-be97-39a077f99c97
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c3386270bb0d98f9351275805563c2f127ed728
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="404---resumesignpostevent"></a>404 - ResumeSignpostEvent
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|404|  
|关键字|疑难解答|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 此事件标记端对端活动的恢复， 它包含活动的名称。  
  
## <a name="message"></a>消息  
 活动边界。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|扩展数据|`xs:string`|活动的名称。|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
