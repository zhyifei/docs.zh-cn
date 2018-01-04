---
title: 401- StopSignPostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 058cae31c70e2c415e27870af1a0064b84a70b12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="401--stopsignpostevent"></a>401- StopSignPostEvent
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|401|  
|关键字|疑难解答|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 此事件标记端对端活动的结束， 它包含活动的名称。  
  
## <a name="message"></a>消息  
 活动边界。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|扩展数据|`xs:string`|活动的名称。|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
