---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dedb1dd389e2308ea8f70d71f057d17a45172517
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1008---workflowapplicationunloaded"></a>1008 - WorkflowApplicationUnloaded
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1008|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示工作流应用程序已卸载。  
  
## <a name="message"></a>消息  
 WorkflowInstance Id“%1”已卸载。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|工作流的实例 ID|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
