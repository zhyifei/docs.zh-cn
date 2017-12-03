---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2a99e8b3158da9d473d50bc7792ce9e2aa19bb27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="f9313-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="f9313-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="f9313-103">指定操作的指定事务由于异步中止而完成。</span><span class="sxs-lookup"><span data-stu-id="f9313-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f9313-104">描述</span><span class="sxs-lookup"><span data-stu-id="f9313-104">Description</span></span>  
 <span data-ttu-id="f9313-105">由于另一名参与者赞成中止，发生超时，或事务的参与者内部出现另一错误，因此当前事务被中止。</span><span class="sxs-lookup"><span data-stu-id="f9313-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="f9313-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="f9313-106">Troubleshooting</span></span>  
 <span data-ttu-id="f9313-107">如果这是意外中止，请检查所有系统日志，以确定发生该中止的真正原因。</span><span class="sxs-lookup"><span data-stu-id="f9313-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9313-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9313-108">See Also</span></span>  
 [<span data-ttu-id="f9313-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="f9313-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f9313-110">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="f9313-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f9313-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="f9313-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
