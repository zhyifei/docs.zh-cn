---
title: 3501 - InferredContractDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 685d2a257dfe6aac892435e2b7a3dbd9599405d0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="3501---inferredcontractdescription"></a>3501 - InferredContractDescription
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|3501|  
|关键字|WFServices|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 指示已从 WorkflowService 中推断出 ContractDescription。  
  
## <a name="message"></a>消息  
 已从 WorkflowService 中推断出含有 Name 为“%1”和 Namespace 为“%2”的 ContractDescription。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|名称|xs:string|ContractDescription 的名称。|  
|命名空间|xs:string|ContractDescription 的命名空间。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
