---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b321f8c20fbd79b5e748601ee06f975dc75a7d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 - WorkflowApplicationPersistableIdle
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1041|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示工作流应用程序空闲且可持久化。 工作流应用程序将是空闲且可持久化的。  
  
## <a name="message"></a>消息  
 WorkflowApplication Id ' %1' 是空闲且可持久化。  不会执行以下操作: %2。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|工作流应用程序 ID|  
|ActionTaken|xs:string|将对工作流应用程序执行的操作。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
