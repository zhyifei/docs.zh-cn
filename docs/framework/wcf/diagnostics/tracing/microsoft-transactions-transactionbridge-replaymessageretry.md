---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.date: 03/30/2017
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
ms.openlocfilehash: bb7f6fcf95d1ff253fa0e2963610bee2b65ef3c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597107"
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="bc636-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="bc636-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="bc636-103">已向无响应的协调程序发送重播消息重试。</span><span class="sxs-lookup"><span data-stu-id="bc636-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bc636-104">描述</span><span class="sxs-lookup"><span data-stu-id="bc636-104">Description</span></span>  
 <span data-ttu-id="bc636-105">如果本地事务管理器因未在给定的时间内收到响应而需要向上级协调程序重新发送重播消息，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="bc636-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="bc636-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="bc636-106">Troubleshooting</span></span>  
 <span data-ttu-id="bc636-107">调查导致响应未及时传送的潜在网络或产品问题。</span><span class="sxs-lookup"><span data-stu-id="bc636-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="bc636-108">如果看到很多这样的消息，可能表明基础结构有问题或响应时间异常长。</span><span class="sxs-lookup"><span data-stu-id="bc636-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="bc636-109">这两种问题都会明显降低系统中事务的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="bc636-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc636-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc636-110">See also</span></span>
- [<span data-ttu-id="bc636-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="bc636-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="bc636-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="bc636-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bc636-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="bc636-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
