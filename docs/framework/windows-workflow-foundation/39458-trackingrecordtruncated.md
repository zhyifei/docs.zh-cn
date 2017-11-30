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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ecf18d6d751edd47dbeca7d2e5f4491892e41e6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
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
