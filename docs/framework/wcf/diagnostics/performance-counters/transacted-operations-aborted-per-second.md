---
title: Transacted Operations Aborted Per Second（每秒中止的事务处理操作次数）
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 6369fea6def5ebb6b62274caed31d5fb63b3b0e1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417477"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="d5ae6-102">Transacted Operations Aborted Per Second（每秒中止的事务处理操作次数）</span><span class="sxs-lookup"><span data-stu-id="d5ae6-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="d5ae6-103">计数器名称：Transacted Operations Aborted Per Second（每秒中止的事务处理操作次数）。</span><span class="sxs-lookup"><span data-stu-id="d5ae6-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d5ae6-104">描述</span><span class="sxs-lookup"><span data-stu-id="d5ae6-104">Description</span></span>  
 <span data-ttu-id="d5ae6-105">在此服务中一秒内已中止的事务性操作的数量。</span><span class="sxs-lookup"><span data-stu-id="d5ae6-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="d5ae6-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="d5ae6-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d5ae6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="d5ae6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
