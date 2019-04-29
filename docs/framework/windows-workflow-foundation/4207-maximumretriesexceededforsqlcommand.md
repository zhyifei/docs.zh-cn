---
title: 4207 - MaximumRetriesExceededForSqlCommand
ms.date: 03/30/2017
ms.assetid: 8c8bee26-9ad4-4e01-bd16-0e1fd510fb6b
ms.openlocfilehash: b763e087d8ead2bcc0fadd1d0223ae1bd58c9fd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774304"
---
# <a name="4207---maximumretriesexceededforsqlcommand"></a>4207 - MaximumRetriesExceededForSqlCommand
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|4207|  
|关键字|配额，FInstanceStore|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 SQL 提供程序正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。  
  
## <a name="message"></a>消息  
 正在放弃重试 SQL 命令，因为执行次数已达到了允许的最多重试次数。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
