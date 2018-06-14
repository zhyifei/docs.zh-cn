---
title: 1007 - WorkflowApplicationPersisted
ms.date: 03/30/2017
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
ms.openlocfilehash: 0b3c290ad06eda6921626c0d7a1c8ec854c30e7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509712"
---
# <a name="1007---workflowapplicationpersisted"></a>1007 - WorkflowApplicationPersisted
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1007|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示工作流应用程序已持久化。  
  
## <a name="message"></a>消息  
 WorkflowApplication ID“%1”已持久化。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|工作流应用程序 ID|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
