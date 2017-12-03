---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c0e688e1f24171494b4adaae964ac1fc2be2309
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="b85c9-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="b85c9-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="b85c9-103">对指定协调上下文的 OleTransactions 协议协商失败。</span><span class="sxs-lookup"><span data-stu-id="b85c9-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b85c9-104">描述</span><span class="sxs-lookup"><span data-stu-id="b85c9-104">Description</span></span>  
 <span data-ttu-id="b85c9-105">当带有 OleTx 信息的传入事务无法使用附加的 OleTx 信息，将回退并改用 WS-AT 时进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="b85c9-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="b85c9-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="b85c9-106">Troubleshooting</span></span>  
 <span data-ttu-id="b85c9-107">指示计算机之间的 MSDTC RPC 通信所具有的一个潜在问题。</span><span class="sxs-lookup"><span data-stu-id="b85c9-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="b85c9-108">如果日志中出现许多此类跟踪，则可能导致性能急剧下降。</span><span class="sxs-lookup"><span data-stu-id="b85c9-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="b85c9-109">如果不希望使用 OleTx，请在 WS-AT 注册表配置中将 `OleTxUpgradeEnabled` 设置为 0。</span><span class="sxs-lookup"><span data-stu-id="b85c9-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85c9-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b85c9-110">See Also</span></span>  
 [<span data-ttu-id="b85c9-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="b85c9-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b85c9-112">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="b85c9-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b85c9-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="b85c9-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
