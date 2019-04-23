---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 3c398aa13a8cd2b87068216d3c07fb29e1a27c3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168098"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="abd77-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="abd77-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>
<span data-ttu-id="abd77-103">已向无反应参与者发送提交消息重试。</span><span class="sxs-lookup"><span data-stu-id="abd77-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="abd77-104">描述</span><span class="sxs-lookup"><span data-stu-id="abd77-104">Description</span></span>  
 <span data-ttu-id="abd77-105">如果本地事务管理器在给定时间内未收到响应，因而需要向从属参与者重新发送“提交”消息，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="abd77-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="abd77-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="abd77-106">Troubleshooting</span></span>  
 <span data-ttu-id="abd77-107">调查导致响应未及时传送的潜在网络或产品问题。</span><span class="sxs-lookup"><span data-stu-id="abd77-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="abd77-108">如果看到很多这样的消息，可能表明基础结构有问题或响应时间异常长。</span><span class="sxs-lookup"><span data-stu-id="abd77-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="abd77-109">这两种问题都会明显降低系统中事务的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="abd77-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd77-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="abd77-110">See also</span></span>

- [<span data-ttu-id="abd77-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="abd77-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="abd77-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="abd77-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="abd77-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="abd77-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
