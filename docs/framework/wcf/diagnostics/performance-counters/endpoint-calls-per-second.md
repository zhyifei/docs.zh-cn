---
title: 终结点：Calls Per Second（每秒调用次数）
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: a70df63f6fd268abdd2e1799d1aa38afb41e2811
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486917"
---
# <a name="endpoint-calls-per-second"></a>终结点：Calls Per Second（每秒调用次数）
计数器名称：Calls Per Second（每秒调用次数）  
  
## <a name="description"></a>描述  
 一秒内对此终结点的调用次数。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
