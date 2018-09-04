---
title: 每秒丢弃的排队消息数
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528118"
---
# <a name="queue-dropped-messages-per-second"></a>每秒丢弃的排队消息数
计数器名称：Queued Messages Dropped Per Second（每秒丢弃的排队消息数）。  
  
## <a name="description"></a>描述  
 此服务处的排队传输机制每秒丢弃的消息数。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
