---
title: 每秒实例数
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: 3ae0b83066b22187ce062596a62e9d17aa2acd45
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163795"
---
# <a name="instances-per-second"></a>每秒实例数
计数器名称：Instances Created Per Second（每秒创建的实例数）。  
  
## <a name="description"></a>描述  
 每秒创建的服务实例的总数。  
  
 此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
