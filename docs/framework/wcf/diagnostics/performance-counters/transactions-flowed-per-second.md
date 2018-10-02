---
title: Transactions Flowed Per Second（每秒流动的事务数）
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501299"
---
# <a name="transactions-flowed-per-second"></a>Transactions Flowed Per Second（每秒流动的事务数）
计数器名称：Transactions Flowed Per Second（每秒流动的事务数）  
  
## <a name="description"></a>描述  
 一秒内向此操作流动的事务数量。 每当发送到此操作的消息中存在事务 ID 时，此计数器就会增加。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
