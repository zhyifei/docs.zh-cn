---
title: "如何：提高 ListBox 的滚动性能"
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
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58435948a3ddd8042b95b30b8d6cbdba984f34d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="12901-102">如何：提高 ListBox 的滚动性能</span><span class="sxs-lookup"><span data-stu-id="12901-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="12901-103">如果<xref:System.Windows.Controls.ListBox>包含多个项，用户界面响应可能会很慢，当用户滚动<xref:System.Windows.Controls.ListBox>通过使用鼠标滚轮或拖动滚动条上的滚动块。</span><span class="sxs-lookup"><span data-stu-id="12901-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="12901-104">你可以提高的性能<xref:System.Windows.Controls.ListBox>通过设置在用户滚动时`VirtualizingStackPanel.VirtualizationMode`附加到属性<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="12901-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12901-105">示例</span><span class="sxs-lookup"><span data-stu-id="12901-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="12901-106">描述</span><span class="sxs-lookup"><span data-stu-id="12901-106">Description</span></span>  
<span data-ttu-id="12901-107">下面的示例创建<xref:System.Windows.Controls.ListBox>和设置`VirtualizingStackPanel.VirtualizationMode`附加到属性<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>若要在滚动期间提高性能。</span><span class="sxs-lookup"><span data-stu-id="12901-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="12901-108">代码</span><span class="sxs-lookup"><span data-stu-id="12901-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="12901-109">下面的示例显示了数据，使用前面的示例。</span><span class="sxs-lookup"><span data-stu-id="12901-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
