---
title: 4202 - StartSqlCommandExecute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d54660ed7f278b1f82fac81c31b8a30e20a2e7d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4202---startsqlcommandexecute"></a>4202 - StartSqlCommandExecute
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|4202|  
|关键字|WFInstanceStore|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 SQL 命令正在执行。  
  
## <a name="message"></a>消息  
 正在开始 SQL 命令执行: %1  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|SqlCommand|xs:string|已执行的 SQL 命令。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
