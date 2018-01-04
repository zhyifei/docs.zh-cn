---
title: CoordinatorRecoveryLogEntryCorrupt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae2b8a8bb536d914edd6c7154136867caee553b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="25f64-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="25f64-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="25f64-103">Id: 139</span><span class="sxs-lookup"><span data-stu-id="25f64-103">Id: 139</span></span>  
  
 <span data-ttu-id="25f64-104">严重性：错误</span><span class="sxs-lookup"><span data-stu-id="25f64-104">Severity: Error</span></span>  
  
 <span data-ttu-id="25f64-105">类别：TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="25f64-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="25f64-106">描述</span><span class="sxs-lookup"><span data-stu-id="25f64-106">Description</span></span>  
 <span data-ttu-id="25f64-107">此事件指示协调程序恢复日志条目已损坏，无法进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="25f64-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="25f64-108">此错误可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="25f64-108">Data loss may result from this error.</span></span> <span data-ttu-id="25f64-109">此事件列出了事务 ID、恢复数据（Base64 编码）、异常、进程名称和进程 ID。</span><span class="sxs-lookup"><span data-stu-id="25f64-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f64-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="25f64-110">See Also</span></span>  
 [<span data-ttu-id="25f64-111">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="25f64-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="25f64-112">事件常规参考</span><span class="sxs-lookup"><span data-stu-id="25f64-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
