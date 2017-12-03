---
title: 3502 - InferredOperationDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 144ab1a4a2fd313dc7817846e3e0118145cd3f8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="3502---inferredoperationdescription"></a>3502 - InferredOperationDescription
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|3502|  
|关键字|WFServices|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 指示已从 WorkflowService 中推断出 OperationDescription。  
  
## <a name="message"></a>消息  
 已从 WorkflowService 中推断出协定“%2”中含有 Name='%1' 的 OperationDescription。 IsOneWay=%3。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|操作的名称。|  
|ContractName|xs:string|协定的名称。|  
|IsOneWay|xs:string|true 或 false 指示协定是否为单向。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
