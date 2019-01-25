---
title: System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
ms.date: 03/30/2017
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
ms.openlocfilehash: 3d43524b7141a134b9560e92da66ef2349b8119a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631270"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforasyncabort"></a><span data-ttu-id="3f618-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="3f618-102">System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort</span></span>
<span data-ttu-id="3f618-103">指定操作的指定事务由于异步中止而完成。</span><span class="sxs-lookup"><span data-stu-id="3f618-103">The specified transaction for the specified operation was completed due to asynchronous abort.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3f618-104">描述</span><span class="sxs-lookup"><span data-stu-id="3f618-104">Description</span></span>  
 <span data-ttu-id="3f618-105">由于另一名参与者赞成中止，发生超时，或事务的参与者内部出现另一错误，因此当前事务被中止。</span><span class="sxs-lookup"><span data-stu-id="3f618-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3f618-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="3f618-106">Troubleshooting</span></span>  
 <span data-ttu-id="3f618-107">如果这是意外中止，请检查所有系统日志，以确定发生该中止的真正原因。</span><span class="sxs-lookup"><span data-stu-id="3f618-107">If this abort is unexpected, check all system logs to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f618-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f618-108">See also</span></span>
- [<span data-ttu-id="3f618-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="3f618-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3f618-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="3f618-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3f618-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="3f618-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
