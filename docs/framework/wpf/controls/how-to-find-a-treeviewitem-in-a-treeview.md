---
title: "如何：在 TreeView 中查找 TreeViewItem"
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
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a231f5eae92bff8e3d525579dae865aaa0d7e496
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a><span data-ttu-id="6e6bf-102">如何：在 TreeView 中查找 TreeViewItem</span><span class="sxs-lookup"><span data-stu-id="6e6bf-102">How to: Find a TreeViewItem in a TreeView</span></span>
<span data-ttu-id="6e6bf-103"><xref:System.Windows.Controls.TreeView>控件提供一种简便方式显示分层数据。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-103">The <xref:System.Windows.Controls.TreeView> control provides a convenient way to display hierarchical data.</span></span> <span data-ttu-id="6e6bf-104">如果你<xref:System.Windows.Controls.TreeView>绑定到数据源，<xref:System.Windows.Controls.TreeView.SelectedItem%2A>属性提供便利的方法，让你快速检索所选的数据对象。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-104">If your <xref:System.Windows.Controls.TreeView> is bound to a data source, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property provides a convenient way for you to quickly retrieve the selected data object.</span></span> <span data-ttu-id="6e6bf-105">通常，最好使用基础数据对象，但有时你可能需要以编程方式操作数据的包含<xref:System.Windows.Controls.TreeViewItem>。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-105">It is typically best to work with the underlying data object, but sometimes you may need to programmatically manipulate the data's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="6e6bf-106">例如，你可能需要以编程方式展开<xref:System.Windows.Controls.TreeViewItem>，或选择不同的项在<xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-106">For example, you may need to programmatically expand the <xref:System.Windows.Controls.TreeViewItem>, or select a different item in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="6e6bf-107">若要查找<xref:System.Windows.Controls.TreeViewItem>包含特定数据对象，则必须遍历每个级别的<xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-107">To find a <xref:System.Windows.Controls.TreeViewItem> that contains a specific data object, you must traverse each level of the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="6e6bf-108">中的项<xref:System.Windows.Controls.TreeView>可以还虚拟化以提高性能。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-108">The items in a <xref:System.Windows.Controls.TreeView> can also be virtualized to improve performance.</span></span> <span data-ttu-id="6e6bf-109">在其中项可能进行虚拟化的情况下，您还必须实现<xref:System.Windows.Controls.TreeViewItem>检查它是否包含数据对象。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-109">In the case where items might be virtualized, you also must realize a <xref:System.Windows.Controls.TreeViewItem> to check whether it contains the data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e6bf-110">示例</span><span class="sxs-lookup"><span data-stu-id="6e6bf-110">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="6e6bf-111">描述</span><span class="sxs-lookup"><span data-stu-id="6e6bf-111">Description</span></span>  
 <span data-ttu-id="6e6bf-112">下面的示例搜索<xref:System.Windows.Controls.TreeView>为特定对象，并返回该对象的包含<xref:System.Windows.Controls.TreeViewItem>。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-112">The following example searches a <xref:System.Windows.Controls.TreeView> for a specific object and returns the object's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="6e6bf-113">该示例将确保每个<xref:System.Windows.Controls.TreeViewItem>实例化，以便可以搜索及其子项。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-113">The example ensures that each <xref:System.Windows.Controls.TreeViewItem> is instantiated so that its child items can be searched.</span></span> <span data-ttu-id="6e6bf-114">此示例也适用于如果<xref:System.Windows.Controls.TreeView>不使用虚拟化的项。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-114">This example also works if the <xref:System.Windows.Controls.TreeView> does not use virtualized items.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e6bf-115">下面的示例适用于任何<xref:System.Windows.Controls.TreeView>，而不考虑基础数据模型和搜索每个<xref:System.Windows.Controls.TreeViewItem>直到找到该对象。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-115">The following example works for any <xref:System.Windows.Controls.TreeView>, regardless of the underlying data model, and searches every <xref:System.Windows.Controls.TreeViewItem> until the object is found.</span></span> <span data-ttu-id="6e6bf-116">具有更好的性能的另一种方法是搜索指定对象的数据模型、 跟踪的数据层次结构，在其位置，然后找到相应<xref:System.Windows.Controls.TreeViewItem>中<xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-116">Another technique that has better performance is to search the data model for the specified object, keep track of its location within the data hierarchy, and then find the corresponding <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="6e6bf-117">但是，具有更好的性能的技术要求的数据模型的知识，并且不能通用对于任何给定<xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-117">However, the technique that has better performance requires knowledge of the data model and cannot be generalized for any given <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="6e6bf-118">代码</span><span class="sxs-lookup"><span data-stu-id="6e6bf-118">Code</span></span>  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 <span data-ttu-id="6e6bf-119">前面的代码依赖于自定义<xref:System.Windows.Controls.VirtualizingStackPanel>公开一个名为方法`BringIntoView`。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-119">The previous code relies on a custom <xref:System.Windows.Controls.VirtualizingStackPanel> that exposes a method named `BringIntoView`.</span></span> <span data-ttu-id="6e6bf-120">下面的代码定义自定义<xref:System.Windows.Controls.VirtualizingStackPanel>。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-120">The following code defines the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 <span data-ttu-id="6e6bf-121">下面的 XAML 演示如何创建<xref:System.Windows.Controls.TreeView>使用自定义<xref:System.Windows.Controls.VirtualizingStackPanel>。</span><span class="sxs-lookup"><span data-stu-id="6e6bf-121">The following XAML shows how to create a <xref:System.Windows.Controls.TreeView> that uses the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6e6bf-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e6bf-122">See Also</span></span>  
 [<span data-ttu-id="6e6bf-123">提升 TreeView 的性能</span><span class="sxs-lookup"><span data-stu-id="6e6bf-123">Improve the Performance of a TreeView</span></span>](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
