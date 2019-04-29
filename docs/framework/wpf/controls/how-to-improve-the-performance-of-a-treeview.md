---
title: 如何：提升 TreeView 的性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: de1b46da2a7c6c3db0c0c19cdbb654fcf2fbbd6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771002"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="8f5cd-102">如何：提升 TreeView 的性能</span><span class="sxs-lookup"><span data-stu-id="8f5cd-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="8f5cd-103">如果<xref:System.Windows.Controls.TreeView>包含很多项所花费的时间量可能会导致明显的延迟导致用户界面中。</span><span class="sxs-lookup"><span data-stu-id="8f5cd-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="8f5cd-104">可以通过设置缩短加载时间`VirtualizingStackPanel.IsVirtualizing`附加属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="8f5cd-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="8f5cd-105">UI 也可能较慢时用户滚动做出反应<xref:System.Windows.Controls.TreeView>通过使用鼠标滚轮或拖动滚动条的滚动块。</span><span class="sxs-lookup"><span data-stu-id="8f5cd-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="8f5cd-106">您可以提高的性能<xref:System.Windows.Controls.TreeView>通过设置在用户滚动时`VirtualizingStackPanel.VirtualizationMode`附加属性设置为<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="8f5cd-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f5cd-107">示例</span><span class="sxs-lookup"><span data-stu-id="8f5cd-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="8f5cd-108">描述</span><span class="sxs-lookup"><span data-stu-id="8f5cd-108">Description</span></span>  
<span data-ttu-id="8f5cd-109">下面的示例创建<xref:System.Windows.Controls.TreeView>，用于设置`VirtualizingStackPanel.IsVirtualizing`附加属性设置为 true 并`VirtualizingStackPanel.VirtualizationMode`附加到属性<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>以优化其性能。</span><span class="sxs-lookup"><span data-stu-id="8f5cd-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="8f5cd-110">代码</span><span class="sxs-lookup"><span data-stu-id="8f5cd-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="8f5cd-111">下面的示例显示了前面的示例使用的数据。</span><span class="sxs-lookup"><span data-stu-id="8f5cd-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="8f5cd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f5cd-112">See also</span></span>

- [<span data-ttu-id="8f5cd-113">控件</span><span class="sxs-lookup"><span data-stu-id="8f5cd-113">Controls</span></span>](../advanced/optimizing-performance-controls.md)
