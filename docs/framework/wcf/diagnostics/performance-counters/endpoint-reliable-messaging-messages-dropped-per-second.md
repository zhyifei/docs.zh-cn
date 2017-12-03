---
title: "终结点：Reliable Messaging Messages Dropped Per Second（每秒丢弃的可靠消息传递消息数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: df6db86febeb88fe934bbd509f6fe8130fd1c811
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>终结点：Reliable Messaging Messages Dropped Per Second（每秒丢弃的可靠消息传递消息数）
计数器名称：Reliable Messaging Sessions Dropped Per Second（每秒丢弃的可靠消息会话数）。  
  
## <a name="description"></a>描述  
 此终结点上每秒钟丢弃的可靠传送消息总数。  
  
 此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
