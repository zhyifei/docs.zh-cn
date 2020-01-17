---
title: 终结点：Calls Per Second（每秒调用次数）
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: d639d881bcedd336c7bbabd28ec385f60ff54d43
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163782"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="cc35b-102">终结点：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="cc35b-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="cc35b-103">计数器名称：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="cc35b-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cc35b-104">描述</span><span class="sxs-lookup"><span data-stu-id="cc35b-104">Description</span></span>  
 <span data-ttu-id="cc35b-105">一秒内对此终结点的调用次数。</span><span class="sxs-lookup"><span data-stu-id="cc35b-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="cc35b-106">此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="cc35b-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="cc35b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="cc35b-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
