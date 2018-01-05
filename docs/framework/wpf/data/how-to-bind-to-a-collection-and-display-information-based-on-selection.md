---
title: "如何：绑定到集合并基于选择显示信息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a751025470b566ef1e735e4ddd192cfd8fc354ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="0e1f1-102">如何：绑定到集合并基于选择显示信息</span><span class="sxs-lookup"><span data-stu-id="0e1f1-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="0e1f1-103">在简单的主 / 从方案中，具有数据绑定<xref:System.Windows.Controls.ItemsControl>如<xref:System.Windows.Controls.ListBox>。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="0e1f1-104">基于用户选择，显示有关选定项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="0e1f1-105">此示例演示如何实现这种情况。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e1f1-106">示例</span><span class="sxs-lookup"><span data-stu-id="0e1f1-106">Example</span></span>  
 <span data-ttu-id="0e1f1-107">在此示例中，`People`是<xref:System.Collections.ObjectModel.ObservableCollection%601>的`Person`类。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="0e1f1-108">这`Person`类包含三个属性： `FirstName`， `LastName`，和`HomeTown`，所有类型`string`。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="0e1f1-109"><xref:System.Windows.Controls.ContentControl>使用以下<xref:System.Windows.DataTemplate>，它定义如何的信息`Person`显示：</span><span class="sxs-lookup"><span data-stu-id="0e1f1-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="0e1f1-110">以下是该示例生成的屏幕快照。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="0e1f1-111"><xref:System.Windows.Controls.ContentControl>显示选择的人员的其他属性。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="0e1f1-112">![绑定到集合](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="0e1f1-112">![Binding to a collection](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="0e1f1-113">需要注意，在此示例中，两个的事项为：</span><span class="sxs-lookup"><span data-stu-id="0e1f1-113">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="0e1f1-114"><xref:System.Windows.Controls.ListBox>和<xref:System.Windows.Controls.ContentControl>将绑定到相同的源。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="0e1f1-115"><xref:System.Windows.Data.Binding.Path%2A>不指定这两种绑定的属性，因为这两个控件绑定到整个集合对象。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2.  <span data-ttu-id="0e1f1-116">必须设置<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>属性`true`为使工作。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="0e1f1-117">将设置此属性可确保所选的项始终设置为<xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="0e1f1-118">或者，如果<xref:System.Windows.Controls.ListBox>获取它从数据<xref:System.Windows.Data.CollectionViewSource>，它自动同步所选内容和货币。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="0e1f1-119">请注意，`Person`类重写`ToString`方法按以下方式。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="0e1f1-120">默认情况下，<xref:System.Windows.Controls.ListBox>调用`ToString`并在与绑定集合中显示的字符串表示形式的每个对象。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="0e1f1-121">这就是为什么每个`Person`显示中的第一个名为<xref:System.Windows.Controls.ListBox>。</span><span class="sxs-lookup"><span data-stu-id="0e1f1-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="0e1f1-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e1f1-122">See Also</span></span>  
 [<span data-ttu-id="0e1f1-123">将主-详细模式与分层数据结合使用</span><span class="sxs-lookup"><span data-stu-id="0e1f1-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)  
 [<span data-ttu-id="0e1f1-124">将主-详细模式与分层 XML 数据结合使用</span><span class="sxs-lookup"><span data-stu-id="0e1f1-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [<span data-ttu-id="0e1f1-125">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="0e1f1-125">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="0e1f1-126">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="0e1f1-126">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="0e1f1-127">帮助主题</span><span class="sxs-lookup"><span data-stu-id="0e1f1-127">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
