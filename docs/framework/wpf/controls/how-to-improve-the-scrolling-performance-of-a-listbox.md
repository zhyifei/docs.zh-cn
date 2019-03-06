---
title: 如何：提高 ListBox 的滚动性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364548"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="e7090-102">如何：提高 ListBox 的滚动性能</span><span class="sxs-lookup"><span data-stu-id="e7090-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="e7090-103">如果<xref:System.Windows.Controls.ListBox>包含多个项，当用户滚动时，用户界面响应可能会很慢<xref:System.Windows.Controls.ListBox>通过使用鼠标滚轮或拖动滚动条的滚动块。</span><span class="sxs-lookup"><span data-stu-id="e7090-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="e7090-104">您可以提高的性能<xref:System.Windows.Controls.ListBox>通过设置在用户滚动时`VirtualizingStackPanel.VirtualizationMode`附加属性设置为<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e7090-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7090-105">示例</span><span class="sxs-lookup"><span data-stu-id="e7090-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="e7090-106">描述</span><span class="sxs-lookup"><span data-stu-id="e7090-106">Description</span></span>  
<span data-ttu-id="e7090-107">下面的示例创建<xref:System.Windows.Controls.ListBox>，并设置`VirtualizingStackPanel.VirtualizationMode`附加属性设置为<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>若要在滚动期间提高性能。</span><span class="sxs-lookup"><span data-stu-id="e7090-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="e7090-108">代码</span><span class="sxs-lookup"><span data-stu-id="e7090-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="e7090-109">下面的示例显示了前面的示例使用的数据。</span><span class="sxs-lookup"><span data-stu-id="e7090-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
