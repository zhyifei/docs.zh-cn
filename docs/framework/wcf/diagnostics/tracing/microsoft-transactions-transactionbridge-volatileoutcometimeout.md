---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: b64f61d25c3be87019151cbf560becd3384ec182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475626"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="26fc7-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="26fc7-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="26fc7-103">WS-AT 协议服务在等待可变参与方对结果消息的响应时超时。</span><span class="sxs-lookup"><span data-stu-id="26fc7-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="26fc7-104">如果参与方返回，则事务结果可能不确定。</span><span class="sxs-lookup"><span data-stu-id="26fc7-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="26fc7-105">描述</span><span class="sxs-lookup"><span data-stu-id="26fc7-105">Description</span></span>  
 <span data-ttu-id="26fc7-106">当可变参与方已决定提交或中止，但未在给定时间内响应提交或回滚请求时跟踪。</span><span class="sxs-lookup"><span data-stu-id="26fc7-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="26fc7-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="26fc7-107">Troubleshooting</span></span>  
 <span data-ttu-id="26fc7-108">确保所有可变参与方都能在给定时间内响应。</span><span class="sxs-lookup"><span data-stu-id="26fc7-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="26fc7-109">默认时间为 180 秒。</span><span class="sxs-lookup"><span data-stu-id="26fc7-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="26fc7-110">如果此时间不够，请增加 WS-AT 的 `VolatileOutcomeDelay` 计时器策略。</span><span class="sxs-lookup"><span data-stu-id="26fc7-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26fc7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="26fc7-111">See Also</span></span>  
 [<span data-ttu-id="26fc7-112">跟踪</span><span class="sxs-lookup"><span data-stu-id="26fc7-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="26fc7-113">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="26fc7-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="26fc7-114">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="26fc7-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
