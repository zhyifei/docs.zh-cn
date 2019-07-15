---
ms.openlocfilehash: c1a2d76b4e596acc395da6cefed008078e57a336
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858384"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="cbec4-101">在执行后一个步骤时才能在调试器中看到空联合器值</span><span class="sxs-lookup"><span data-stu-id="cbec4-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cbec4-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="cbec4-102">Details</span></span>|<span data-ttu-id="cbec4-103">在 64 位版本的 Framework 上运行时，.NET Framework 4.5 中的 bug 导致在执行分配操作后无法立即在调试器中看到通过空联合操作设置的值。</span><span class="sxs-lookup"><span data-stu-id="cbec4-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="cbec4-104">建议</span><span class="sxs-lookup"><span data-stu-id="cbec4-104">Suggestion</span></span>|<span data-ttu-id="cbec4-105">在调试器中多单步执行一次将正确更新本地/字段的值。</span><span class="sxs-lookup"><span data-stu-id="cbec4-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="cbec4-106">另外，此问题已在 .NET Framework 4.6 中解决；因此升级到该版本的 Framework 即可解决该问题。</span><span class="sxs-lookup"><span data-stu-id="cbec4-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="cbec4-107">范围</span><span class="sxs-lookup"><span data-stu-id="cbec4-107">Scope</span></span>|<span data-ttu-id="cbec4-108">边缘</span><span class="sxs-lookup"><span data-stu-id="cbec4-108">Edge</span></span>|
|<span data-ttu-id="cbec4-109">版本</span><span class="sxs-lookup"><span data-stu-id="cbec4-109">Version</span></span>|<span data-ttu-id="cbec4-110">4.5</span><span class="sxs-lookup"><span data-stu-id="cbec4-110">4.5</span></span>|
|<span data-ttu-id="cbec4-111">类型</span><span class="sxs-lookup"><span data-stu-id="cbec4-111">Type</span></span>|<span data-ttu-id="cbec4-112">运行时</span><span class="sxs-lookup"><span data-stu-id="cbec4-112">Runtime</span></span>|

