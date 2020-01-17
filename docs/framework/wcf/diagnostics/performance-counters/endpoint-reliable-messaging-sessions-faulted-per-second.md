---
title: 终结点：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）
ms.date: 03/30/2017
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
ms.openlocfilehash: 26fd8236af6516716f7cf9c7c06f669473bdfc3a
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163184"
---
# <a name="endpoint-reliable-messaging-sessions-faulted-per-second"></a>终结点：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）
计数器名称：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）。  
  
## <a name="description"></a>描述  
 此终结点上每秒出错的可靠消息会话的数量。  
  
 此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
