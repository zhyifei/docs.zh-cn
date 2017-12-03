---
title: 1125 - InvokeMethodIsNotStatic
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b31bb8db8252474d20f7523e08cadf35bfcc84a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1125---invokemethodisnotstatic"></a>1125 - InvokeMethodIsNotStatic
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1125|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 在 CacheMetadata 步骤中，InvokeMethod 活动指示要调用的方法是非静态的。  
  
## <a name="message"></a>消息  
 InvokeMethod“%1”- 方法非静态。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|InvokeMethod 活动的显示名称。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
