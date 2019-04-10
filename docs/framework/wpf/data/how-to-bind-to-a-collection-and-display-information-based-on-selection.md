---
title: 如何：绑定到集合并根据选择的内容显示信息
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
ms.openlocfilehash: bb7d4c89e63982a3052857dcb50d04d36d9517dd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314382"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="a83d6-102">如何：绑定到集合并根据选择的内容显示信息</span><span class="sxs-lookup"><span data-stu-id="a83d6-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="a83d6-103">在简单的母版-详细信息方案中，具有数据绑定<xref:System.Windows.Controls.ItemsControl>如<xref:System.Windows.Controls.ListBox>。</span><span class="sxs-lookup"><span data-stu-id="a83d6-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="a83d6-104">基于用户所选内容上，显示有关选定项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a83d6-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="a83d6-105">此示例演示如何实现此方案。</span><span class="sxs-lookup"><span data-stu-id="a83d6-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a83d6-106">示例</span><span class="sxs-lookup"><span data-stu-id="a83d6-106">Example</span></span>  
 <span data-ttu-id="a83d6-107">在此示例中，`People` 是 `Person` 类的 <xref:System.Collections.ObjectModel.ObservableCollection%601>。</span><span class="sxs-lookup"><span data-stu-id="a83d6-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="a83d6-108">`Person` 类包含三个属性：`FirstName`、`LastName` 和 `HomeTown`，类型均为 `string`。</span><span class="sxs-lookup"><span data-stu-id="a83d6-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="a83d6-109"><xref:System.Windows.Controls.ContentControl> 使用以下 <xref:System.Windows.DataTemplate>，它定义了 `Person` 信息的显示方式：</span><span class="sxs-lookup"><span data-stu-id="a83d6-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="a83d6-110">下面是该示例生成的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="a83d6-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="a83d6-111"><xref:System.Windows.Controls.ContentControl> 显示选中人员的其他属性。</span><span class="sxs-lookup"><span data-stu-id="a83d6-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="a83d6-112">![绑定到集合](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="a83d6-112">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="a83d6-113">在此示例中，需要注意两个事项：</span><span class="sxs-lookup"><span data-stu-id="a83d6-113">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="a83d6-114"><xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.ContentControl> 将绑定到相同的源。</span><span class="sxs-lookup"><span data-stu-id="a83d6-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="a83d6-115">两个绑定的 <xref:System.Windows.Data.Binding.Path%2A> 属性都没有指定，因为这两个控件都绑定到整个集合对象。</span><span class="sxs-lookup"><span data-stu-id="a83d6-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="a83d6-116">必须将 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 属性设置为 `true` 才能使其生效。</span><span class="sxs-lookup"><span data-stu-id="a83d6-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="a83d6-117">设置此属性可确保所选的项始终设置为 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。</span><span class="sxs-lookup"><span data-stu-id="a83d6-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="a83d6-118">或者，如果 <xref:System.Windows.Controls.ListBox> 从 <xref:System.Windows.Data.CollectionViewSource> 获取数据，它将自动同步所选内容和货币。</span><span class="sxs-lookup"><span data-stu-id="a83d6-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="a83d6-119">需要注意，`Person` 类将按以下方式重写 `ToString` 方法。</span><span class="sxs-lookup"><span data-stu-id="a83d6-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="a83d6-120">默认情况下，<xref:System.Windows.Controls.ListBox> 会调用 `ToString` 并以字符串形式显示绑定集合中的每个对象。</span><span class="sxs-lookup"><span data-stu-id="a83d6-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="a83d6-121">这就是每个 `Person` 在 <xref:System.Windows.Controls.ListBox> 中显示为名字的原因。</span><span class="sxs-lookup"><span data-stu-id="a83d6-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="a83d6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a83d6-122">See also</span></span>

- [<span data-ttu-id="a83d6-123">将主-详细模式与分层数据结合使用</span><span class="sxs-lookup"><span data-stu-id="a83d6-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="a83d6-124">将主-详细模式与分层 XML 数据结合使用</span><span class="sxs-lookup"><span data-stu-id="a83d6-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="a83d6-125">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="a83d6-125">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="a83d6-126">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="a83d6-126">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="a83d6-127">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a83d6-127">How-to Topics</span></span>](data-binding-how-to-topics.md)
