---
title: Microsoft.Transactions.TransactionBridge.PrepareMessageRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada4baa5-b60d-46b8-ad46-4d69f8d8a9fa
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7b53620a08d21d40a230f82b3b2b3ea3cd05feea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgepreparemessageretry"></a><span data-ttu-id="d412b-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span><span class="sxs-lookup"><span data-stu-id="d412b-102">Microsoft.Transactions.TransactionBridge.PrepareMessageRetry</span></span>
<span data-ttu-id="d412b-103">准备消息重试发送到的参与者无响应。</span><span class="sxs-lookup"><span data-stu-id="d412b-103">A prepare message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d412b-104">描述</span><span class="sxs-lookup"><span data-stu-id="d412b-104">Description</span></span>  
 <span data-ttu-id="d412b-105">如果本地事务管理器因为在指定的时间内没有收到响应，而需要向从属参与者重新发行一条 Prepare 消息，就会进行此跟踪。</span><span class="sxs-lookup"><span data-stu-id="d412b-105">Traced if the local Transaction Manager needed to resend a Prepare message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d412b-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="d412b-106">Troubleshooting</span></span>  
 <span data-ttu-id="d412b-107">调查导致响应未及时传送的潜在网络或产品问题。</span><span class="sxs-lookup"><span data-stu-id="d412b-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="d412b-108">如果看到很多这样的消息，可能表明基础结构有问题或响应时间异常长。</span><span class="sxs-lookup"><span data-stu-id="d412b-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="d412b-109">这两种问题都会明显降低系统中事务的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="d412b-109">Both issues can drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d412b-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d412b-110">See Also</span></span>  
 [<span data-ttu-id="d412b-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="d412b-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="d412b-112">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="d412b-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="d412b-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="d412b-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
