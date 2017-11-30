---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5fa64c87bc4cd0c8dc677d8b4c59de45e31d3270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="a6742-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="a6742-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="a6742-103">WS-AT 协议服务无法使用提供的协调上下文在事务上登记。</span><span class="sxs-lookup"><span data-stu-id="a6742-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a6742-104">描述</span><span class="sxs-lookup"><span data-stu-id="a6742-104">Description</span></span>  
 <span data-ttu-id="a6742-105">对于给定的 2pc 协议，当 MSDTC 无法在事务上登记时跟踪。</span><span class="sxs-lookup"><span data-stu-id="a6742-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="a6742-106">当事务不再存在、不再允许登记或者已存在过多的登记项时可能出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="a6742-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="a6742-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="a6742-107">Troubleshooting</span></span>  
 <span data-ttu-id="a6742-108">检查跟踪消息中的状态字符串以确定是否存在任何可操作的项。</span><span class="sxs-lookup"><span data-stu-id="a6742-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6742-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6742-109">See Also</span></span>  
 [<span data-ttu-id="a6742-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="a6742-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="a6742-111">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="a6742-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="a6742-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="a6742-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
