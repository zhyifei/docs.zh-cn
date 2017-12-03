---
title: 222 - OperationFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d56766dd32acf1ef71f7c06a5c3c94cc7510070
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="222---operationfailed"></a>222 - OperationFailed
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|222|  
|关键字|EndToEndMonitoring、HealthMonitoring、疑难解答、ServiceModel|  
|级别|警告|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 如果服务模型的默认 `OperationInvoker` 在调用其方法时遇到异常，则会发出此事件。 请注意，派生自 `FaultException` 的异常会导致不发出此事件。  
  
## <a name="message"></a>消息  
 “%1”方法在由 OperationInvoker 调用时引发了未经处理的异常。 该方法调用持续了“%2”毫秒。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|方法名|`xs:string`|由 `OperationInvoker` 调用的方法的 CLR 名称。|  
|持续时间|`xs:long`|`OperationInvoker` 调用方法所花费的时间（以毫秒为单位）。|  
|HostReference|`xs:string`|对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。 其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。 示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
