---
title: 终结点：Reliable Messaging Messages Dropped Per Second（每秒丢弃的可靠消息传递消息数）
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 8f935bee06d175ce454bd7f58a1afbbe9ab505ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797197"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>终结点：Reliable Messaging Messages Dropped Per Second（每秒丢弃的可靠消息传递消息数）
计数器名称：每秒丢弃的可靠消息传送会话。  
  
## <a name="description"></a>描述  
 此终结点上每秒钟丢弃的可靠传送消息总数。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
