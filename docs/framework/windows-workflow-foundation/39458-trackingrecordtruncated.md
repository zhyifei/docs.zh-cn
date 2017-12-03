---
title: 39458 - TrackingRecordTruncated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d2bc07cff75fce7ddb50da9f54d161d7f235cab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="39458---trackingrecordtruncated"></a>39458 - TrackingRecordTruncated
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|39458|  
|关键字|WFTracking|  
|级别|警告|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示已截断跟踪记录。 已移除了变量/批注/用户数据。  
  
## <a name="message"></a>消息  
 用提供程序 %2 向 ETW 会话写入了截断的跟踪记录 %1。 已移除了变量/批注/用户数据  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|跟踪记录编号。|  
|ProviderId|xs:string|ETW 提供程序 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
