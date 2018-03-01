---
title: "如何：将 TreeView 绑定到深度无法确定的数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: be21ecb75420b6499e5b95d5f4d93a5f079f9646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a><span data-ttu-id="81d1d-102">如何：将 TreeView 绑定到深度无法确定的数据</span><span class="sxs-lookup"><span data-stu-id="81d1d-102">How to: Bind a TreeView to Data That Has an Indeterminable Depth</span></span>
<span data-ttu-id="81d1d-103">可能有的时候你想要将绑定<xref:System.Windows.Controls.TreeView>到数据源不已知其深度。</span><span class="sxs-lookup"><span data-stu-id="81d1d-103">There might be times when you want to bind a <xref:System.Windows.Controls.TreeView> to a data source whose depth is not known.</span></span>  <span data-ttu-id="81d1d-104">这会时发生数据具有递归性质，例如文件系统，其中文件夹可以包含文件夹或公司的组织结构，其中员工的直接下属作为其他员工。</span><span class="sxs-lookup"><span data-stu-id="81d1d-104">This can occur when the data is recursive in nature, such as a file system, where folders can contain folders, or a company's organizational structure, where employees have other employees as direct reports.</span></span>  
  
 <span data-ttu-id="81d1d-105">数据源必须具有层次结构的对象模型。</span><span class="sxs-lookup"><span data-stu-id="81d1d-105">The data source must have a hierarchical object model.</span></span> <span data-ttu-id="81d1d-106">例如，`Employee`类可能包含的是直接下属的员工的员工对象的集合。</span><span class="sxs-lookup"><span data-stu-id="81d1d-106">For example, an `Employee` class might contain a collection of Employee objects that are the direct reports of an employee.</span></span> <span data-ttu-id="81d1d-107">如果不是分层的方式表示数据，则必须生成的分层表示形式的数据。</span><span class="sxs-lookup"><span data-stu-id="81d1d-107">If the data is represented in a way that is not hierarchical, you must build a hierarchical representation of the data.</span></span>  
  
 <span data-ttu-id="81d1d-108">当你将设置<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType>属性如果<xref:System.Windows.Controls.ItemsControl>生成<xref:System.Windows.Controls.ItemsControl>每个子项，则子<xref:System.Windows.Controls.ItemsControl>使用相同<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>与父项。</span><span class="sxs-lookup"><span data-stu-id="81d1d-108">When you set the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> property and if the <xref:System.Windows.Controls.ItemsControl> generates an <xref:System.Windows.Controls.ItemsControl> for each child item, then the child <xref:System.Windows.Controls.ItemsControl> uses the same <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> as the parent.</span></span> <span data-ttu-id="81d1d-109">例如，如果你设置<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>数据绑定属性<xref:System.Windows.Controls.TreeView>，每个<xref:System.Windows.Controls.TreeViewItem>，它是生成的使用<xref:System.Windows.DataTemplate>，已分配给<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>属性<xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="81d1d-109">For example, if you set the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property on a data-bound <xref:System.Windows.Controls.TreeView>, each <xref:System.Windows.Controls.TreeViewItem> that is generated uses the <xref:System.Windows.DataTemplate> that was assigned to the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property of the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="81d1d-110"><xref:System.Windows.HierarchicalDataTemplate>使您能够指定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>为<xref:System.Windows.Controls.TreeViewItem>，或任何<xref:System.Windows.Controls.HeaderedItemsControl>，数据模板。</span><span class="sxs-lookup"><span data-stu-id="81d1d-110">The <xref:System.Windows.HierarchicalDataTemplate> enables you to specify the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for a <xref:System.Windows.Controls.TreeViewItem>, or any <xref:System.Windows.Controls.HeaderedItemsControl>, on the data template.</span></span> <span data-ttu-id="81d1d-111">当你将设置<xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType>属性的值时使用<xref:System.Windows.HierarchicalDataTemplate>应用。</span><span class="sxs-lookup"><span data-stu-id="81d1d-111">When you set the <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> property, that value is used when the <xref:System.Windows.HierarchicalDataTemplate> is applied.</span></span> <span data-ttu-id="81d1d-112">通过使用<xref:System.Windows.HierarchicalDataTemplate>，你可以以递归方式集<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>每个<xref:System.Windows.Controls.TreeViewItem>中<xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="81d1d-112">By using a <xref:System.Windows.HierarchicalDataTemplate>, you can recursively set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for each <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81d1d-113">示例</span><span class="sxs-lookup"><span data-stu-id="81d1d-113">Example</span></span>  
 <span data-ttu-id="81d1d-114">下面的示例演示如何将绑定<xref:System.Windows.Controls.TreeView>到层次结构数据，然后使用<xref:System.Windows.HierarchicalDataTemplate>指定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>每个<xref:System.Windows.Controls.TreeViewItem>。</span><span class="sxs-lookup"><span data-stu-id="81d1d-114">The following example demonstrates how to bind a <xref:System.Windows.Controls.TreeView> to hierarchical data and use a <xref:System.Windows.HierarchicalDataTemplate> to specify the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for each <xref:System.Windows.Controls.TreeViewItem>.</span></span>  <span data-ttu-id="81d1d-115"><xref:System.Windows.Controls.TreeView>将绑定到表示一家公司中的员工的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="81d1d-115">The <xref:System.Windows.Controls.TreeView> binds to XML data that represents the employees in a company.</span></span>  <span data-ttu-id="81d1d-116">每个`Employee`元素可以包含其他`Employee`元素以指示隶属关系。</span><span class="sxs-lookup"><span data-stu-id="81d1d-116">Each `Employee` element can contain other `Employee` elements to indicate who reports to whom.</span></span> <span data-ttu-id="81d1d-117">因为数据是递归的<xref:System.Windows.HierarchicalDataTemplate>可以应用于每个级别。</span><span class="sxs-lookup"><span data-stu-id="81d1d-117">Because the data is recursive, the <xref:System.Windows.HierarchicalDataTemplate> can be applied to each level.</span></span>  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="81d1d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="81d1d-118">See Also</span></span>  
 [<span data-ttu-id="81d1d-119">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="81d1d-119">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="81d1d-120">数据模板化概述</span><span class="sxs-lookup"><span data-stu-id="81d1d-120">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)
