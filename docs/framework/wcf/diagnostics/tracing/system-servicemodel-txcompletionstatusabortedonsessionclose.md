---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7b1f6a2f4a344b566c76d0095942b84a8a4e76f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166499"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="df7b2-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="df7b2-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="df7b2-103">指定的事务被中止，因为当会话被关闭时尚未完成，且 TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute 被设置为 false。</span><span class="sxs-lookup"><span data-stu-id="df7b2-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="df7b2-104">描述</span><span class="sxs-lookup"><span data-stu-id="df7b2-104">Description</span></span>  
 <span data-ttu-id="df7b2-105">如果当前活动会话已关闭，事务未完成，并且 TransactionAutoCompleteOnSessionClose 设置为 `false`，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="df7b2-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="df7b2-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="df7b2-106">Troubleshooting</span></span>  
 <span data-ttu-id="df7b2-107">此跟踪指示一个应予调查的潜在应用程序 Bug。</span><span class="sxs-lookup"><span data-stu-id="df7b2-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7b2-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="df7b2-108">See also</span></span>

- [<span data-ttu-id="df7b2-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="df7b2-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="df7b2-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="df7b2-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="df7b2-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="df7b2-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
