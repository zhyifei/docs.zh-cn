---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b4e101c4e9e5812c32b85029e9c24d983cb5e5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="205---operationinvoked"></a>205 - OperationInvoked
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|205|  
|关键字|疑难解答，ServiceModel|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 恰好在服务模型的默认 `OperationInvoker` 开始调用方法之前发出此事件。  
  
## <a name="message"></a>消息  
 OperationInvoker 调用了“%1”方法。 调用方信息:“%2”。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|方法名|`xs:string`|由 `OperationInvoker` 调用的方法的 CLR 名称。|  
|调用方信息|`xs:string`|客户端 IP 地址和端口号（格式为“IPAddress:PortNumber”）。 需要从操作上下文的“System.ServiceModel.Channels.RemoteEndpointMessageProperty”消息属性中检索这两个值。 请注意，对于非 TCP 绑定，该值为 `null`。|  
|HostReference|`xs:string`|对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。 其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。 示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
