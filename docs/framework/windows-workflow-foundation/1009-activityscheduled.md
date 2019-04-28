---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924652"
---
# <a name="1009---activityscheduled"></a>1009 - ActivityScheduled
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1009|  
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
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
