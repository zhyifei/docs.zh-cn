---
title: 终结点：每秒未授权的安全调用次数
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
author: BrucePerlerMS
ms.openlocfilehash: 4abea795eb196d339beec17fa7a171927aa85324
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078365"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a>终结点：每秒未授权的安全调用次数
计数器名称：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）。  
  
## <a name="description"></a>描述  
 每秒钟内来自有效用户（但该用户没有获得执行特定任务的授权）并得到正确保护的传入消息的数量。  
  
 当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
