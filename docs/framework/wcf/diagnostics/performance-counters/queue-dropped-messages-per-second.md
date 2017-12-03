---
title: "每秒丢弃的排队消息数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d97d78ddbf52e821cfff2aac08b41e732b189602
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="25708-102">每秒丢弃的排队消息数</span><span class="sxs-lookup"><span data-stu-id="25708-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="25708-103">计数器名称：Queued Messages Dropped Per Second（每秒丢弃的排队消息数）。</span><span class="sxs-lookup"><span data-stu-id="25708-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="25708-104">描述</span><span class="sxs-lookup"><span data-stu-id="25708-104">Description</span></span>  
 <span data-ttu-id="25708-105">此服务处的排队传输机制每秒丢弃的消息数。</span><span class="sxs-lookup"><span data-stu-id="25708-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="25708-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="25708-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="25708-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="25708-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
