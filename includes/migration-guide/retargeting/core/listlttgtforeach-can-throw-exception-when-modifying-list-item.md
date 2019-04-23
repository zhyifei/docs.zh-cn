---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234619"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="bb004-101">List\<T>.ForEach 在修改列表项时可能会抛出异常</span><span class="sxs-lookup"><span data-stu-id="bb004-101">List\<T>.ForEach can throw exception when modifying list item</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bb004-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="bb004-102">Details</span></span>|<span data-ttu-id="bb004-103">从 .NET Framework 4.5 开始，如果修改了调用集合中的元素，<xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> 枚举器将引发 <xref:System.InvalidOperationException?displayProperty=name> 异常。</span><span class="sxs-lookup"><span data-stu-id="bb004-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=name> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="bb004-104">该操作在以前不会引发异常，但可能会导致争用条件。</span><span class="sxs-lookup"><span data-stu-id="bb004-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>|
|<span data-ttu-id="bb004-105">建议</span><span class="sxs-lookup"><span data-stu-id="bb004-105">Suggestion</span></span>|<span data-ttu-id="bb004-106">理想情况下，应修复代码以便在枚举列表元素时不会修改列表，因为这始终不是安全操作。</span><span class="sxs-lookup"><span data-stu-id="bb004-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="bb004-107">但是，若要还原到以前的行为，应用可面向 .NET Framework 4.0。</span><span class="sxs-lookup"><span data-stu-id="bb004-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>|
|<span data-ttu-id="bb004-108">范围</span><span class="sxs-lookup"><span data-stu-id="bb004-108">Scope</span></span>|<span data-ttu-id="bb004-109">边缘</span><span class="sxs-lookup"><span data-stu-id="bb004-109">Edge</span></span>|
|<span data-ttu-id="bb004-110">版本</span><span class="sxs-lookup"><span data-stu-id="bb004-110">Version</span></span>|<span data-ttu-id="bb004-111">4.5</span><span class="sxs-lookup"><span data-stu-id="bb004-111">4.5</span></span>|
|<span data-ttu-id="bb004-112">类型</span><span class="sxs-lookup"><span data-stu-id="bb004-112">Type</span></span>|<span data-ttu-id="bb004-113">重定目标</span><span class="sxs-lookup"><span data-stu-id="bb004-113">Retargeting</span></span>|
|<span data-ttu-id="bb004-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="bb004-114">Affected APIs</span></span>|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
