---
title: "Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a17d99329248dff4a29f3c68649c67622c45d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transacted-operations-committed-per-second"></a>Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）
计数器名称：Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）。  
  
## <a name="description"></a>描述  
 此服务中每秒提交的事务处理操作的数量。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
