---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 9dd2ba5a3e94ff794d4b8a8775944355b105f790
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33482003"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="2aa7c-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="2aa7c-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="2aa7c-103">WS-AT 协议服务无法使用提供的协调上下文在事务上登记。</span><span class="sxs-lookup"><span data-stu-id="2aa7c-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2aa7c-104">描述</span><span class="sxs-lookup"><span data-stu-id="2aa7c-104">Description</span></span>  
 <span data-ttu-id="2aa7c-105">对于给定的 2pc 协议，当 MSDTC 无法在事务上登记时跟踪。</span><span class="sxs-lookup"><span data-stu-id="2aa7c-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="2aa7c-106">当事务不再存在、不再允许登记或者已存在过多的登记项时可能出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="2aa7c-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2aa7c-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2aa7c-107">Troubleshooting</span></span>  
 <span data-ttu-id="2aa7c-108">检查跟踪消息中的状态字符串以确定是否存在任何可操作的项。</span><span class="sxs-lookup"><span data-stu-id="2aa7c-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa7c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="2aa7c-109">See Also</span></span>  
 [<span data-ttu-id="2aa7c-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="2aa7c-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2aa7c-111">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="2aa7c-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2aa7c-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="2aa7c-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
