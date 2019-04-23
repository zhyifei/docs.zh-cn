---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2de1aa51d58d9d86f953e027fd3f7f172e3887d3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097559"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="1c94e-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="1c94e-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="1c94e-103">对指定协调上下文的 OleTransactions 协议协商失败。</span><span class="sxs-lookup"><span data-stu-id="1c94e-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1c94e-104">描述</span><span class="sxs-lookup"><span data-stu-id="1c94e-104">Description</span></span>  
 <span data-ttu-id="1c94e-105">当带有 OleTx 信息的传入事务无法使用附加的 OleTx 信息，将回退并改用 WS-AT 时进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="1c94e-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="1c94e-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="1c94e-106">Troubleshooting</span></span>  
 <span data-ttu-id="1c94e-107">指示计算机之间的 MSDTC RPC 通信所具有的一个潜在问题。</span><span class="sxs-lookup"><span data-stu-id="1c94e-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="1c94e-108">如果日志中出现许多此类跟踪，则可能导致性能急剧下降。</span><span class="sxs-lookup"><span data-stu-id="1c94e-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="1c94e-109">如果不希望使用 OleTx，请在 WS-AT 注册表配置中将 `OleTxUpgradeEnabled` 设置为 0。</span><span class="sxs-lookup"><span data-stu-id="1c94e-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c94e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c94e-110">See also</span></span>

- [<span data-ttu-id="1c94e-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="1c94e-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1c94e-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="1c94e-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1c94e-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="1c94e-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
