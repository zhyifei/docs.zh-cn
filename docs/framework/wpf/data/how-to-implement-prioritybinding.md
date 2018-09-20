---
title: 如何：实现 PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: a7729ec3d06ec701cf2194bed5d90b5bed76573a
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46490700"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="c3778-102">如何：实现 PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="c3778-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="c3778-103"><xref:System.Windows.Data.PriorityBinding> 在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]的工作原理是指定的绑定的列表。</span><span class="sxs-lookup"><span data-stu-id="c3778-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="c3778-104">绑定的列表按从最高优先级到最低优先级排序。</span><span class="sxs-lookup"><span data-stu-id="c3778-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="c3778-105">如果最高优先级绑定返回一个值成功时对其进行处理然后则永远不需要处理列表中的其他绑定。</span><span class="sxs-lookup"><span data-stu-id="c3778-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="c3778-106">这是最高优先级的绑定需要很长的时间要计算的情况下，将使用成功返回值的下一步最高优先级，直到较高优先级的绑定会成功返回一个值。</span><span class="sxs-lookup"><span data-stu-id="c3778-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3778-107">示例</span><span class="sxs-lookup"><span data-stu-id="c3778-107">Example</span></span>  
 <span data-ttu-id="c3778-108">若要演示如何<xref:System.Windows.Data.PriorityBinding>的工作原理，`AsyncDataSource`对象已创建具有以下三个属性： `FastDP`， `SlowerDP`，和`SlowestDP`。</span><span class="sxs-lookup"><span data-stu-id="c3778-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="c3778-109">Get 访问器的`FastDP`返回的值`_fastDP`数据成员。</span><span class="sxs-lookup"><span data-stu-id="c3778-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="c3778-110">Get 访问器的`SlowerDP`等待返回的值之前的 3 秒`_slowerDP`数据成员。</span><span class="sxs-lookup"><span data-stu-id="c3778-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="c3778-111">Get 访问器的`SlowestDP`等待 5 秒钟之后返回的值`_slowestDP`数据成员。</span><span class="sxs-lookup"><span data-stu-id="c3778-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3778-112">此示例只为了方便本文演示。</span><span class="sxs-lookup"><span data-stu-id="c3778-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="c3778-113">[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]准则不建议将定义所数量级字段集相比，速度较慢的属性。</span><span class="sxs-lookup"><span data-stu-id="c3778-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="c3778-114">有关详细信息，请参阅[NIB： 选择属性和方法](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af)。</span><span class="sxs-lookup"><span data-stu-id="c3778-114">For more information, see [NIB: Choosing Between Properties and Methods](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af).</span></span>  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="c3778-115"><xref:System.Windows.Controls.TextBlock.Text%2A>属性绑定到上述`AsyncDS`使用<xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="c3778-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="c3778-116">当处理绑定引擎<xref:System.Windows.Data.Binding>对象，它与第一个启动<xref:System.Windows.Data.Binding>，后者已绑定到`SlowestDP`属性。</span><span class="sxs-lookup"><span data-stu-id="c3778-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="c3778-117">当这<xref:System.Windows.Data.Binding>是处理，它不返回一个值成功因为它处于睡眠状态 5 秒钟，因此下一步<xref:System.Windows.Data.Binding>处理元素。</span><span class="sxs-lookup"><span data-stu-id="c3778-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="c3778-118">下一步<xref:System.Windows.Data.Binding>不返回值成功因为等待 3 秒。</span><span class="sxs-lookup"><span data-stu-id="c3778-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="c3778-119">绑定引擎随后会转至下一步<xref:System.Windows.Data.Binding>元素，它绑定到`FastDP`属性。</span><span class="sxs-lookup"><span data-stu-id="c3778-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="c3778-120">这<xref:System.Windows.Data.Binding>返回"快速值"的值。</span><span class="sxs-lookup"><span data-stu-id="c3778-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="c3778-121"><xref:System.Windows.Controls.TextBlock>现在将显示"快速值"的值。</span><span class="sxs-lookup"><span data-stu-id="c3778-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="c3778-122">3 秒结束后`SlowerDP`属性返回的值"慢值"。</span><span class="sxs-lookup"><span data-stu-id="c3778-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="c3778-123"><xref:System.Windows.Controls.TextBlock>然后显示"慢 Value"的值。</span><span class="sxs-lookup"><span data-stu-id="c3778-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="c3778-124">在 5 秒结束后`SlowestDP`属性返回的值"最慢值"。</span><span class="sxs-lookup"><span data-stu-id="c3778-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="c3778-125">该绑定具有最高优先级，因为首先列出。</span><span class="sxs-lookup"><span data-stu-id="c3778-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="c3778-126"><xref:System.Windows.Controls.TextBlock>现在将显示"最慢 Value"的值。</span><span class="sxs-lookup"><span data-stu-id="c3778-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="c3778-127">请参阅<xref:System.Windows.Data.PriorityBinding>有关被视为成功的返回值从绑定信息。</span><span class="sxs-lookup"><span data-stu-id="c3778-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3778-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3778-128">See Also</span></span>  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c3778-129">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="c3778-129">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="c3778-130">帮助主题</span><span class="sxs-lookup"><span data-stu-id="c3778-130">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
