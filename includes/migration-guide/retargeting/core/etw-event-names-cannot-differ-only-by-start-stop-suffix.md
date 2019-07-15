---
ms.openlocfilehash: 9ad283af76085c228bedceb6db723a1d18b10210
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804477"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="0e3a5-101">ETW 事件名称无法仅通过“Start”或“Stop”后缀区别开来</span><span class="sxs-lookup"><span data-stu-id="0e3a5-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0e3a5-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="0e3a5-102">Details</span></span>|<span data-ttu-id="0e3a5-103">在 .NET Framework 4.6 和 4.6.1 中，当两个 Windows 事件跟踪 (ETW) 事件名称只有 &quot;Start&quot; 或 &quot;Stop&quot; 后缀不同时（例如，当一个事件命名为 <code>LogUser</code>，另一个事件命名为 <code>LogUserStart</code>），运行时会引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="0e3a5-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="0e3a5-104">在这种情况下，运行时不会构建不能发出任何日志记录的事件源。</span><span class="sxs-lookup"><span data-stu-id="0e3a5-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="0e3a5-105">建议</span><span class="sxs-lookup"><span data-stu-id="0e3a5-105">Suggestion</span></span>|<span data-ttu-id="0e3a5-106">若要避免此异常，请确保两个事件名称不是只有 &quot;Start&quot; 或 &quot;Stop&quot; 后缀不同。从 .NET Framework 4.6.2 开始，将删除此要求，运行时可区分只有 &quot;Start&quot; 和 &quot;Stop&quot; 后缀不同的事件名称。</span><span class="sxs-lookup"><span data-stu-id="0e3a5-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="0e3a5-107">范围</span><span class="sxs-lookup"><span data-stu-id="0e3a5-107">Scope</span></span>|<span data-ttu-id="0e3a5-108">边缘</span><span class="sxs-lookup"><span data-stu-id="0e3a5-108">Edge</span></span>|
|<span data-ttu-id="0e3a5-109">版本</span><span class="sxs-lookup"><span data-stu-id="0e3a5-109">Version</span></span>|<span data-ttu-id="0e3a5-110">4.6</span><span class="sxs-lookup"><span data-stu-id="0e3a5-110">4.6</span></span>|
|<span data-ttu-id="0e3a5-111">类型</span><span class="sxs-lookup"><span data-stu-id="0e3a5-111">Type</span></span>|<span data-ttu-id="0e3a5-112">重定目标</span><span class="sxs-lookup"><span data-stu-id="0e3a5-112">Retargeting</span></span>|

