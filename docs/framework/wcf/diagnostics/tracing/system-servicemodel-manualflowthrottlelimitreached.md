---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: a6b4e369d2d22d2441b3896321b7c152e21d967b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33483326"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="cd1bf-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="cd1bf-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="cd1bf-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="cd1bf-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="cd1bf-104">描述</span><span class="sxs-lookup"><span data-stu-id="cd1bf-104">Description</span></span>  
 <span data-ttu-id="cd1bf-105">系统已达到为 ManualFlowControlLimit throttle 阈值设置的限制。</span><span class="sxs-lookup"><span data-stu-id="cd1bf-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="cd1bf-106">通过对 ServiceHost 或 InstanceContext 上的 ManualFlowControlLimit 属性进行适当修改，可以更改该阈值。</span><span class="sxs-lookup"><span data-stu-id="cd1bf-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="cd1bf-107">在手动流控制限制最初减少为 0 时发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="cd1bf-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="cd1bf-108">不跟踪后续更改为 0 的情况。</span><span class="sxs-lookup"><span data-stu-id="cd1bf-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="cd1bf-109">对于每个上下文只跟踪一次实例上下文上的流控制限制。</span><span class="sxs-lookup"><span data-stu-id="cd1bf-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd1bf-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd1bf-110">See Also</span></span>  
 [<span data-ttu-id="cd1bf-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="cd1bf-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="cd1bf-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="cd1bf-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="cd1bf-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="cd1bf-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
