---
title: 服务：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）
ms.date: 03/30/2017
ms.assetid: 1eeade5a-ea62-4757-b1f9-1b1b1746abd1
author: BrucePerlerMS
ms.openlocfilehash: 17da19e88dfa837cc1e45d0b6af2ebdbfd00182c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198249"
---
# <a name="service-security-calls-not-authorized-per-second"></a><span data-ttu-id="35592-102">服务：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）</span><span class="sxs-lookup"><span data-stu-id="35592-102">Service: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="35592-103">计数器名称：每秒未授权的安全调用次数</span><span class="sxs-lookup"><span data-stu-id="35592-103">Counter name: Security Calls Not Authorized Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="35592-104">描述</span><span class="sxs-lookup"><span data-stu-id="35592-104">Description</span></span>  
 <span data-ttu-id="35592-105">一秒钟内来自有效用户并得到适当保护，但未授权用户执行特定任务的传入消息的数量。</span><span class="sxs-lookup"><span data-stu-id="35592-105">Number of incoming messages in one second, which are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="35592-106">当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="35592-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="35592-107">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="35592-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkId=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="35592-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="35592-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
