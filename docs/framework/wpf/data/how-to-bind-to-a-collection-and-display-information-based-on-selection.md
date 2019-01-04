---
title: 如何：绑定到集合并基于选择显示信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 154f4b9b6024d064e73d64c44e2398a5da47052c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557402"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="bbc2e-102">如何：绑定到集合并基于选择显示信息</span><span class="sxs-lookup"><span data-stu-id="bbc2e-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="bbc2e-103">在简单的主 / 从方案中，具有数据绑定<xref:System.Windows.Controls.ItemsControl>如<xref:System.Windows.Controls.ListBox>。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="bbc2e-104">基于用户选择，显示有关选定项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="bbc2e-105">此示例演示如何实现这种情况。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbc2e-106">示例</span><span class="sxs-lookup"><span data-stu-id="bbc2e-106">Example</span></span>  
 <span data-ttu-id="bbc2e-107">在此示例中，`People` 是 `Person` 类的 <xref:System.Collections.ObjectModel.ObservableCollection%601>。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="bbc2e-108">`Person` 类包含三个属性：`FirstName`、`LastName` 和 `HomeTown`，类型均为 `string`。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="bbc2e-109"><xref:System.Windows.Controls.ContentControl> 使用以下 <xref:System.Windows.DataTemplate>，它定义了 `Person` 信息的显示方式：</span><span class="sxs-lookup"><span data-stu-id="bbc2e-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="bbc2e-110">以下是该示例生成的屏幕快照。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="bbc2e-111"><xref:System.Windows.Controls.ContentControl> 显示选中人员的其他属性。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="bbc2e-112">![绑定到集合](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="bbc2e-112">![Binding to a collection](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="bbc2e-113">在此示例中，需要注意两个事项：</span><span class="sxs-lookup"><span data-stu-id="bbc2e-113">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="bbc2e-114"><xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.ContentControl> 将绑定到相同的源。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="bbc2e-115">两个绑定的 <xref:System.Windows.Data.Binding.Path%2A> 属性都没有指定，因为这两个控件都绑定到整个集合对象。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2.  <span data-ttu-id="bbc2e-116">必须将 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 属性设置为 `true` 才能使其生效。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="bbc2e-117">设置此属性可确保所选的项始终设置为 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="bbc2e-118">或者，如果 <xref:System.Windows.Controls.ListBox> 从 <xref:System.Windows.Data.CollectionViewSource> 获取数据，它将自动同步所选内容和货币。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="bbc2e-119">需要注意，`Person` 类将按以下方式重写 `ToString` 方法。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="bbc2e-120">默认情况下，<xref:System.Windows.Controls.ListBox> 会调用 `ToString` 并以字符串形式显示绑定集合中的每个对象。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="bbc2e-121">这就是每个 `Person` 在 <xref:System.Windows.Controls.ListBox> 中显示为名字的原因。</span><span class="sxs-lookup"><span data-stu-id="bbc2e-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="bbc2e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbc2e-122">See Also</span></span>  
 [<span data-ttu-id="bbc2e-123">将主-详细模式与分层数据结合使用</span><span class="sxs-lookup"><span data-stu-id="bbc2e-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [<span data-ttu-id="bbc2e-124">将主-详细模式与分层 XML 数据结合使用</span><span class="sxs-lookup"><span data-stu-id="bbc2e-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [<span data-ttu-id="bbc2e-125">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="bbc2e-125">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="bbc2e-126">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="bbc2e-126">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="bbc2e-127">帮助主题</span><span class="sxs-lookup"><span data-stu-id="bbc2e-127">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
