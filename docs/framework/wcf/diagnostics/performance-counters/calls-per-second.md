---
title: Calls Per Second（每秒调用次数）
ms.date: 03/30/2017
ms.assetid: 0efb5a94-d83b-4793-b529-6fcbedb65c43
ms.openlocfilehash: 525f3e81c8f574dfd56b69836263472bf23f289f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43780296"
---
# <a name="calls-per-second"></a>Calls Per Second（每秒调用次数）
计数器名称：Calls Per Second（每秒调用次数）  
  
## <a name="description"></a>描述  
 一秒内对此操作调用的次数。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
