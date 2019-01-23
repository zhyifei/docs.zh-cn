---
title: Microsoft.Transactions.TransactionBridge.PreparedMessageRetry
ms.date: 03/30/2017
ms.assetid: 2194292d-bf5f-4aef-9336-cd3c4795cb71
ms.openlocfilehash: e5735596f1b724e47cdaadd30f07629ea6b772eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585924"
---
# <a name="microsofttransactionstransactionbridgepreparedmessageretry"></a><span data-ttu-id="51bce-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span><span class="sxs-lookup"><span data-stu-id="51bce-102">Microsoft.Transactions.TransactionBridge.PreparedMessageRetry</span></span>
<span data-ttu-id="51bce-103">准备的消息重试发送到的协调程序无响应。</span><span class="sxs-lookup"><span data-stu-id="51bce-103">A prepared message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="51bce-104">描述</span><span class="sxs-lookup"><span data-stu-id="51bce-104">Description</span></span>  
 <span data-ttu-id="51bce-105">跟踪本地事务管理器在给定时间内未接收到响应时是否需要向上级协调器重新发送准备的消息/</span><span class="sxs-lookup"><span data-stu-id="51bce-105">Traced if the local Transaction Manager needed to resend a Prepared message to a superior coordinator because it did not receive a response in a given amount of time/</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="51bce-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="51bce-106">Troubleshooting</span></span>  
 <span data-ttu-id="51bce-107">调查导致响应未及时传送的潜在网络或产品问题。</span><span class="sxs-lookup"><span data-stu-id="51bce-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="51bce-108">如果看到很多这样的消息，可能表明基础结构有问题或响应时间异常长。</span><span class="sxs-lookup"><span data-stu-id="51bce-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="51bce-109">这两种问题都会明显降低系统中事务的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="51bce-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51bce-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="51bce-110">See also</span></span>
- [<span data-ttu-id="51bce-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="51bce-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="51bce-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="51bce-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="51bce-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="51bce-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
