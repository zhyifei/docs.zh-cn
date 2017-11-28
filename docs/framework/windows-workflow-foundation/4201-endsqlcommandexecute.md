---
title: 4201 - EndSqlCommandExecute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 57c413ddae884f50e8f65eac146ccf5b2fc84b8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4201---endsqlcommandexecute"></a>4201 - EndSqlCommandExecute
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|4201|  
|关键字|WFInstanceStore|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 SQL 命令已完成执行。  
  
## <a name="message"></a>消息  
 结束 SQL 命令执行: %1  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|SqlCommand|xs:string|已执行的 SQL 命令。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
