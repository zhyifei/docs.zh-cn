---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 695ebb2089147093601f2d51f11f11ca45861590
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a><span data-ttu-id="6692f-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="6692f-102">System.ServiceModel.TxCompletionStatusAbortedOnSessionClose</span></span>
<span data-ttu-id="6692f-103">指定的事务被中止，因为当会话被关闭时尚未完成，且 TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute 被设置为 false。</span><span class="sxs-lookup"><span data-stu-id="6692f-103">The specified transaction was aborted because it was uncompleted when the session was closed and the TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute was set to false.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6692f-104">描述</span><span class="sxs-lookup"><span data-stu-id="6692f-104">Description</span></span>  
 <span data-ttu-id="6692f-105">如果当前活动会话已关闭，事务未完成，并且 TransactionAutoCompleteOnSessionClose 设置为 `false`，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="6692f-105">Traced if the current active session was closed, and the transaction was not completed, and TransactionAutoCompleteOnSessionClose is set to `false`.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="6692f-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="6692f-106">Troubleshooting</span></span>  
 <span data-ttu-id="6692f-107">此跟踪指示一个应予调查的潜在应用程序 Bug。</span><span class="sxs-lookup"><span data-stu-id="6692f-107">This trace indicates a potential application bug that should be investigated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6692f-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6692f-108">See Also</span></span>  
 [<span data-ttu-id="6692f-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="6692f-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="6692f-110">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="6692f-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="6692f-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="6692f-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
