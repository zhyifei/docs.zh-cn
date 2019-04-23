---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 22992b4dfad4b4867adda0fcbbd8ecc5eb67d87e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160137"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="b5046-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="b5046-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="b5046-103">WS-AT 协议服务在等待可变参与方对结果消息的响应时超时。</span><span class="sxs-lookup"><span data-stu-id="b5046-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="b5046-104">如果参与方返回，则事务结果可能不确定。</span><span class="sxs-lookup"><span data-stu-id="b5046-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b5046-105">描述</span><span class="sxs-lookup"><span data-stu-id="b5046-105">Description</span></span>  
 <span data-ttu-id="b5046-106">当可变参与方已决定提交或中止，但未在给定时间内响应提交或回滚请求时跟踪。</span><span class="sxs-lookup"><span data-stu-id="b5046-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="b5046-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="b5046-107">Troubleshooting</span></span>  
 <span data-ttu-id="b5046-108">确保所有可变参与方都能在给定时间内响应。</span><span class="sxs-lookup"><span data-stu-id="b5046-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="b5046-109">默认时间为 180 秒。</span><span class="sxs-lookup"><span data-stu-id="b5046-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="b5046-110">如果此时间不够，请增加 WS-AT 的 `VolatileOutcomeDelay` 计时器策略。</span><span class="sxs-lookup"><span data-stu-id="b5046-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5046-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5046-111">See also</span></span>

- [<span data-ttu-id="b5046-112">跟踪</span><span class="sxs-lookup"><span data-stu-id="b5046-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="b5046-113">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="b5046-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="b5046-114">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="b5046-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
