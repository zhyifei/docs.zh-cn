---
title: PiiLoggingNotAllowed
ms.date: 03/30/2017
ms.assetid: fc34a0b6-fee7-4da4-b146-b0c1c8b7519a
ms.openlocfilehash: 4df8a9cae517baff99f7fb47047a3dd275c63524
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592648"
---
# <a name="piiloggingnotallowed"></a><span data-ttu-id="d3727-102">PiiLoggingNotAllowed</span><span class="sxs-lookup"><span data-stu-id="d3727-102">PiiLoggingNotAllowed</span></span>
<span data-ttu-id="d3727-103">ID:108</span><span class="sxs-lookup"><span data-stu-id="d3727-103">Id: 108</span></span>  
  
 <span data-ttu-id="d3727-104">严重性：Error</span><span class="sxs-lookup"><span data-stu-id="d3727-104">Severity: Error</span></span>  
  
 <span data-ttu-id="d3727-105">类别：跟踪</span><span class="sxs-lookup"><span data-stu-id="d3727-105">Category: Tracing</span></span>  
  
## <a name="description"></a><span data-ttu-id="d3727-106">描述</span><span class="sxs-lookup"><span data-stu-id="d3727-106">Description</span></span>  
 <span data-ttu-id="d3727-107">此事件指示没有正在记录的已知 PII。</span><span class="sxs-lookup"><span data-stu-id="d3727-107">This event indicates that no known PII is being logged.</span></span> <span data-ttu-id="d3727-108">不允许记录已知的 PII。</span><span class="sxs-lookup"><span data-stu-id="d3727-108">Logging of known PII is not allowed.</span></span> <span data-ttu-id="d3727-109">若要记录已知的 PII，请在 Machine.config 中将“enableLoggingKnownPii”设置为 `true`。该事件将列出进程名称和进程 ID。</span><span class="sxs-lookup"><span data-stu-id="d3727-109">To allow logging of known PII, set "enableLoggingKnownPii" to `true` in Machine.config. The event lists the process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3727-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3727-110">See also</span></span>
- [<span data-ttu-id="d3727-111">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="d3727-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="d3727-112">事件常规参考</span><span class="sxs-lookup"><span data-stu-id="d3727-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
