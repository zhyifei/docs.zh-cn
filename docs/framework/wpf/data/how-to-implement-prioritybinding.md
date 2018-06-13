---
title: 如何：实现 PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: cf0ed5c2b55358d3a583ac89e307b23b3ab08a9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557753"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="863ba-102">如何：实现 PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="863ba-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="863ba-103"><xref:System.Windows.Data.PriorityBinding> 在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]的工作原理是指定的绑定的列表。</span><span class="sxs-lookup"><span data-stu-id="863ba-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="863ba-104">绑定列表按优先级从高到最低优先级排序。</span><span class="sxs-lookup"><span data-stu-id="863ba-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="863ba-105">如果高优先级的绑定返回一个值成功处理时则永远不会需要处理其他列表中的绑定。</span><span class="sxs-lookup"><span data-stu-id="863ba-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="863ba-106">它可能是最高的优先级绑定需要很长的时间要进行求值的用例时，将使用成功返回一个值的下一步最高优先级，直到较高优先级的绑定成功返回一个值。</span><span class="sxs-lookup"><span data-stu-id="863ba-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="863ba-107">示例</span><span class="sxs-lookup"><span data-stu-id="863ba-107">Example</span></span>  
 <span data-ttu-id="863ba-108">为了演示如何<xref:System.Windows.Data.PriorityBinding>可以正常工作，`AsyncDataSource`对象已创建具有以下三个属性： `FastDP`， `SlowerDP`，和`SlowestDP`。</span><span class="sxs-lookup"><span data-stu-id="863ba-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="863ba-109">Get 访问器`FastDP`返回的值`_fastDP`数据成员。</span><span class="sxs-lookup"><span data-stu-id="863ba-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="863ba-110">Get 访问器`SlowerDP`等待 3 秒，然后返回的值`_slowerDP`数据成员。</span><span class="sxs-lookup"><span data-stu-id="863ba-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="863ba-111">Get 访问器`SlowestDP`等待 5 秒，然后返回的值`_slowestDP`数据成员。</span><span class="sxs-lookup"><span data-stu-id="863ba-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="863ba-112">此示例只为了方便本文演示。</span><span class="sxs-lookup"><span data-stu-id="863ba-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="863ba-113">[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]准则建议您定义个数量级慢于字段集的属性。</span><span class="sxs-lookup"><span data-stu-id="863ba-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="863ba-114">有关详细信息，请参阅[NIB： 选择之间属性和方法](http://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af)。</span><span class="sxs-lookup"><span data-stu-id="863ba-114">For more information, see [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af).</span></span>  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="863ba-115"><xref:System.Windows.Controls.TextBlock.Text%2A>属性将绑定到上述`AsyncDS`使用<xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="863ba-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="863ba-116">当处理绑定引擎<xref:System.Windows.Data.Binding>对象，它与第一个启动<xref:System.Windows.Data.Binding>，该元素绑定到`SlowestDP`属性。</span><span class="sxs-lookup"><span data-stu-id="863ba-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="863ba-117">当这<xref:System.Windows.Data.Binding>是处理，它不返回值成功因为它等待 5 秒，因此下一步<xref:System.Windows.Data.Binding>处理元素。</span><span class="sxs-lookup"><span data-stu-id="863ba-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="863ba-118">下一步<xref:System.Windows.Data.Binding>不返回值成功因为它等待 3 秒。</span><span class="sxs-lookup"><span data-stu-id="863ba-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="863ba-119">绑定引擎然后移到下一步<xref:System.Windows.Data.Binding>元素，它绑定到`FastDP`属性。</span><span class="sxs-lookup"><span data-stu-id="863ba-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="863ba-120">这<xref:System.Windows.Data.Binding>返回"快速 Value"的值。</span><span class="sxs-lookup"><span data-stu-id="863ba-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="863ba-121"><xref:System.Windows.Controls.TextBlock>现在显示"快速 Value"的值。</span><span class="sxs-lookup"><span data-stu-id="863ba-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="863ba-122">后 3 秒过后，`SlowerDP`属性返回的值"速度较慢值"。</span><span class="sxs-lookup"><span data-stu-id="863ba-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="863ba-123"><xref:System.Windows.Controls.TextBlock>然后显示值"速度较慢值"。</span><span class="sxs-lookup"><span data-stu-id="863ba-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="863ba-124">后 5 秒过后，`SlowestDP`属性返回的值"最慢的值"。</span><span class="sxs-lookup"><span data-stu-id="863ba-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="863ba-125">该绑定具有最高优先级，因为它会最先列出。</span><span class="sxs-lookup"><span data-stu-id="863ba-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="863ba-126"><xref:System.Windows.Controls.TextBlock>现在显示"最慢 Value"的值。</span><span class="sxs-lookup"><span data-stu-id="863ba-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="863ba-127">请参阅<xref:System.Windows.Data.PriorityBinding>有关什么被视为一个成功的返回值从绑定信息。</span><span class="sxs-lookup"><span data-stu-id="863ba-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="863ba-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="863ba-128">See Also</span></span>  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="863ba-129">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="863ba-129">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="863ba-130">帮助主题</span><span class="sxs-lookup"><span data-stu-id="863ba-130">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
