---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.date: 03/30/2017
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
ms.openlocfilehash: 7ecc70f1c4d7184401dd29908968f628f2e6792a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484209"
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="b4aec-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="b4aec-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="b4aec-103">指定的事务被中止，因为当会话被关闭时尚未完成，且 TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute 被设置为 false。</span><span class="sxs-lookup"><span data-stu-id="b4aec-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4aec-104">描述</span><span class="sxs-lookup"><span data-stu-id="b4aec-104">Description</span></span>  
 <span data-ttu-id="b4aec-105">如果当前活动会话已关闭，事务未完成，并且 TransactionAutoCompleteOnSessionClose 设置为 `false`，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="b4aec-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="b4aec-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="b4aec-106">Troubleshooting</span></span>  
 <span data-ttu-id="b4aec-107">此跟踪指示一个应予调查的潜在应用程序 Bug。</span><span class="sxs-lookup"><span data-stu-id="b4aec-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4aec-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4aec-108">See Also</span></span>  
 [<span data-ttu-id="b4aec-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="b4aec-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="b4aec-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="b4aec-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="b4aec-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="b4aec-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
