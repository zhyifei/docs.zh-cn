---
title: "服务：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ad28d6afe26537e7a3eface8be70bcecf15b7aa8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-calls-not-authorized-per-second"></a>服务：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）
计数器名称：每秒未授权的安全调用次数  
  
## <a name="description"></a>描述  
 一秒钟内来自有效用户并得到适当保护，但未授权用户执行特定任务的传入消息的数量。  
  
 当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkId=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
