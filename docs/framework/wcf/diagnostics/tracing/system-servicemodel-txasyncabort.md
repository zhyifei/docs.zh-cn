---
title: System.ServiceModel.TxAsyncAbort
ms.date: 03/30/2017
ms.assetid: bce47ff2-abd0-4b58-8667-ebf1ef3580b8
ms.openlocfilehash: a6989da7b457e819a49d7c27e8732c7f33dc51b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133921"
---
# <a name="systemservicemodeltxasyncabort"></a><span data-ttu-id="d8760-102">System.ServiceModel.TxAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="d8760-102">System.ServiceModel.TxAsyncAbort</span></span>
<span data-ttu-id="d8760-103">指定的事务被异步中止。</span><span class="sxs-lookup"><span data-stu-id="d8760-103">The specified transaction was asynchronously aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d8760-104">描述</span><span class="sxs-lookup"><span data-stu-id="d8760-104">Description</span></span>  
 <span data-ttu-id="d8760-105">由于另一名参与者赞成中止，发生超时，或事务的参与者内部出现另一错误，因此当前事务被中止。</span><span class="sxs-lookup"><span data-stu-id="d8760-105">The current transaction was aborted due to another participant voting for Abort, time-outs occurring, or another error inside the participant of a transaction.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d8760-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="d8760-106">Troubleshooting</span></span>  
 <span data-ttu-id="d8760-107">如果该中止是意料之外的，请检查所有系统日志，以便确定发生该中止的真正原因。</span><span class="sxs-lookup"><span data-stu-id="d8760-107">Check all system logs if this abort is unexpected to determine the real reason for the abort.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8760-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8760-108">See also</span></span>

- [<span data-ttu-id="d8760-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="d8760-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d8760-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="d8760-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d8760-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="d8760-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
