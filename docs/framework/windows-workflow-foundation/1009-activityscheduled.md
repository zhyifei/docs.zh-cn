---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d9463fbf2e7f2ac3424488dc3fca322a91d11126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1009---activityscheduled"></a>1009 - ActivityScheduled
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1009|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示正在安排某一活动的执行。  
  
## <a name="message"></a>消息  
 父 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了子 Activity“%4”、DisplayName“%5”、InstanceId“%6”。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|父活动的类型名称。|  
|ParentDisplayName|xs:string|父活动的显示名称。|  
|ParentInstanceId|xs:string|父活动的实例 ID。|  
|ChildActivity|xs:string|所安排子活动的类型名称。|  
|ChildDisplayName|xs:string|所安排子活动的显示名称。|  
|ChildInstanceId|xs:string|所安排子活动的实例 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
