---
title: 如何：将主-详细模式与分层数据结合使用
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e0bbb24b07fdc1c362e2be43d69d189defbc27a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931882"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="2b287-102">如何：将主-详细模式与分层数据结合使用</span><span class="sxs-lookup"><span data-stu-id="2b287-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="2b287-103">此示例演示如何实现母版-详细信息方案。</span><span class="sxs-lookup"><span data-stu-id="2b287-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b287-104">示例</span><span class="sxs-lookup"><span data-stu-id="2b287-104">Example</span></span>  
 <span data-ttu-id="2b287-105">在此示例中，`LeagueList` 是 `Leagues` 的集合。</span><span class="sxs-lookup"><span data-stu-id="2b287-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="2b287-106">每个 `League` 有一个 `Name` 和一个 `Divisions` 的集合，每个 `Division` 有一个名称和一个 `Teams` 的集合。</span><span class="sxs-lookup"><span data-stu-id="2b287-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="2b287-107">每个 `Team` 有一个团队名称。</span><span class="sxs-lookup"><span data-stu-id="2b287-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="2b287-108">下面是该示例的一个屏幕快照。</span><span class="sxs-lookup"><span data-stu-id="2b287-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="2b287-109">`Divisions` 列表框<xref:System.Windows.Controls.ListBox>自动跟踪 `Leagues` 列表框<xref:System.Windows.Controls.ListBox>中的选择并显示相应的数据。</span><span class="sxs-lookup"><span data-stu-id="2b287-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="2b287-110">`Teams` 列表框<xref:System.Windows.Controls.ListBox>跟踪其他两个列表框<xref:System.Windows.Controls.ListBox>控件中的选择。</span><span class="sxs-lookup"><span data-stu-id="2b287-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![显示一个母版的屏幕截图&#45;详细信息方案示例。](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="2b287-112">在此示例中，有两点需要注意：</span><span class="sxs-lookup"><span data-stu-id="2b287-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="2b287-113">这三个 <xref:System.Windows.Controls.ListBox> 控件绑定到相同的源。</span><span class="sxs-lookup"><span data-stu-id="2b287-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="2b287-114">需设置绑定的 <xref:System.Windows.Data.Binding.Path%2A> 属性，用于指定 <xref:System.Windows.Controls.ListBox> 显示哪个级别的数据。</span><span class="sxs-lookup"><span data-stu-id="2b287-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="2b287-115">对于要跟踪其选择内容的 <xref:System.Windows.Controls.ListBox> 控件, 须将其 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2b287-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="2b287-116">设置此属性可确保所选的项始终设置为 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。</span><span class="sxs-lookup"><span data-stu-id="2b287-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="2b287-117">或者，如果 <xref:System.Windows.Controls.ListBox> 从 <xref:System.Windows.Data.CollectionViewSource> 获取数据，它会自动同步所选内容和货币。</span><span class="sxs-lookup"><span data-stu-id="2b287-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="2b287-118">使用[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据时，采用的方法略有不同。</span><span class="sxs-lookup"><span data-stu-id="2b287-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="2b287-119">有关示例，请参阅[对分层 XML 数据使用主-从模式](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2b287-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b287-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b287-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="2b287-121">绑定到集合并根据选择的内容显示信息</span><span class="sxs-lookup"><span data-stu-id="2b287-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="2b287-122">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="2b287-122">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="2b287-123">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="2b287-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="2b287-124">帮助主题</span><span class="sxs-lookup"><span data-stu-id="2b287-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
