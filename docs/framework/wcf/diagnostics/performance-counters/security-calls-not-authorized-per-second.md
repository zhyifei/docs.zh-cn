---
title: Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 15890506aece94a07d4b97101519007accf3570a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915910"
---
# <a name="security-calls-not-authorized-per-second"></a><span data-ttu-id="9e9d6-102">Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）</span><span class="sxs-lookup"><span data-stu-id="9e9d6-102">Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="9e9d6-103">计数器名称：每秒未授权的安全调用。</span><span class="sxs-lookup"><span data-stu-id="9e9d6-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9e9d6-104">描述</span><span class="sxs-lookup"><span data-stu-id="9e9d6-104">Description</span></span>  
 <span data-ttu-id="9e9d6-105">一秒内此操作中未授权的调用次数。</span><span class="sxs-lookup"><span data-stu-id="9e9d6-105">Number of calls that failed authorization in this operation in a second.</span></span>  
  
 <span data-ttu-id="9e9d6-106">当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="9e9d6-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span> <span data-ttu-id="9e9d6-107">它指示传入的消息来自有效的用户并得到了良好保护，但该用户没有获得执行特定任务的授权。</span><span class="sxs-lookup"><span data-stu-id="9e9d6-107">It indicates that the incoming message is from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="9e9d6-108">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="9e9d6-108">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9e9d6-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="9e9d6-109">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
