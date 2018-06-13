---
title: PiiLoggingNotAllowed
ms.date: 03/30/2017
ms.assetid: fc34a0b6-fee7-4da4-b146-b0c1c8b7519a
ms.openlocfilehash: bbeaefc49df856e0fc3b989ad899f26052bed7b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33468278"
---
# <a name="piiloggingnotallowed"></a><span data-ttu-id="1067e-102">PiiLoggingNotAllowed</span><span class="sxs-lookup"><span data-stu-id="1067e-102">PiiLoggingNotAllowed</span></span>
<span data-ttu-id="1067e-103">ID：108</span><span class="sxs-lookup"><span data-stu-id="1067e-103">Id: 108</span></span>  
  
 <span data-ttu-id="1067e-104">严重性：错误</span><span class="sxs-lookup"><span data-stu-id="1067e-104">Severity: Error</span></span>  
  
 <span data-ttu-id="1067e-105">类别：跟踪</span><span class="sxs-lookup"><span data-stu-id="1067e-105">Category: Tracing</span></span>  
  
## <a name="description"></a><span data-ttu-id="1067e-106">描述</span><span class="sxs-lookup"><span data-stu-id="1067e-106">Description</span></span>  
 <span data-ttu-id="1067e-107">此事件指示没有正在记录的已知 PII。</span><span class="sxs-lookup"><span data-stu-id="1067e-107">This event indicates that no known PII is being logged.</span></span> <span data-ttu-id="1067e-108">不允许记录已知的 PII。</span><span class="sxs-lookup"><span data-stu-id="1067e-108">Logging of known PII is not allowed.</span></span> <span data-ttu-id="1067e-109">若要记录已知的 PII，请在 Machine.config 中将“enableLoggingKnownPii”设置为 `true`。该事件将列出进程名称和进程 ID。</span><span class="sxs-lookup"><span data-stu-id="1067e-109">To allow logging of known PII, set "enableLoggingKnownPii" to `true` in Machine.config. The event lists the process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1067e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1067e-110">See Also</span></span>  
 [<span data-ttu-id="1067e-111">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="1067e-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="1067e-112">事件常规参考</span><span class="sxs-lookup"><span data-stu-id="1067e-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
