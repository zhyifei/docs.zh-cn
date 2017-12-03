---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 803616fdd287491afa27d3ac23dfce99c5db08ca
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="57398---maxinstancesexceeded"></a>57398 - MaxInstancesExceeded
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|57398|  
|关键字|WFServices|  
|级别|警告|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 指示系统达到为限制“MaxConcurrentInstances”设置的限制值。  
  
## <a name="message"></a>消息  
 系统达到为限制“MaxConcurrentInstances”设置的限制值。 此限制的限制值设置为 %1。 可通过修改 serviceThrottle 元素中的特性“maxConcurrentInstances”或修改行为 ServiceThrottlingBehavior 的“MaxConcurrentInstances”属性来更改限制值。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|名称|xs:string|项的名称。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
