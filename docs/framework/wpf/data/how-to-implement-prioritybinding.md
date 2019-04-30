---
title: 如何：实现 PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: aaf2caff1e2684e08c7eb65125536f1070203d70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020850"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="43be6-102">如何：实现 PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="43be6-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="43be6-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中 <xref:System.Windows.Data.PriorityBinding> 的工作方式是指定一个绑定列表。</span><span class="sxs-lookup"><span data-stu-id="43be6-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="43be6-104">列表中的绑定按优先级从高到低排序。</span><span class="sxs-lookup"><span data-stu-id="43be6-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="43be6-105">对最高优先级绑定进行处理时，如果成功返回一个值，就不再需要处理列表中的其他绑定。</span><span class="sxs-lookup"><span data-stu-id="43be6-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="43be6-106">在最高优先级绑定需要长时间计算的情况下，则会使用已成功返回值的下一个优先级最高的绑定，直到优先级更高的绑定成功返回值为止。</span><span class="sxs-lookup"><span data-stu-id="43be6-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43be6-107">示例</span><span class="sxs-lookup"><span data-stu-id="43be6-107">Example</span></span>  
 <span data-ttu-id="43be6-108">为了演示 <xref:System.Windows.Data.PriorityBinding> 的工作方式，我们创建了 `AsyncDataSource` 对象，该对象具有三个属性：`FastDP`、`SlowerDP` 和 `SlowestDP`。</span><span class="sxs-lookup"><span data-stu-id="43be6-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="43be6-109">`FastDP` 的 Get 访问器返回数据成员 `_fastDP` 的值。</span><span class="sxs-lookup"><span data-stu-id="43be6-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="43be6-110">`SlowerDP` 的 Get 访问器等待 3 秒后返回数据成员 `_slowerDP` 的值。</span><span class="sxs-lookup"><span data-stu-id="43be6-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="43be6-111">`SlowestDP` 的 Get 访问器等待 5 秒后返回数据成员 `_slowestDP` 的值。</span><span class="sxs-lookup"><span data-stu-id="43be6-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43be6-112">此示例仅供演示。</span><span class="sxs-lookup"><span data-stu-id="43be6-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="43be6-113">[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 准则不建议将比字段设置更慢的操作定义为属性。</span><span class="sxs-lookup"><span data-stu-id="43be6-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="43be6-114">有关详细信息，请参阅[选择属性和方法](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="43be6-114">For more information, see [Choosing Between Properties and Methods](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="43be6-115"><xref:System.Windows.Controls.TextBlock.Text%2A> 属性使用 <xref:System.Windows.Data.PriorityBinding> 绑定到上述 `AsyncDS`:</span><span class="sxs-lookup"><span data-stu-id="43be6-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="43be6-116">绑定引擎在处理 <xref:System.Windows.Data.Binding> 对象时，会从已绑定到 `SlowestDP` 属性的第一个 <xref:System.Windows.Data.Binding> 开始。</span><span class="sxs-lookup"><span data-stu-id="43be6-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="43be6-117">处理此 <xref:System.Windows.Data.Binding> 时并未成功返回值，因为它正处于 5 秒的睡眠状态，因此会开始处理下一个 <xref:System.Windows.Data.Binding> 元素。</span><span class="sxs-lookup"><span data-stu-id="43be6-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="43be6-118">该 <xref:System.Windows.Data.Binding> 也没有成功返回值，因为它正处于 3 秒的睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="43be6-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="43be6-119">绑定引擎随后会转至下一个 <xref:System.Windows.Data.Binding> 元素，该元素已绑定到 `FastDP` 属性。</span><span class="sxs-lookup"><span data-stu-id="43be6-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="43be6-120">该 <xref:System.Windows.Data.Binding> 会返回值“Fast Value”。</span><span class="sxs-lookup"><span data-stu-id="43be6-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="43be6-121">于是 <xref:System.Windows.Controls.TextBlock> 会显示值“Fast Value”。</span><span class="sxs-lookup"><span data-stu-id="43be6-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="43be6-122">3 秒后，`SlowerDP` 属性返回了值“Slower Value”。</span><span class="sxs-lookup"><span data-stu-id="43be6-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="43be6-123">于是 <xref:System.Windows.Controls.TextBlock> 会显示值“Slower Value”。</span><span class="sxs-lookup"><span data-stu-id="43be6-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="43be6-124">5 秒后，`SlowestDP` 属性返回了值“Slowest Value”。</span><span class="sxs-lookup"><span data-stu-id="43be6-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="43be6-125">该绑定第一个列出，因此具有最高优先级。</span><span class="sxs-lookup"><span data-stu-id="43be6-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="43be6-126">于是 <xref:System.Windows.Controls.TextBlock> 会显示值“Slowest Value”。</span><span class="sxs-lookup"><span data-stu-id="43be6-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="43be6-127">请参阅 <xref:System.Windows.Data.PriorityBinding>，了解“何为成功的绑定返回值” 相关信息。</span><span class="sxs-lookup"><span data-stu-id="43be6-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43be6-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="43be6-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="43be6-129">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="43be6-129">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="43be6-130">帮助主题</span><span class="sxs-lookup"><span data-stu-id="43be6-130">How-to Topics</span></span>](data-binding-how-to-topics.md)
