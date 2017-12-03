---
title: 1007 - WorkflowApplicationPersisted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cae6ba6f3d86fa0a7c123a82ee61b9d01cf352c5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
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
