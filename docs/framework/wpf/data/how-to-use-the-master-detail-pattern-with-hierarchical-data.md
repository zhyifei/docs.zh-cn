---
title: "如何：对分层数据使用主-从模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb546a3429012a49ee7652a3470460935fc76d70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="7b925-102">如何：对分层数据使用主-从模式</span><span class="sxs-lookup"><span data-stu-id="7b925-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="7b925-103">此示例演示如何实现主 / 从方案。</span><span class="sxs-lookup"><span data-stu-id="7b925-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b925-104">示例</span><span class="sxs-lookup"><span data-stu-id="7b925-104">Example</span></span>  
 <span data-ttu-id="7b925-105">在此示例中，`LeagueList`是一套`Leagues`。</span><span class="sxs-lookup"><span data-stu-id="7b925-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="7b925-106">每个`League`具有`Name`和一系列`Divisions`，和每个`Division`有一个名称和一套`Teams`。</span><span class="sxs-lookup"><span data-stu-id="7b925-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="7b925-107">每个`Team`有一个团队名称。</span><span class="sxs-lookup"><span data-stu-id="7b925-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="7b925-108">下面是该示例的一个屏幕快照。</span><span class="sxs-lookup"><span data-stu-id="7b925-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="7b925-109">`Divisions` <xref:System.Windows.Controls.ListBox>自动跟踪中的选择`Leagues`<xref:System.Windows.Controls.ListBox>并显示相应的数据。</span><span class="sxs-lookup"><span data-stu-id="7b925-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="7b925-110">`Teams` <xref:System.Windows.Controls.ListBox>跟踪中与其他两个选项<xref:System.Windows.Controls.ListBox>控件。</span><span class="sxs-lookup"><span data-stu-id="7b925-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 <span data-ttu-id="7b925-111">![Master &#45; 详细信息示例](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span><span class="sxs-lookup"><span data-stu-id="7b925-111">![Master&#45;detail example](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span></span>  
  
 <span data-ttu-id="7b925-112">需要注意，在此示例中，两个的事项为：</span><span class="sxs-lookup"><span data-stu-id="7b925-112">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="7b925-113">这三种<xref:System.Windows.Controls.ListBox>的控件绑定到相同的源。</span><span class="sxs-lookup"><span data-stu-id="7b925-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="7b925-114">你设置<xref:System.Windows.Data.Binding.Path%2A>要指定所需的数据级别的绑定属性<xref:System.Windows.Controls.ListBox>以显示。</span><span class="sxs-lookup"><span data-stu-id="7b925-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2.  <span data-ttu-id="7b925-115">必须设置<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>属性`true`上<xref:System.Windows.Controls.ListBox>种控件跟踪所做的选择。</span><span class="sxs-lookup"><span data-stu-id="7b925-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="7b925-116">将设置此属性可确保所选的项始终设置为<xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。</span><span class="sxs-lookup"><span data-stu-id="7b925-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="7b925-117">或者，如果<xref:System.Windows.Controls.ListBox>获取它从数据<xref:System.Windows.Data.CollectionViewSource>，它自动同步所选内容和货币。</span><span class="sxs-lookup"><span data-stu-id="7b925-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="7b925-118">这种方法是略有不同，当你使用[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据。</span><span class="sxs-lookup"><span data-stu-id="7b925-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="7b925-119">有关示例，请参阅[对层次结构的 XML 数据使用主-详细信息模式](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)。</span><span class="sxs-lookup"><span data-stu-id="7b925-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b925-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b925-120">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="7b925-121">绑定到集合并根据选择的内容显示信息</span><span class="sxs-lookup"><span data-stu-id="7b925-121">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="7b925-122">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="7b925-122">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="7b925-123">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="7b925-123">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="7b925-124">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="7b925-124">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
