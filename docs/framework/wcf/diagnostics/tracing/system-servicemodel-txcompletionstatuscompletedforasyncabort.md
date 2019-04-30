---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: f84cc9336d6cce7d8c477a1feb6caf45b0662177
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996926"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="9f87e-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="9f87e-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="9f87e-103">指定操作的指定事务由于异步中止而完成。</span><span class="sxs-lookup"><span data-stu-id="9f87e-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9f87e-104">描述</span><span class="sxs-lookup"><span data-stu-id="9f87e-104">Description</span></span>  
 <span data-ttu-id="9f87e-105">由于另一名参与者赞成中止，发生超时，或事务的参与者内部出现另一错误，因此当前事务被中止。</span><span class="sxs-lookup"><span data-stu-id="9f87e-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9f87e-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="9f87e-106">Troubleshooting</span></span>  
 <span data-ttu-id="9f87e-107">如果这是意外中止，请检查所有系统日志，以确定发生该中止的真正原因。</span><span class="sxs-lookup"><span data-stu-id="9f87e-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f87e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f87e-108">See also</span></span>

- [<span data-ttu-id="9f87e-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="9f87e-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9f87e-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="9f87e-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9f87e-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="9f87e-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
