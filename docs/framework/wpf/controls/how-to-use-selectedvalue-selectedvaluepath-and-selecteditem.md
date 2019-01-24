---
title: 如何：使用 SelectedValue、SelectedValuePath 和 SelectedItem
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: 1bb307009586a5bbf4e9accefb633b97dc837528
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637815"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="0bac2-102">如何：使用 SelectedValue、SelectedValuePath 和 SelectedItem</span><span class="sxs-lookup"><span data-stu-id="0bac2-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="0bac2-103">此示例演示如何使用<xref:System.Windows.Controls.TreeView.SelectedValue%2A>并<xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>属性，以指定的值<xref:System.Windows.Controls.TreeView.SelectedItem%2A>的<xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="0bac2-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bac2-104">示例</span><span class="sxs-lookup"><span data-stu-id="0bac2-104">Example</span></span>  
 <span data-ttu-id="0bac2-105"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>属性提供了一种方法来指定<xref:System.Windows.Controls.TreeView.SelectedValue%2A>有关<xref:System.Windows.Controls.TreeView.SelectedItem%2A>中<xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="0bac2-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="0bac2-106"><xref:System.Windows.Controls.TreeView.SelectedItem%2A>表示中的对象<xref:System.Windows.Controls.ItemsControl.Items%2A>集合和<xref:System.Windows.Controls.TreeView>显示选定项的单个属性的值。</span><span class="sxs-lookup"><span data-stu-id="0bac2-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="0bac2-107"><xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>属性指定用于确定值的属性的路径<xref:System.Windows.Controls.TreeView.SelectedValue%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0bac2-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="0bac2-108">本主题中的示例演示了这一概念。</span><span class="sxs-lookup"><span data-stu-id="0bac2-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="0bac2-109">下面的示例演示<xref:System.Windows.Data.XmlDataProvider>包含雇员的信息。</span><span class="sxs-lookup"><span data-stu-id="0bac2-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="0bac2-110">下面的示例定义<xref:System.Windows.HierarchicalDataTemplate>，它显示`EmployeeName`并`EmployeeWorkDay`的`Employee`。</span><span class="sxs-lookup"><span data-stu-id="0bac2-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="0bac2-111">请注意，<xref:System.Windows.HierarchicalDataTemplate>未指定`EmployeeNumber`作为模板的一部分。</span><span class="sxs-lookup"><span data-stu-id="0bac2-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="0bac2-112">下面的示例演示<xref:System.Windows.Controls.TreeView>，它使用以前定义<xref:System.Windows.HierarchicalDataTemplate>，用于设置和<xref:System.Windows.Controls.TreeView.SelectedValue%2A>属性设置为`EmployeeNumber`。</span><span class="sxs-lookup"><span data-stu-id="0bac2-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="0bac2-113">当选择`EmployeeName`中<xref:System.Windows.Controls.TreeView>，则<xref:System.Windows.Controls.TreeView.SelectedItem%2A>属性将返回`EmployeeInfo`对应于所选的数据项`EmployeeName`。</span><span class="sxs-lookup"><span data-stu-id="0bac2-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="0bac2-114">但是，由于<xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>的这<xref:System.Windows.Controls.TreeView>设置为`EmployeeNumber`，则<xref:System.Windows.Controls.TreeView.SelectedValue%2A>设置为`EmployeeNumber`。</span><span class="sxs-lookup"><span data-stu-id="0bac2-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="0bac2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bac2-115">See also</span></span>
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="0bac2-116">TreeView 概述</span><span class="sxs-lookup"><span data-stu-id="0bac2-116">TreeView Overview</span></span>](../../../../docs/framework/wpf/controls/treeview-overview.md)
- [<span data-ttu-id="0bac2-117">帮助主题</span><span class="sxs-lookup"><span data-stu-id="0bac2-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
