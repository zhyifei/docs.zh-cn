---
title: "缓解：网格控件向 *-列分配空间"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- Grid control retargeting changes
ms.assetid: 707c064d-85e9-4ea1-aefb-e42b60b88679
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54391538ac0b2daf307cba2f7ceff1984d26b0ce
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a><span data-ttu-id="6e3ed-102">缓解：网格控件向 *-列分配空间</span><span class="sxs-lookup"><span data-stu-id="6e3ed-102">Mitigation: Grid Control&#39;s Space Allocation to Star-columns</span></span>

<span data-ttu-id="6e3ed-103">自定位 .NET Framework 4.7 的应用程序起，WPF 替换了 <xref:System.Windows.Controls.Grid> 控件用于向 \*-列分配空间的算法。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-103">Starting with applications that the .NET Framework 4.7, WPF replaces the algorithm that the <xref:System.Windows.Controls.Grid> control uses to allocate space to \*-columns.</span></span> 

## <a name="whats-changed"></a><span data-ttu-id="6e3ed-104">具体更改</span><span class="sxs-lookup"><span data-stu-id="6e3ed-104">What's changed</span></span>

<span data-ttu-id="6e3ed-105">新算法修复了旧算法中的以下多处 bug：</span><span class="sxs-lookup"><span data-stu-id="6e3ed-105">The new algorithm fixes several bugs present in the old algorithm:</span></span>

1. <span data-ttu-id="6e3ed-106">向列分配的总空间可能会超过网格宽度。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-106">Total allocation to columns can exceed the Grid's width.</span></span> <span data-ttu-id="6e3ed-107">当向比例份额小于其大小下限的列分配空间时，可能会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-107">This can occur when allocating space to a column whose proportional share is less than its minimum size.</span></span> <span data-ttu-id="6e3ed-108">算法会分配大小下限对应的空间，这将减少其他列的可用空间。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-108">The algorithm allocates the minimum size, which decreases the space available to other columns.</span></span> <span data-ttu-id="6e3ed-109">如果没有可分配空间的 \*-列剩余，分配的总空间可能会过大。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-109">If there are no \*-columns left to allocate, the total allocation will be too large.</span></span>

1. <span data-ttu-id="6e3ed-110">向列分配的总空间可能会占不满网格宽度。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-110">Total allocation can fall short of the Grid's width.</span></span> <span data-ttu-id="6e3ed-111">这是第 1 个问题的对偶问题，当向比例份额大于其大小上限的列分配空间，没有剩余的 \*-列来收紧空间时，可能会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-111">This is the dual problem to #1, arising when allocating to a column whose proportional share is greater than its maximum size, with no \*-columns left to take up the slack.</span></span>

1. <span data-ttu-id="6e3ed-112">可能会向两个 \*-列分配与其 *-权重不成比例的空间。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-112">Two \*-columns can receive allocations not proportional to their -weights.</span></span> <span data-ttu-id="6e3ed-113">这是第 1 个/第 2 个问题造成的较为温和的影响，当依序向 *-列 A、B 和 C 分配空间，但 B 列的比例份额与约束下限（或上限）冲突时，可能会出现这种问题。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-113">This is a milder version of #1/#2, arising when allocating to *-columns A, B, and C (in that order), where B's proportional share violates its min (or max) constraint.</span></span> <span data-ttu-id="6e3ed-114">同样，这会更改 C 列的可用空间，它将比 A 列获得更少（或更多）的按比例分配空间。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-114">As above, this changes the space available to column C, who gets less (or more) proportional allocation than A did,</span></span>

1. <span data-ttu-id="6e3ed-115">权重极大 (> 10^298) 的列全都被视为具有权重 10^298。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-115">Columns with extremely large weights (> 10^298) are all treated as if they had weight 10^298.</span></span> <span data-ttu-id="6e3ed-116">这些列（以及权重略小的列）之间的比例差异将不会生效。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-116">Proportional differences between them (and between columns with slightly smaller weights) are not honored.</span></span>

