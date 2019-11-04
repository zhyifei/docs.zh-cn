---
title: 如何：对分层数据使用主-从模式
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 2e7d9ceed3ab8385f07d87ecdb92c0a99d410b40
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459077"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="0de23-102">如何：对分层数据使用主-从模式</span><span class="sxs-lookup"><span data-stu-id="0de23-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="0de23-103">此示例演示如何实现主-从方案。</span><span class="sxs-lookup"><span data-stu-id="0de23-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0de23-104">示例</span><span class="sxs-lookup"><span data-stu-id="0de23-104">Example</span></span>  
 <span data-ttu-id="0de23-105">在此示例中，`LeagueList` 是 `Leagues`的集合。</span><span class="sxs-lookup"><span data-stu-id="0de23-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="0de23-106">每个 `League` 都有一个 `Name` 和一个 `Divisions`集合，每个 `Division` 都有一个名称和 `Teams`的集合。</span><span class="sxs-lookup"><span data-stu-id="0de23-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="0de23-107">每个 `Team` 都有一个团队名称。</span><span class="sxs-lookup"><span data-stu-id="0de23-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="0de23-108">下面是该示例的一个屏幕快照。</span><span class="sxs-lookup"><span data-stu-id="0de23-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="0de23-109">`Divisions` <xref:System.Windows.Controls.ListBox> 会自动跟踪 `Leagues` <xref:System.Windows.Controls.ListBox> 中的选定内容，并显示相应的数据。</span><span class="sxs-lookup"><span data-stu-id="0de23-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="0de23-110">`Teams` <xref:System.Windows.Controls.ListBox> 跟踪其他两个 <xref:System.Windows.Controls.ListBox> 控件中的选定内容。</span><span class="sxs-lookup"><span data-stu-id="0de23-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![显示主&#45;详细方案示例的屏幕截图。](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="0de23-112">在此示例中，需要注意以下两个事项：</span><span class="sxs-lookup"><span data-stu-id="0de23-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="0de23-113">这三个 <xref:System.Windows.Controls.ListBox> 控件绑定到同一个源。</span><span class="sxs-lookup"><span data-stu-id="0de23-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="0de23-114">可以设置绑定的 <xref:System.Windows.Data.Binding.Path%2A> 属性，以指定希望 <xref:System.Windows.Controls.ListBox> 显示哪一级别的数据。</span><span class="sxs-lookup"><span data-stu-id="0de23-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="0de23-115">必须在要跟踪的选定内容的 <xref:System.Windows.Controls.ListBox> 控件上将 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0de23-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="0de23-116">设置此属性可确保选定项始终设置为 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。</span><span class="sxs-lookup"><span data-stu-id="0de23-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="0de23-117">或者，如果 <xref:System.Windows.Controls.ListBox> 从 <xref:System.Windows.Data.CollectionViewSource>中获取数据，则会自动同步选定内容和货币。</span><span class="sxs-lookup"><span data-stu-id="0de23-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="0de23-118">使用 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据时，此方法会略有不同。</span><span class="sxs-lookup"><span data-stu-id="0de23-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="0de23-119">有关示例，请参阅对[分层 XML 数据使用主-从模式](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0de23-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de23-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0de23-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="0de23-121">绑定到集合并根据选择的内容显示信息</span><span class="sxs-lookup"><span data-stu-id="0de23-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="0de23-122">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="0de23-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="0de23-123">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="0de23-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="0de23-124">帮助主题</span><span class="sxs-lookup"><span data-stu-id="0de23-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
