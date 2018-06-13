---
title: Transacted Operations Aborted Per Second（每秒中止的事务处理操作次数）
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: dacdf93f4610df9161134a41ece19fd2a18637c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474527"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="a7a7d-102">Transacted Operations Aborted Per Second（每秒中止的事务处理操作次数）</span><span class="sxs-lookup"><span data-stu-id="a7a7d-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="a7a7d-103">计数器名称：Transacted Operations Aborted Per Second（每秒中止的事务处理操作次数）。</span><span class="sxs-lookup"><span data-stu-id="a7a7d-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a7a7d-104">描述</span><span class="sxs-lookup"><span data-stu-id="a7a7d-104">Description</span></span>  
 <span data-ttu-id="a7a7d-105">在此服务中一秒内已中止的事务性操作的数量。</span><span class="sxs-lookup"><span data-stu-id="a7a7d-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="a7a7d-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="a7a7d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a7a7d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a7a7d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
