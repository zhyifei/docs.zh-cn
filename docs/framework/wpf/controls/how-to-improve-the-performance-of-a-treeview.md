---
title: "如何：提高 TreeView 的性能"
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
helpviewer_keywords: TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c13a9c89bdcb149df61f26177ea8705e502402f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="6ec0d-102">如何：提高 TreeView 的性能</span><span class="sxs-lookup"><span data-stu-id="6ec0d-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="6ec0d-103">如果<xref:System.Windows.Controls.TreeView>包含多个项，用户界面中，它所加载的时间量可能会导致较长的延迟。</span><span class="sxs-lookup"><span data-stu-id="6ec0d-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="6ec0d-104">你可以通过设置来缩短加载时间`VirtualizingStackPanel.IsVirtualizing`附加到属性`true`。</span><span class="sxs-lookup"><span data-stu-id="6ec0d-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="6ec0d-105">UI 还可能会很慢时在用户滚动做出反应<xref:System.Windows.Controls.TreeView>通过使用鼠标滚轮或拖动滚动条上的滚动块。</span><span class="sxs-lookup"><span data-stu-id="6ec0d-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="6ec0d-106">你可以提高的性能<xref:System.Windows.Controls.TreeView>通过设置在用户滚动时`VirtualizingStackPanel.VirtualizationMode`附加到属性<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="6ec0d-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ec0d-107">示例</span><span class="sxs-lookup"><span data-stu-id="6ec0d-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="6ec0d-108">描述</span><span class="sxs-lookup"><span data-stu-id="6ec0d-108">Description</span></span>  
<span data-ttu-id="6ec0d-109">下面的示例创建<xref:System.Windows.Controls.TreeView>设置`VirtualizingStackPanel.IsVirtualizing`附加属性为 true 和`VirtualizingStackPanel.VirtualizationMode`附加到属性<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>以优化其性能。</span><span class="sxs-lookup"><span data-stu-id="6ec0d-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="6ec0d-110">代码</span><span class="sxs-lookup"><span data-stu-id="6ec0d-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="6ec0d-111">下面的示例显示了数据，使用前面的示例。</span><span class="sxs-lookup"><span data-stu-id="6ec0d-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="6ec0d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ec0d-112">See Also</span></span>  
 [<span data-ttu-id="6ec0d-113">控件</span><span class="sxs-lookup"><span data-stu-id="6ec0d-113">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
