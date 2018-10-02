---
title: Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964600"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）
计数器名称：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）。  
  
## <a name="description"></a>描述  
 此服务每秒出错的可靠消息会话的数目。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
