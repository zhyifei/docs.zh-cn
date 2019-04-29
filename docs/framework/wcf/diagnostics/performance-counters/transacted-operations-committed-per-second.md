---
title: Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 124eae3b36a731ac50a147782b19c87e3adfa7be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766371"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="02318-102">Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）</span><span class="sxs-lookup"><span data-stu-id="02318-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="02318-103">计数器名称：每秒提交的事务处理的操作。</span><span class="sxs-lookup"><span data-stu-id="02318-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="02318-104">描述</span><span class="sxs-lookup"><span data-stu-id="02318-104">Description</span></span>  
 <span data-ttu-id="02318-105">此服务中每秒提交的事务处理操作的数量。</span><span class="sxs-lookup"><span data-stu-id="02318-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="02318-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="02318-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="02318-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="02318-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
