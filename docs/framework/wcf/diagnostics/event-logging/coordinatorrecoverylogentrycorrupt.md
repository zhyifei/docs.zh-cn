---
title: CoordinatorRecoveryLogEntryCorrupt
ms.date: 03/30/2017
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
ms.openlocfilehash: de9d27e74088b1bac9c8a401c5af2b119fc8e90e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797984"
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="4451f-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="4451f-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="4451f-103">ID:139</span><span class="sxs-lookup"><span data-stu-id="4451f-103">Id: 139</span></span>  
  
 <span data-ttu-id="4451f-104">对应Error</span><span class="sxs-lookup"><span data-stu-id="4451f-104">Severity: Error</span></span>  
  
 <span data-ttu-id="4451f-105">类别TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="4451f-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="4451f-106">描述</span><span class="sxs-lookup"><span data-stu-id="4451f-106">Description</span></span>  
 <span data-ttu-id="4451f-107">此事件指示协调程序恢复日志条目已损坏，无法进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="4451f-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="4451f-108">此错误可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="4451f-108">Data loss may result from this error.</span></span> <span data-ttu-id="4451f-109">此事件列出了事务 ID、恢复数据（Base64 编码）、异常、进程名称和进程 ID。</span><span class="sxs-lookup"><span data-stu-id="4451f-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4451f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4451f-110">See also</span></span>

- [<span data-ttu-id="4451f-111">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="4451f-111">Event Logging</span></span>](index.md)
- [<span data-ttu-id="4451f-112">事件常规参考</span><span class="sxs-lookup"><span data-stu-id="4451f-112">Events General Reference</span></span>](events-general-reference.md)
