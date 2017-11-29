---
title: "终结点：每秒未授权的安全调用次数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8a1547b-986b-45c1-b302-dea0cd4b516d
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 50bb92a31af3775f17868c7057a160f64a82f0b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-security-calls-not-authorized-per-second"></a><span data-ttu-id="20120-102">终结点：每秒未授权的安全调用次数</span><span class="sxs-lookup"><span data-stu-id="20120-102">Endpoint: Security Calls Not Authorized Per Second</span></span>
<span data-ttu-id="20120-103">计数器名称：Security Calls Not Authorized Per Second（每秒未授权的安全调用次数）。</span><span class="sxs-lookup"><span data-stu-id="20120-103">Counter Name: Security Calls Not Authorized Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="20120-104">描述</span><span class="sxs-lookup"><span data-stu-id="20120-104">Description</span></span>  
 <span data-ttu-id="20120-105">每秒钟内来自有效用户（但该用户没有获得执行特定任务的授权）并得到正确保护的传入消息的数量。</span><span class="sxs-lookup"><span data-stu-id="20120-105">Number of incoming messages in a second that are from a valid user and protected properly, but the user is not authorized to do specific tasks.</span></span>  
  
 <span data-ttu-id="20120-106">当 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法返回 `false` 时，此计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="20120-106">This counter is incremented when the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method returns `false`.</span></span>  
  
 <span data-ttu-id="20120-107">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="20120-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="20120-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="20120-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
