---
title: 实例数
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118984"
---
# <a name="instances"></a><span data-ttu-id="d7094-102">实例数</span><span class="sxs-lookup"><span data-stu-id="d7094-102">Instances</span></span>
<span data-ttu-id="d7094-103">计数器名称：实例。</span><span class="sxs-lookup"><span data-stu-id="d7094-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d7094-104">描述</span><span class="sxs-lookup"><span data-stu-id="d7094-104">Description</span></span>  
 <span data-ttu-id="d7094-105">服务当前包含的实例上下文的数量。</span><span class="sxs-lookup"><span data-stu-id="d7094-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="d7094-106">在大部分时间里，实例上下文的数量都等于实例数。</span><span class="sxs-lookup"><span data-stu-id="d7094-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="d7094-107">但是，下列方案例外。</span><span class="sxs-lookup"><span data-stu-id="d7094-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="d7094-108">服务方法显式调用 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="d7094-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="d7094-109">一个 <xref:System.ServiceModel.ReleaseInstanceMode> 被应用于一个 <xref:System.ServiceModel.OperationBehaviorAttribute> 实例。</span><span class="sxs-lookup"><span data-stu-id="d7094-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7094-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7094-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
