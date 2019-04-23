---
title: PiiLoggingNotAllowed
ms.date: 03/30/2017
ms.assetid: fc34a0b6-fee7-4da4-b146-b0c1c8b7519a
ms.openlocfilehash: 7e1ee746c16eabfa84d96d9157a6248f640e5a1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150041"
---
# <a name="piiloggingnotallowed"></a><span data-ttu-id="dfa97-102">PiiLoggingNotAllowed</span><span class="sxs-lookup"><span data-stu-id="dfa97-102">PiiLoggingNotAllowed</span></span>
<span data-ttu-id="dfa97-103">ID:108</span><span class="sxs-lookup"><span data-stu-id="dfa97-103">Id: 108</span></span>  
  
 <span data-ttu-id="dfa97-104">严重性：Error</span><span class="sxs-lookup"><span data-stu-id="dfa97-104">Severity: Error</span></span>  
  
 <span data-ttu-id="dfa97-105">类别：跟踪</span><span class="sxs-lookup"><span data-stu-id="dfa97-105">Category: Tracing</span></span>  
  
## <a name="description"></a><span data-ttu-id="dfa97-106">描述</span><span class="sxs-lookup"><span data-stu-id="dfa97-106">Description</span></span>  
 <span data-ttu-id="dfa97-107">此事件指示没有正在记录的已知 PII。</span><span class="sxs-lookup"><span data-stu-id="dfa97-107">This event indicates that no known PII is being logged.</span></span> <span data-ttu-id="dfa97-108">不允许记录已知的 PII。</span><span class="sxs-lookup"><span data-stu-id="dfa97-108">Logging of known PII is not allowed.</span></span> <span data-ttu-id="dfa97-109">若要记录已知的 PII，请在 Machine.config 中将“enableLoggingKnownPii”设置为 `true`。该事件将列出进程名称和进程 ID。</span><span class="sxs-lookup"><span data-stu-id="dfa97-109">To allow logging of known PII, set "enableLoggingKnownPii" to `true` in Machine.config. The event lists the process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa97-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa97-110">See also</span></span>

- [<span data-ttu-id="dfa97-111">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="dfa97-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)
- [<span data-ttu-id="dfa97-112">事件常规参考</span><span class="sxs-lookup"><span data-stu-id="dfa97-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
