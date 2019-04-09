---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: faf4a07badb71588c601cd9390e4d8e3f187e629
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121623"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="80d6e-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="80d6e-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="80d6e-103">ID:139</span><span class="sxs-lookup"><span data-stu-id="80d6e-103">Id: 139</span></span>  
  
 <span data-ttu-id="80d6e-104">严重性：Error</span><span class="sxs-lookup"><span data-stu-id="80d6e-104">Severity: Error</span></span>  
  
 <span data-ttu-id="80d6e-105">类别：TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="80d6e-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="80d6e-106">描述</span><span class="sxs-lookup"><span data-stu-id="80d6e-106">Description</span></span>  
 <span data-ttu-id="80d6e-107">此事件指示协调程序恢复日志条目已损坏，无法进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="80d6e-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="80d6e-108">此错误可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="80d6e-108">Data loss may result from this error.</span></span> <span data-ttu-id="80d6e-109">此事件列出了事务 ID、恢复数据（Base64 编码）、异常、进程名称和进程 ID。</span><span class="sxs-lookup"><span data-stu-id="80d6e-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d6e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="80d6e-110">See also</span></span>

- [<span data-ttu-id="80d6e-111">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="80d6e-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="80d6e-112">事件常规参考</span><span class="sxs-lookup"><span data-stu-id="80d6e-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
