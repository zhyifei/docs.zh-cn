---
title: 每秒实例数
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: f0797c38a5eb7399817eaf6aad9fb5b6ecbfab89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916488"
---
# <a name="instances-per-second"></a>每秒实例数
计数器名称：每秒创建的实例。  
  
## <a name="description"></a>描述  
 每秒创建的服务实例的总数。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