1. <span data-ttu-id="6e3ed-117">无法正确处理权重无穷大的列。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-117">Columns with infinite weights are not handled correctly.</span></span> <span data-ttu-id="6e3ed-118">[实际上，不能设置无穷大的权重，但这是一项人为限制。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-118">[Actually you can't set a weight to Infinity, but this is an artificial restriction.</span></span> <span data-ttu-id="6e3ed-119">空间分配代码是在努力处理这样的列，但处理得并不好。]</span><span class="sxs-lookup"><span data-stu-id="6e3ed-119">The allocation code was trying to handle it, but doing a bad job.]</span></span>

1. <span data-ttu-id="6e3ed-120">在避免溢出、下溢、精度损失和类似浮点问题时，存在一些小问题。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-120">Several minor problems while avoiding overflow, underflow, loss of precision and similar floating-point issues.</span></span>

1. <span data-ttu-id="6e3ed-121">在 DPI 足够高的情况下，无法正确调整布局的圆化处理。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-121">Adjustments for layout rounding are incorrect at sufficiently high DPI.</span></span>

<span data-ttu-id="6e3ed-122">新算法生成符合以下条件的结果：</span><span class="sxs-lookup"><span data-stu-id="6e3ed-122">The new algorithm produces results that meet the following criteria:</span></span>

<span data-ttu-id="6e3ed-123">答：</span><span class="sxs-lookup"><span data-stu-id="6e3ed-123">A.</span></span> <span data-ttu-id="6e3ed-124">分配给 *-列的实际宽度永远不会小于其最小宽度，也不会大于其最大宽度。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-124">The actual width assigned to a *-column is never less than its minimum width nor greater than its maximum width.</span></span>

<span data-ttu-id="6e3ed-125">B.</span><span class="sxs-lookup"><span data-stu-id="6e3ed-125">B.</span></span> <span data-ttu-id="6e3ed-126">对于没有分配最小或最大宽度的每个 *-列，向其分配与其 *-权重成比例的宽度。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-126">Each -column that is not assigned its minimum or maximum width is assigned a width proportional to its -weight.</span></span> <span data-ttu-id="6e3ed-127">确切地讲，如果分别使用宽度 x 和 y 声明两个列，且没有向这两个列分配最小或最大宽度，那么将按同一比例向这两个列分配实际宽度 v 和 w：v / w == x / y。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-127">To be precise, if two columns are declared with width x and y respectively, and if neither column receives its minimum or maximum width, the actual widths v and w assigned to the columns are in the same proportion: v / w == x / y.</span></span>

<span data-ttu-id="6e3ed-128">C.</span><span class="sxs-lookup"><span data-stu-id="6e3ed-128">C.</span></span> <span data-ttu-id="6e3ed-129">分配给“成比例的”\*-列的总宽度等于分配给受约束列（向其分配了最小或最大宽度的固定、自动和 \*-列）后剩余的可用空间。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-129">The total width allocated to "proportional" \*-columns is equal to the space available after allocating to the constrained columns (fixed, auto, and \*-columns that are allocated their min or max width).</span></span> <span data-ttu-id="6e3ed-130">此空间可能为零（例如，当最小宽度的总和超过了网格的可用宽度时）。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-130">This might be zero, for instance if the sum of the minimum widths exceeds the Grid's availbable width.</span></span>

<span data-ttu-id="6e3ed-131">D.</span><span class="sxs-lookup"><span data-stu-id="6e3ed-131">D.</span></span> <span data-ttu-id="6e3ed-132">所有这些语句都是针对“理想”布局进行解释的。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-132">All these statements are to be interpreted with respect to the "ideal" layout.</span></span> <span data-ttu-id="6e3ed-133">当布局圆化处理有效时，实际宽度与理想宽度可能会相差一个像素。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-133">When layout rounding is in effect, the actual widths can differ from the ideal widths by as much as one pixel.</span></span>

<span data-ttu-id="6e3ed-134">旧算法只遵循了 (A)，并未遵循上面所述情况中的其他条件。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-134">The old algorithm honored (A) but failed to honor the other criteria in the cases outlined above.</span></span>

<span data-ttu-id="6e3ed-135">本主题中有关列和宽度的一切介绍同样也适用于行和高度。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-135">Everything said about columns and widths in this topic applies as well to rows and heights.</span></span>

## <a name="impact"></a><span data-ttu-id="6e3ed-136">影响</span><span class="sxs-lookup"><span data-stu-id="6e3ed-136">Impact</span></span>

<span data-ttu-id="6e3ed-137">新算法在以下许多情况下会更改分配给 \*-列的实际宽度：</span><span class="sxs-lookup"><span data-stu-id="6e3ed-137">The new algorithm changes the actual width assigned to \*-columns in a number of cases:</span></span>

- <span data-ttu-id="6e3ed-138">当一个或多个 \*-列的最小或最大宽度替代相应列的按比例分配空间时。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-138">When one or more \*-columns also have a minimum or maximum width that overrides the proportional allocation for that column.</span></span> <span data-ttu-id="6e3ed-139">（最小宽度可以派生自显式声明 <xref:System.Windows.FrameworkElement.MinWidth%2A>，也可以派生自从列内容中获取的隐式最小值。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-139">(The minimum width can derive from an explicit <xref:System.Windows.FrameworkElement.MinWidth%2A> declaration, or from an implicit minimum obtained from the column's content.</span></span> <span data-ttu-id="6e3ed-140">只能通过 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 声明显式定义最大宽度。）</span><span class="sxs-lookup"><span data-stu-id="6e3ed-140">The maximum width can only be defined explicitly, from a <xref:System.Windows.FrameworkElement.MaxWidth%2A> declaration.)</span></span>

- <span data-ttu-id="6e3ed-141">当一个或多个 \*-列声明极大 \*-权重时（即大于 10^298）。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-141">When one or more \*-columns declare an extremely large \*-weight, greater than 10^298.</span></span>

- <span data-ttu-id="6e3ed-142">当 \*-权重明显不同，遇到了浮点不稳定问题（溢出、下溢、精度损失）时。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-142">When the \*-weights are sufficiently different to encounter floating-point instability (overflow, underflow, loss of precision).</span></span>

- <span data-ttu-id="6e3ed-143">当布局圆化处理已启用且有效显示 DPI 足够高时。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-143">When layout rounding is enabled, and the effective display DPI is sufficiently high.</span></span>

<span data-ttu-id="6e3ed-144">在前两种情况下，新旧算法生成的宽度明显不同；在最后一种情况下，新旧算法生成的宽度最多相差一或两个像素。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-144">In the first two cases, the widths produced by the new algorithm can be significantly different from those produced by the old algorithm; in the last case, the difference will be at most one or two pixels.</span></span>

## <a name="mitigation"></a><span data-ttu-id="6e3ed-145">缓解操作</span><span class="sxs-lookup"><span data-stu-id="6e3ed-145">Mitigation</span></span>

<span data-ttu-id="6e3ed-146">默认情况下，定位 .NET framework 4.7 及更高版本的应用程序将使用新算法，而定位 .NET Framework 4.6.2 或更低版本的应用程序将使用旧算法。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-146">By default, apps that target versions of the .NET Framework starting with the .NET Framework 4.7 will use the new algorithm, while apps that target the .NET Framework 4.6.2 or earlier versions will use the old algorithm.</span></span>

<span data-ttu-id="6e3ed-147">若要替代默认设置，请使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="6e3ed-147">To override the default, use the following configuration setting:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

<span data-ttu-id="6e3ed-148">值为“true”表示选择旧算法，值为“false”表示选择新算法。</span><span class="sxs-lookup"><span data-stu-id="6e3ed-148">The value 'true' selects the old algorithm, and 'false' selects the new algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e3ed-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e3ed-149">See also</span></span>
[<span data-ttu-id="6e3ed-150">.NET Framework 4.7 中的重定目标更改</span><span class="sxs-lookup"><span data-stu-id="6e3ed-150">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

