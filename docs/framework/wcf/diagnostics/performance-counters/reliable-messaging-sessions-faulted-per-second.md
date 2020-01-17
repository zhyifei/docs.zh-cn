---
title: Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: 4dd247131182aca65a837095144673690cb134c8
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163938"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）
计数器名称：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）。  
  
## <a name="description"></a>描述  
 此服务每秒出错的可靠消息会话的数目。  
  
 此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
