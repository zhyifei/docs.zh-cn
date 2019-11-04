---
title: 如何：实现 PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 343b0aca4736905f3a0cbff5a0f76b170da0c920
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459780"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="3dc56-102">如何：实现 PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="3dc56-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="3dc56-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的 <xref:System.Windows.Data.PriorityBinding> 通过指定绑定列表来实现。</span><span class="sxs-lookup"><span data-stu-id="3dc56-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="3dc56-104">绑定列表按从最高优先级到最低优先级的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="3dc56-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="3dc56-105">如果最高优先级绑定在处理时成功返回值，则永远不需要处理列表中的其他绑定。</span><span class="sxs-lookup"><span data-stu-id="3dc56-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="3dc56-106">这种情况可能是最高优先级的绑定需要很长的时间来计算，因此，在更高优先级的绑定成功返回值之前，将使用下一个最高优先级来成功返回值。</span><span class="sxs-lookup"><span data-stu-id="3dc56-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dc56-107">示例</span><span class="sxs-lookup"><span data-stu-id="3dc56-107">Example</span></span>  
 <span data-ttu-id="3dc56-108">为了演示 <xref:System.Windows.Data.PriorityBinding> 的工作方式，已使用以下三个属性创建了 `AsyncDataSource` 对象： "`FastDP`"、"`SlowerDP`" 和 "`SlowestDP`"。</span><span class="sxs-lookup"><span data-stu-id="3dc56-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="3dc56-109">`FastDP` 的 get 访问器返回 `_fastDP` 数据成员的值。</span><span class="sxs-lookup"><span data-stu-id="3dc56-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="3dc56-110">`SlowerDP` 的 get 访问器在返回 `_slowerDP` 数据成员的值之前等待3秒。</span><span class="sxs-lookup"><span data-stu-id="3dc56-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="3dc56-111">`SlowestDP` 的 get 访问器在返回 `_slowestDP` 数据成员的值之前等待5秒。</span><span class="sxs-lookup"><span data-stu-id="3dc56-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3dc56-112">此示例只为了方便本文演示。</span><span class="sxs-lookup"><span data-stu-id="3dc56-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="3dc56-113">.NET 指导原则建议不要定义比字段集慢的数量级顺序的属性。</span><span class="sxs-lookup"><span data-stu-id="3dc56-113">The .NET guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="3dc56-114">有关详细信息，请参阅[在属性和方法之间进行选择](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="3dc56-114">For more information, see [Choosing Between Properties and Methods](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="3dc56-115"><xref:System.Windows.Controls.TextBlock.Text%2A> 属性使用 <xref:System.Windows.Data.PriorityBinding>绑定到上述 `AsyncDS`：</span><span class="sxs-lookup"><span data-stu-id="3dc56-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="3dc56-116">当绑定引擎处理 <xref:System.Windows.Data.Binding> 对象时，它将从绑定到 `SlowestDP` 属性的第一个 <xref:System.Windows.Data.Binding>开始。</span><span class="sxs-lookup"><span data-stu-id="3dc56-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="3dc56-117">处理此 <xref:System.Windows.Data.Binding> 时，它不会成功返回值，因为它处于休眠状态5秒，因此处理下一个 <xref:System.Windows.Data.Binding> 元素。</span><span class="sxs-lookup"><span data-stu-id="3dc56-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="3dc56-118">接下来的 <xref:System.Windows.Data.Binding> 不会成功返回值，因为它处于休眠状态3秒。</span><span class="sxs-lookup"><span data-stu-id="3dc56-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="3dc56-119">然后，绑定引擎会移动到绑定到 `FastDP` 属性的下一个 <xref:System.Windows.Data.Binding> 元素。</span><span class="sxs-lookup"><span data-stu-id="3dc56-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="3dc56-120">此 <xref:System.Windows.Data.Binding> 返回值 "Fast Value"。</span><span class="sxs-lookup"><span data-stu-id="3dc56-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="3dc56-121">现在 <xref:System.Windows.Controls.TextBlock> 显示值 "Fast Value"。</span><span class="sxs-lookup"><span data-stu-id="3dc56-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="3dc56-122">3秒钟后，`SlowerDP` 属性返回值 "慢速值"。</span><span class="sxs-lookup"><span data-stu-id="3dc56-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="3dc56-123">然后 <xref:System.Windows.Controls.TextBlock> 显示值 "慢速值"。</span><span class="sxs-lookup"><span data-stu-id="3dc56-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="3dc56-124">超过5秒钟后，`SlowestDP` 属性返回值 "最慢的值"。</span><span class="sxs-lookup"><span data-stu-id="3dc56-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="3dc56-125">由于此绑定首先列出，因此具有最高优先级。</span><span class="sxs-lookup"><span data-stu-id="3dc56-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="3dc56-126">现在 <xref:System.Windows.Controls.TextBlock> 显示值 "最慢的值"。</span><span class="sxs-lookup"><span data-stu-id="3dc56-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="3dc56-127">请参阅 <xref:System.Windows.Data.PriorityBinding>，了解从绑定中被视为成功返回值的内容。</span><span class="sxs-lookup"><span data-stu-id="3dc56-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc56-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dc56-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3dc56-129">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="3dc56-129">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="3dc56-130">帮助主题</span><span class="sxs-lookup"><span data-stu-id="3dc56-130">How-to Topics</span></span>](data-binding-how-to-topics.md)
