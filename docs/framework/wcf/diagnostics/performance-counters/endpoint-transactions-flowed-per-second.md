---
title: "终结点：Transactions Flowed Per Second（每秒流动的事务数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 58d1bec0110d669258e8f003cb1e882207133a5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-transactions-flowed-per-second"></a>终结点：Transactions Flowed Per Second（每秒流动的事务数）
计数器名称：Transactions Flowed Per Second（每秒流动的事务数）。  
  
## <a name="description"></a>描述  
 一秒内流向此终结点上的操作的事务数。 只要发送到终结点的消息中出现事务 ID，此计数器即会递增。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
