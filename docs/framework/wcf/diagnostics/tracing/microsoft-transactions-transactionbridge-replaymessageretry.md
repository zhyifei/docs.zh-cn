---
title: Microsoft.Transactions.TransactionBridge.ReplayMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b820ae-504d-405a-926a-9effa41d2369
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c19eede74bd1d036ae1277af5826ca8fcc7fb2d7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgereplaymessageretry"></a><span data-ttu-id="14a23-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span><span class="sxs-lookup"><span data-stu-id="14a23-102">Microsoft.Transactions.TransactionBridge.ReplayMessageRetry</span></span>
<span data-ttu-id="14a23-103">已向无响应的协调程序发送重播消息重试。</span><span class="sxs-lookup"><span data-stu-id="14a23-103">A replay message retry was sent to an unresponsive coordinator.</span></span>  
  
## <a name="description"></a><span data-ttu-id="14a23-104">描述</span><span class="sxs-lookup"><span data-stu-id="14a23-104">Description</span></span>  
 <span data-ttu-id="14a23-105">如果本地事务管理器因未在给定的时间内收到响应而需要向上级协调程序重新发送重播消息，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="14a23-105">Traced if the local Transaction Manager needed to resend a Replay message to a superior coordinator because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="14a23-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="14a23-106">Troubleshooting</span></span>  
 <span data-ttu-id="14a23-107">调查导致响应未及时传送的潜在网络或产品问题。</span><span class="sxs-lookup"><span data-stu-id="14a23-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="14a23-108">如果看到很多这样的消息，可能表明基础结构有问题或响应时间异常长。</span><span class="sxs-lookup"><span data-stu-id="14a23-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="14a23-109">这两种问题都会明显降低系统中事务的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="14a23-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a23-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14a23-110">See Also</span></span>  
 [<span data-ttu-id="14a23-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="14a23-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="14a23-112">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="14a23-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="14a23-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="14a23-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
