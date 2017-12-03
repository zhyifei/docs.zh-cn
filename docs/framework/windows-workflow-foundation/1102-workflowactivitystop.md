---
title: 1102 - WorkflowActivityStop
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 285e5cb8-e90d-4914-ac06-e9b176ffefa2
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e6f70af8df131767dd528774f9098f30e7223d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1102---workflowactivitystop"></a>1102 - WorkflowActivityStop
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1102|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示工作流活动已停止。  
  
## <a name="message"></a>消息  
 WorkflowInstance Id“%1”E2E 活动  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|工作流实例 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
