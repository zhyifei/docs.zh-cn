---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803329"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="6da4d-101">ConcurrentQueue\<T>.TryPeek 可通过 out 参数返回错误的 null</span><span class="sxs-lookup"><span data-stu-id="6da4d-101">ConcurrentQueue\<T>.TryPeek can return an erroneous null via its out parameter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6da4d-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="6da4d-102">Details</span></span>|<span data-ttu-id="6da4d-103">在某些多线程情况下，<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> 可返回 true，但使用 null 值填充 Out 参数（而非正确的扫视值）。</span><span class="sxs-lookup"><span data-stu-id="6da4d-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>|
|<span data-ttu-id="6da4d-104">建议</span><span class="sxs-lookup"><span data-stu-id="6da4d-104">Suggestion</span></span>|<span data-ttu-id="6da4d-105">此问题已在 .NET Framework 4.5.1 中解决。</span><span class="sxs-lookup"><span data-stu-id="6da4d-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="6da4d-106">升级到该 Framework 即可解决该问题。</span><span class="sxs-lookup"><span data-stu-id="6da4d-106">Upgrading to that Framework will solve the issue.</span></span>|
|<span data-ttu-id="6da4d-107">范围</span><span class="sxs-lookup"><span data-stu-id="6da4d-107">Scope</span></span>|<span data-ttu-id="6da4d-108">主要</span><span class="sxs-lookup"><span data-stu-id="6da4d-108">Major</span></span>|
|<span data-ttu-id="6da4d-109">版本</span><span class="sxs-lookup"><span data-stu-id="6da4d-109">Version</span></span>|<span data-ttu-id="6da4d-110">4.5</span><span class="sxs-lookup"><span data-stu-id="6da4d-110">4.5</span></span>|
|<span data-ttu-id="6da4d-111">类型</span><span class="sxs-lookup"><span data-stu-id="6da4d-111">Type</span></span>|<span data-ttu-id="6da4d-112">运行时</span><span class="sxs-lookup"><span data-stu-id="6da4d-112">Runtime</span></span>|
|<span data-ttu-id="6da4d-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="6da4d-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
