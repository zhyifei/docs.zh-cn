---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: fb69c3c737a0e77b05e08ab8d8282069feb069bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761515"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="b0ef0-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="b0ef0-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="b0ef0-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="b0ef0-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="b0ef0-104">描述</span><span class="sxs-lookup"><span data-stu-id="b0ef0-104">Description</span></span>  
 <span data-ttu-id="b0ef0-105">系统已达到为 ManualFlowControlLimit throttle 阈值设置的限制。</span><span class="sxs-lookup"><span data-stu-id="b0ef0-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="b0ef0-106">通过对 ServiceHost 或 InstanceContext 上的 ManualFlowControlLimit 属性进行适当修改，可以更改该阈值。</span><span class="sxs-lookup"><span data-stu-id="b0ef0-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="b0ef0-107">在手动流控制限制最初减少为 0 时发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="b0ef0-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="b0ef0-108">不跟踪后续更改为 0 的情况。</span><span class="sxs-lookup"><span data-stu-id="b0ef0-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="b0ef0-109">对于每个上下文只跟踪一次实例上下文上的流控制限制。</span><span class="sxs-lookup"><span data-stu-id="b0ef0-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ef0-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0ef0-110">See also</span></span>

- [<span data-ttu-id="b0ef0-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="b0ef0-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="b0ef0-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="b0ef0-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b0ef0-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="b0ef0-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
