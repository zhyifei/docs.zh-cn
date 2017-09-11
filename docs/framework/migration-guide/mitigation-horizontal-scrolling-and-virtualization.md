---
title: "缓解：水平滚动和虚拟化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5bafd9b-a3b3-4f92-8241-2aad254fb1a9
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40eaf185e9c0c60493e9a2e5428c58b7463789fe
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-horizontal-scrolling-and-virtualization"></a><span data-ttu-id="681a4-102">缓解：水平滚动和虚拟化</span><span class="sxs-lookup"><span data-stu-id="681a4-102">Mitigation: Horizontal Scrolling and Virtualization</span></span>
<span data-ttu-id="681a4-103">此更改适用于按与主滚动方向正交的方向自行执行虚拟化的 <xref:System.Windows.Controls.ItemsControl>。</span><span class="sxs-lookup"><span data-stu-id="681a4-103">This change applies to an <xref:System.Windows.Controls.ItemsControl> that does its own virtualization in the direction orthogonal to the main scrolling direction.</span></span> <span data-ttu-id="681a4-104">（主要示例是 <xref:System.Windows.Controls.DataGrid> 控件，其 <xref:System.Windows.Controls.DataGrid.EnableColumnVirtualization%2A> 设置为 `true`。）已将特定水平滚动操作更改为生成更直观且更类似于可类比垂直滚动操作的结果。</span><span class="sxs-lookup"><span data-stu-id="681a4-104">(The chief  example is a <xref:System.Windows.Controls.DataGrid> control with <xref:System.Windows.Controls.DataGrid.EnableColumnVirtualization%2A> set to `true`.)  The outcome of certain  horizontal scrolling operations has been changed to produce results that are more intuitive and more analogous to the results of comparable vertical operations.</span></span>  <span data-ttu-id="681a4-105">具体操作包括“滚动到此处”和“滚动到右边缘”（使用右键单击水平滚动条所获得的菜单中的名称）。</span><span class="sxs-lookup"><span data-stu-id="681a4-105">The specific operations include **Scroll Here** and **Right Edge**, to use the names from the menu obtained by right-clicking a horizontal scrollbar.</span></span>  <span data-ttu-id="681a4-106">这两种方法都能计算候选偏移和调用 <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="681a4-106">Both of these compute a  candidate offset and call <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>.</span></span>  <span data-ttu-id="681a4-107">滚动到新偏移后，“滚动到此处”或“滚动到右边缘”的定义可能会发生变化，因为反虚拟化的新内容已更改 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A?displayProperty=fullName> 的值。</span><span class="sxs-lookup"><span data-stu-id="681a4-107">After scrolling to the new offset, the definition of "here" or "right edge" may have changed because newly de-virtualized content has changed the value of <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A?displayProperty=fullName>.</span></span>  
  
## <a name="description-of-the-change"></a><span data-ttu-id="681a4-108">更改说明</span><span class="sxs-lookup"><span data-stu-id="681a4-108">Description of the change</span></span>  
 <span data-ttu-id="681a4-109">在低于 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的版本中，滚动操作仅使用候选偏移，即使不再位于“此处”或“右边缘”，也不例外。</span><span class="sxs-lookup"><span data-stu-id="681a4-109">Prior to the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the scroll operation simply uses the candidate offset, even though it may not be "here" or at the "right edge" any more.</span></span>  <span data-ttu-id="681a4-110">这会导致滚动翻阅出现“退回”等效果，最好是用举例来说明。</span><span class="sxs-lookup"><span data-stu-id="681a4-110">This results in effects like "bouncing" the scroll thumb, best illustrated by example.</span></span>  <span data-ttu-id="681a4-111">假设 <xref:System.Windows.Controls.DataGrid> 控件具有设置为 1000 的 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> 和设置为 200 的 <xref:System.Windows.FrameworkElement.Width%2A>。</span><span class="sxs-lookup"><span data-stu-id="681a4-111">Suppose a <xref:System.Windows.Controls.DataGrid> control has <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> set to 1000 and <xref:System.Windows.FrameworkElement.Width%2A> set to 200.</span></span>  <span data-ttu-id="681a4-112">“滚动到右边缘”使用候选偏移 1000 - 200 = 800。</span><span class="sxs-lookup"><span data-stu-id="681a4-112">A scroll to "Right Edge" uses candidate offset  1000 - 200 = 800.</span></span>  <span data-ttu-id="681a4-113">在滚动到此偏移时，新列会进行反虚拟化；假设这些列都非常宽，这样就可以将 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> 更改为 2000。</span><span class="sxs-lookup"><span data-stu-id="681a4-113">While scrolling to that offset, new columns are de-virtualized; let's suppose they are very wide, so that the <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> changes to 2000.</span></span>  <span data-ttu-id="681a4-114">滚动偏移最终为 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A>=800，而翻阅“退回”到滚动条中间位置附近，精确位置是 800/2000 = 40%。</span><span class="sxs-lookup"><span data-stu-id="681a4-114">The scroll ends with <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A>=800, and the thumb "bounces" back to near the middle of the scrollbar -- precisely at 800/2000 = 40%.</span></span>  
  
 <span data-ttu-id="681a4-115">自 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 起，如果发生这种情况，将重新计算新的候选偏移。</span><span class="sxs-lookup"><span data-stu-id="681a4-115">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a new candidate offset is recomputed when this situation occurs.</span></span> <span data-ttu-id="681a4-116">（垂直滚动已采用这样的做法。）</span><span class="sxs-lookup"><span data-stu-id="681a4-116">(This is how vertical scrolling works already.)</span></span>  
  
## <a name="impact"></a><span data-ttu-id="681a4-117">影响</span><span class="sxs-lookup"><span data-stu-id="681a4-117">Impact</span></span>  
 <span data-ttu-id="681a4-118">此更改为最终用户提供了更易于预测的直观体验，但还可能会影响依赖水平滚动后的 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> 确切值的所有应用，不论水平滚动是由最终用户触发，还是由显式调用 <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName> 所触发。</span><span class="sxs-lookup"><span data-stu-id="681a4-118">The change produces a more predictable and intuitive experience for the end user, but it could also affect any app that depends on the exact value of <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> after a horizontal scroll, whether invoked by the end user or by an explicit call to <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="681a4-119">缓解操作</span><span class="sxs-lookup"><span data-stu-id="681a4-119">Mitigation</span></span>  
 <span data-ttu-id="681a4-120">应将使用 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> 预测值的应用更改为：在由于反虚拟化而可能更改 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> 的任何水平滚动发生后检索实际值（和 <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> 值）。</span><span class="sxs-lookup"><span data-stu-id="681a4-120">An app that uses a predicted value for <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> should be changed to retrieve the actual value (and the value of <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A>) after any horizontal scroll that could change <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> due to de-virtualization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="681a4-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="681a4-121">See Also</span></span>  
 [<span data-ttu-id="681a4-122">运行时更改</span><span class="sxs-lookup"><span data-stu-id="681a4-122">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)

