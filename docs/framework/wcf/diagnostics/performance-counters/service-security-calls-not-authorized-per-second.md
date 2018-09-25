---
title: 服务：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
author: BrucePerlerMS
ms.openlocfilehash: 17da19e88dfa837cc1e45d0b6af2ebdbfd00182c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157124"
---
# <a name="service-security-calls-not-authorized-per-second"></a>服务：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）
计数器名称：每秒未授权的安全调用次数  
  
## <a name="description"></a>描述  
 一秒钟内来自有效用户并得到适当保护，但未授权用户执行特定任务的传入消息的数量。  
  
 当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
