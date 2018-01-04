---
title: "如何：在 StackPanel 中水平或垂直对齐内容"
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
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad3252b249c716d59b72a6c5af7bd96f2d058126
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="f100f-102">如何：在 StackPanel 中水平或垂直对齐内容</span><span class="sxs-lookup"><span data-stu-id="f100f-102">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="f100f-103">此示例演示如何调整<xref:System.Windows.Controls.StackPanel.Orientation%2A>中内容的<xref:System.Windows.Controls.StackPanel>元素，以及如何调整<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>子内容。</span><span class="sxs-lookup"><span data-stu-id="f100f-103">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f100f-104">示例</span><span class="sxs-lookup"><span data-stu-id="f100f-104">Example</span></span>  
 <span data-ttu-id="f100f-105">下面的示例创建三个<xref:System.Windows.Controls.ListBox>中的元素[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f100f-105">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="f100f-106">每个<xref:System.Windows.Controls.ListBox>表示的可能值<xref:System.Windows.Controls.StackPanel.Orientation%2A>， <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>，和<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="f100f-106">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="f100f-107">当用户选择的值中的任何<xref:System.Windows.Controls.ListBox>元素、 关联的属性的<xref:System.Windows.Controls.StackPanel>及其子<xref:System.Windows.Controls.Button>元素更改。</span><span class="sxs-lookup"><span data-stu-id="f100f-107">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="f100f-108">下面的代码隐藏文件与之关联的事件定义所做的更改<xref:System.Windows.Controls.ListBox>选择会有所变化。</span><span class="sxs-lookup"><span data-stu-id="f100f-108">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="f100f-109"><xref:System.Windows.Controls.StackPanel>由标识<xref:System.Windows.FrameworkElement.Name%2A> `sp1`。</span><span class="sxs-lookup"><span data-stu-id="f100f-109"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f100f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f100f-110">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 [<span data-ttu-id="f100f-111">面板概述</span><span class="sxs-lookup"><span data-stu-id="f100f-111">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
