---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 42d22a7187adc712c0f236111cecac89dd59e2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1005---workflowapplicationidled"></a>1005 - WorkflowApplicationIdled
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1005|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示工作流应用程序已处于空闲状态。  
  
## <a name="message"></a>消息  
 WorkflowApplication ID“%1”变为空闲状态。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|工作流应用程序 ID|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
