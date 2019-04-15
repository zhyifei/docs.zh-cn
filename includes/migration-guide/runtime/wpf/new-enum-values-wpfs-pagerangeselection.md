---
ms.openlocfilehash: edd194fef27d97976f1ff45daec1cd56382bbb55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235082"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="22747-101">WPF PageRangeSelection 中的新枚举值</span><span class="sxs-lookup"><span data-stu-id="22747-101">New enum values in WPF's PageRangeSelection</span></span>

|   |   |
|---|---|
|<span data-ttu-id="22747-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="22747-102">Details</span></span>|<span data-ttu-id="22747-103">两个新成员（<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> 和 <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>）已添加到 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> 枚举。</span><span class="sxs-lookup"><span data-stu-id="22747-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> enum.</span></span>|
|<span data-ttu-id="22747-104">建议</span><span class="sxs-lookup"><span data-stu-id="22747-104">Suggestion</span></span>|<span data-ttu-id="22747-105">大多数情况下，这些更改不会影响用户代码。</span><span class="sxs-lookup"><span data-stu-id="22747-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="22747-106">但是，应该修改依赖于对 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> 类型的 <xref:System.Enum.GetNames(System.Type)> 或 <xref:System.Enum.GetValues(System.Type)> 调用中所存在特定数量元素的代码。</span><span class="sxs-lookup"><span data-stu-id="22747-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> type should be modified, though.</span></span>|
|<span data-ttu-id="22747-107">范围</span><span class="sxs-lookup"><span data-stu-id="22747-107">Scope</span></span>|<span data-ttu-id="22747-108">边缘</span><span class="sxs-lookup"><span data-stu-id="22747-108">Edge</span></span>|
|<span data-ttu-id="22747-109">版本</span><span class="sxs-lookup"><span data-stu-id="22747-109">Version</span></span>|<span data-ttu-id="22747-110">4.5</span><span class="sxs-lookup"><span data-stu-id="22747-110">4.5</span></span>|
|<span data-ttu-id="22747-111">类型</span><span class="sxs-lookup"><span data-stu-id="22747-111">Type</span></span>|<span data-ttu-id="22747-112">运行时</span><span class="sxs-lookup"><span data-stu-id="22747-112">Runtime</span></span>|
|<span data-ttu-id="22747-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="22747-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
