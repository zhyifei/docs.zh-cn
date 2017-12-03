---
title: 1033 - StartRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cc905fbd960b3ed5c36cac40300ba58697f8903
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1033---startruntimeworkitem"></a>1033 - StartRuntimeWorkItem
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|2052|  
|关键字|WFRuntime|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 RuntimeWorkItem 正在开始执行。  
  
## <a name="message"></a>消息  
 开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行运行时工作项。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|Activity|xs:string|活动的类型名称。|  
|DisplayName|xs:string|活动的显示名称。|  
|InstanceId|xs:string|活动的实例 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
