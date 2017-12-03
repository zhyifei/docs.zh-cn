---
title: "Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8708e7f030e0c10028938abcdccb54903a7fca52
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="759a1-102">Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）</span><span class="sxs-lookup"><span data-stu-id="759a1-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="759a1-103">计数器名称：Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）。</span><span class="sxs-lookup"><span data-stu-id="759a1-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="759a1-104">描述</span><span class="sxs-lookup"><span data-stu-id="759a1-104">Description</span></span>  
 <span data-ttu-id="759a1-105">此服务中每秒提交的事务处理操作的数量。</span><span class="sxs-lookup"><span data-stu-id="759a1-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="759a1-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="759a1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="759a1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="759a1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
