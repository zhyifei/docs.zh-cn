---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1992a209bb58c0a0d6f181eb2f1ec546d50372ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a><span data-ttu-id="96757-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span><span class="sxs-lookup"><span data-stu-id="96757-102">Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout</span></span>
<span data-ttu-id="96757-103">WS-AT 协议服务在等待可变参与方对结果消息的响应时超时。</span><span class="sxs-lookup"><span data-stu-id="96757-103">The WS-AT protocol service timed out waiting for a response to an outcome message from a volatile participant.</span></span> <span data-ttu-id="96757-104">如果参与方返回，则事务结果可能不确定。</span><span class="sxs-lookup"><span data-stu-id="96757-104">The transaction outcome may be in doubt if the participant returns.</span></span>  
  
## <a name="description"></a><span data-ttu-id="96757-105">描述</span><span class="sxs-lookup"><span data-stu-id="96757-105">Description</span></span>  
 <span data-ttu-id="96757-106">当可变参与方已决定提交或中止，但未在给定时间内响应提交或回滚请求时跟踪。</span><span class="sxs-lookup"><span data-stu-id="96757-106">Traced when a Volatile participant has decided to Commit or Abort but has not responded to a Commit or Rollback request within a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="96757-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="96757-107">Troubleshooting</span></span>  
 <span data-ttu-id="96757-108">确保所有可变参与方都能在给定时间内响应。</span><span class="sxs-lookup"><span data-stu-id="96757-108">Ensure that all Volatile participants are able to respond within the given amount of time.</span></span> <span data-ttu-id="96757-109">默认时间为 180 秒。</span><span class="sxs-lookup"><span data-stu-id="96757-109">The default time period is 180 seconds.</span></span>  <span data-ttu-id="96757-110">如果此时间不够，请增加 WS-AT 的 `VolatileOutcomeDelay` 计时器策略。</span><span class="sxs-lookup"><span data-stu-id="96757-110">If this is insufficient, increase the `VolatileOutcomeDelay` timer policy for WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96757-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96757-111">See Also</span></span>  
 [<span data-ttu-id="96757-112">跟踪</span><span class="sxs-lookup"><span data-stu-id="96757-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="96757-113">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="96757-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="96757-114">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="96757-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
