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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1db6f8dc4136623f35767c122dbea46fd4706b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="09175-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="09175-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="09175-103">Id: 139</span><span class="sxs-lookup"><span data-stu-id="09175-103">Id: 139</span></span>  
  
 <span data-ttu-id="09175-104">严重性：错误</span><span class="sxs-lookup"><span data-stu-id="09175-104">Severity: Error</span></span>  
  
 <span data-ttu-id="09175-105">类别：TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="09175-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="09175-106">描述</span><span class="sxs-lookup"><span data-stu-id="09175-106">Description</span></span>  
 <span data-ttu-id="09175-107">此事件指示协调程序恢复日志条目已损坏，无法进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="09175-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="09175-108">此错误可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="09175-108">Data loss may result from this error.</span></span> <span data-ttu-id="09175-109">此事件列出了事务 ID、恢复数据（Base64 编码）、异常、进程名称和进程 ID。</span><span class="sxs-lookup"><span data-stu-id="09175-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09175-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09175-110">See Also</span></span>  
 [<span data-ttu-id="09175-111">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="09175-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="09175-112">事件常规参考</span><span class="sxs-lookup"><span data-stu-id="09175-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
