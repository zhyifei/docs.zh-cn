---
title: 终结点：每秒未授权的安全调用次数
ms.date: 03/30/2017
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
author: BrucePerlerMS
ms.openlocfilehash: 4abea795eb196d339beec17fa7a171927aa85324
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47194056"
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="f0b46-102">终结点：每秒未授权的安全调用次数</span><span class="sxs-lookup"><span data-stu-id="f0b46-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="f0b46-103">计数器名称：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）。</span><span class="sxs-lookup"><span data-stu-id="f0b46-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f0b46-104">描述</span><span class="sxs-lookup"><span data-stu-id="f0b46-104">Description</span></span>  
 <span data-ttu-id="f0b46-105">每秒钟内来自有效用户（但该用户没有获得执行特定任务的授权）并得到正确保护的传入消息的数量。</span><span class="sxs-lookup"><span data-stu-id="f0b46-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="f0b46-106">当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="f0b46-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="f0b46-107">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="f0b46-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f0b46-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f0b46-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
