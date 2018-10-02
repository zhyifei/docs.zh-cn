---
title: 每秒拒绝的排队消息数
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 096e2188b13d0fd5a9be35e5e6473107a58c5566
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507275"
---
# <a name="queued-rejected-messages-per-second"></a>每秒拒绝的排队消息数
计数器名称：Queued Messages Rejected Per Second（每秒拒绝的排队消息数）。  
  
## <a name="description"></a>描述  
 此服务中每秒被排队传输拒绝的消息数。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
