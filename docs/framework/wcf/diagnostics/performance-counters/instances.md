---
title: "实例数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87423c3de551cb9fbf8c5a7756e2f0f999129a3b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="instances"></a><span data-ttu-id="9e0b8-102">实例数</span><span class="sxs-lookup"><span data-stu-id="9e0b8-102">Instances</span></span>
<span data-ttu-id="9e0b8-103">计数器名称：Instances（实例数）。</span><span class="sxs-lookup"><span data-stu-id="9e0b8-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9e0b8-104">描述</span><span class="sxs-lookup"><span data-stu-id="9e0b8-104">Description</span></span>  
 <span data-ttu-id="9e0b8-105">服务当前包含的实例上下文的数量。</span><span class="sxs-lookup"><span data-stu-id="9e0b8-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="9e0b8-106">在大部分时间里，实例上下文的数量都等于实例数。</span><span class="sxs-lookup"><span data-stu-id="9e0b8-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="9e0b8-107">但是，下列方案例外。</span><span class="sxs-lookup"><span data-stu-id="9e0b8-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="9e0b8-108">服务方法显式调用 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="9e0b8-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="9e0b8-109">一个 <xref:System.ServiceModel.ReleaseInstanceMode> 被应用于一个 <xref:System.ServiceModel.OperationBehaviorAttribute> 实例。</span><span class="sxs-lookup"><span data-stu-id="9e0b8-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0b8-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e0b8-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
