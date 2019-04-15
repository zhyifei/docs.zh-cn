---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235071"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="7caae-101">在执行后一个步骤时才能在调试器中看到空联合器值</span><span class="sxs-lookup"><span data-stu-id="7caae-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7caae-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="7caae-102">Details</span></span>|<span data-ttu-id="7caae-103">在 64 位版本的 Framework 上运行时，.NET Framework 4.5 中的 bug 导致在执行分配操作后无法立即在调试器中看到通过空联合操作设置的值。</span><span class="sxs-lookup"><span data-stu-id="7caae-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="7caae-104">建议</span><span class="sxs-lookup"><span data-stu-id="7caae-104">Suggestion</span></span>|<span data-ttu-id="7caae-105">在调试器中多单步执行一次将正确更新本地/字段的值。</span><span class="sxs-lookup"><span data-stu-id="7caae-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="7caae-106">另外，此问题已在 .NET Framework 4.6 中解决；因此升级到该版本的 Framework 即可解决该问题。</span><span class="sxs-lookup"><span data-stu-id="7caae-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="7caae-107">范围</span><span class="sxs-lookup"><span data-stu-id="7caae-107">Scope</span></span>|<span data-ttu-id="7caae-108">边缘</span><span class="sxs-lookup"><span data-stu-id="7caae-108">Edge</span></span>|
|<span data-ttu-id="7caae-109">版本</span><span class="sxs-lookup"><span data-stu-id="7caae-109">Version</span></span>|<span data-ttu-id="7caae-110">4.5</span><span class="sxs-lookup"><span data-stu-id="7caae-110">4.5</span></span>|
|<span data-ttu-id="7caae-111">类型</span><span class="sxs-lookup"><span data-stu-id="7caae-111">Type</span></span>|<span data-ttu-id="7caae-112">运行时</span><span class="sxs-lookup"><span data-stu-id="7caae-112">Runtime</span></span>|
