---
title: Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: f7365c4e5f03711129916c8c6964f7e25e9b553e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734715"
---
# <a name="transacted-operations-in-doubt-per-second"></a>Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）
计数器名称：Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）。  
  
## <a name="description"></a>描述  
 此服务中每秒产生不确定结果的事务性操作的数量。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
