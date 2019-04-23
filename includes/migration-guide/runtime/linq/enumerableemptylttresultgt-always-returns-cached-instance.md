---
ms.openlocfilehash: c9efbefc2bce9e21f328680795e72b62bfcd5cbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803379"
---
### <a name="enumerableemptytresult-always-returns-cached-instance"></a><span data-ttu-id="0062e-101">Enumerable.Empty\<TResult> 始终返回缓存实例</span><span class="sxs-lookup"><span data-stu-id="0062e-101">Enumerable.Empty\<TResult> always returns cached instance</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0062e-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="0062e-102">Details</span></span>|<span data-ttu-id="0062e-103">从 .NET Framework 4.5 开始，<xref:System.Linq.Enumerable.Empty%60%601> 始终返回缓存的内部实例 <xref:System.Collections.Generic.IEnumerable%601>。以前，在调用 API 时，<xref:System.Linq.Enumerable.Empty%60%601> 将缓存空 <xref:System.Collections.Generic.IEnumerable%601>，这意味着在同时快速调用 <xref:System.Linq.Enumerable.Empty%60%601> 的某些情况下，针对 API 的不同调用将返回不同的类型实例。</span><span class="sxs-lookup"><span data-stu-id="0062e-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>|
|<span data-ttu-id="0062e-104">建议</span><span class="sxs-lookup"><span data-stu-id="0062e-104">Suggestion</span></span>|<span data-ttu-id="0062e-105">因为以前的行为不确定，所以代码不太可能依赖它。</span><span class="sxs-lookup"><span data-stu-id="0062e-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="0062e-106">但是，如果出现需要比较空枚举并希望它们有时不相等这一罕见情形，应创建显式空数组 (<code>new T[0]</code>)，而非使用 <xref:System.Linq.Enumerable.Empty%60%601>。</span><span class="sxs-lookup"><span data-stu-id="0062e-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>|
|<span data-ttu-id="0062e-107">范围</span><span class="sxs-lookup"><span data-stu-id="0062e-107">Scope</span></span>|<span data-ttu-id="0062e-108">边缘</span><span class="sxs-lookup"><span data-stu-id="0062e-108">Edge</span></span>|
|<span data-ttu-id="0062e-109">版本</span><span class="sxs-lookup"><span data-stu-id="0062e-109">Version</span></span>|<span data-ttu-id="0062e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="0062e-110">4.5</span></span>|
|<span data-ttu-id="0062e-111">类型</span><span class="sxs-lookup"><span data-stu-id="0062e-111">Type</span></span>|<span data-ttu-id="0062e-112">运行时</span><span class="sxs-lookup"><span data-stu-id="0062e-112">Runtime</span></span>|
|<span data-ttu-id="0062e-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="0062e-113">Affected APIs</span></span>|<ul><li><xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
