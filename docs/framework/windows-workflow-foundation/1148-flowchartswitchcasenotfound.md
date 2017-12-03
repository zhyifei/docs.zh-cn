---
title: 1148 - FlowchartSwitchCaseNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fa173290b528be690b418622baaa2a12e4930cb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1148---flowchartswitchcasenotfound"></a>1148 - FlowchartSwitchCaseNotFound
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1148|  
|关键字|WFActivities|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示在 Flowchart 开关中找不到匹配大小写，也找不到默认大小写。 Flowchart 执行将结束。  
  
## <a name="message"></a>消息  
 Flowchart“%1”/FlowSwitch - 找不到 Case 活动，也找不到与 Expression 结果匹配的 Default Case。 Flowchart 执行将结束。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|FlowChart|xs:string|FlowChart 的显示名称。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
