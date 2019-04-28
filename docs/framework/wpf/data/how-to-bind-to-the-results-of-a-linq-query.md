---
title: 如何：绑定到 LINQ 查询结果
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 5464ee9c59a7c99a83774a7535b9b3c422c1d2e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644407"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="a4bb6-102">如何：绑定到 LINQ 查询结果</span><span class="sxs-lookup"><span data-stu-id="a4bb6-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="a4bb6-103">此示例演示如何运行 LINQ 查询，然后绑定到结果。</span><span class="sxs-lookup"><span data-stu-id="a4bb6-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4bb6-104">示例</span><span class="sxs-lookup"><span data-stu-id="a4bb6-104">Example</span></span>  
 <span data-ttu-id="a4bb6-105">以下示例创建两个列表框。</span><span class="sxs-lookup"><span data-stu-id="a4bb6-105">The following example creates two list boxes.</span></span> <span data-ttu-id="a4bb6-106">第一个列表框包含三个列表项。</span><span class="sxs-lookup"><span data-stu-id="a4bb6-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="a4bb6-107">从第一个列表框中选择一项即可调用以下事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a4bb6-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="a4bb6-108">在此示例中，`Tasks` 是一系列 `Task` 对象。</span><span class="sxs-lookup"><span data-stu-id="a4bb6-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="a4bb6-109">`Task` 类有一个名为 `Priority` 的属性。</span><span class="sxs-lookup"><span data-stu-id="a4bb6-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="a4bb6-110">此事件处理程序会运行 LINQ 查询，返回具有所选优先级值的 `Task` 对象集合，然后将其设置为 <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="a4bb6-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="a4bb6-111">第二个列表框将绑定到该集合，因为其 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 值设置为 `{Binding}`。</span><span class="sxs-lookup"><span data-stu-id="a4bb6-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="a4bb6-112">因此，它将显示返回的集合（基于 `myTaskTemplate` <xref:System.Windows.DataTemplate>）。</span><span class="sxs-lookup"><span data-stu-id="a4bb6-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bb6-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4bb6-113">See also</span></span>

- [<span data-ttu-id="a4bb6-114">让数据可供 XAML 中的绑定使用</span><span class="sxs-lookup"><span data-stu-id="a4bb6-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="a4bb6-115">绑定到集合并根据选择的内容显示信息</span><span class="sxs-lookup"><span data-stu-id="a4bb6-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="a4bb6-116">WPF 版本 4.5 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="a4bb6-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="a4bb6-117">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="a4bb6-117">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="a4bb6-118">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a4bb6-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
