---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 61613a27c4d4d8fb0b206246fef25ae87def47a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923859"
---
# <a name="1150---compensationstate"></a>1150 - CompensationState
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1150|  
|关键字|WFActivities|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示状态在 CompensableActivity 中发生更改。  
  
## <a name="message"></a>消息  
 CompensableActivity“%1”的状态为“%2”。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|活动的显示名称。|  
|状态|xs:string|补偿状态。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
