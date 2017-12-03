---
title: "Transactions Flowed Per Second（每秒流动的事务数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 776b9e9f019aadb5fa96a6b6a7bb4a4a07eb16ec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="transactions-flowed-per-second"></a>Transactions Flowed Per Second（每秒流动的事务数）
计数器名称：Transactions Flowed Per Second（每秒流动的事务数）  
  
## <a name="description"></a>描述  
 一秒内向此操作流动的事务数量。 每当发送到此操作的消息中存在事务 ID 时，此计数器就会增加。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
