---
title: 实例数
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: a95acf8e775e0802dc0ed781c562fa6373995a70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473037"
---
# <a name="instances"></a><span data-ttu-id="842e0-102">实例数</span><span class="sxs-lookup"><span data-stu-id="842e0-102">Instances</span></span>
<span data-ttu-id="842e0-103">计数器名称：Instances（实例数）。</span><span class="sxs-lookup"><span data-stu-id="842e0-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="842e0-104">描述</span><span class="sxs-lookup"><span data-stu-id="842e0-104">Description</span></span>  
 <span data-ttu-id="842e0-105">服务当前包含的实例上下文的数量。</span><span class="sxs-lookup"><span data-stu-id="842e0-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="842e0-106">在大部分时间里，实例上下文的数量都等于实例数。</span><span class="sxs-lookup"><span data-stu-id="842e0-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="842e0-107">但是，下列方案例外。</span><span class="sxs-lookup"><span data-stu-id="842e0-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="842e0-108">服务方法显式调用 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="842e0-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="842e0-109">一个 <xref:System.ServiceModel.ReleaseInstanceMode> 被应用于一个 <xref:System.ServiceModel.OperationBehaviorAttribute> 实例。</span><span class="sxs-lookup"><span data-stu-id="842e0-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="842e0-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="842e0-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
