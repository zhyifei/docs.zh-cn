---
title: "如何：获取 Visual 的偏移量"
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
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22c35a683f479660a17f11e44f9a0721f9d35968
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="94997-102">如何：获取 Visual 的偏移量</span><span class="sxs-lookup"><span data-stu-id="94997-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="94997-103">这些示例演示如何检索相对于其父级，或任何祖先或后代的视觉对象的偏移量的值。</span><span class="sxs-lookup"><span data-stu-id="94997-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94997-104">示例</span><span class="sxs-lookup"><span data-stu-id="94997-104">Example</span></span>  
 <span data-ttu-id="94997-105">下面的标记的示例演示<xref:System.Windows.Controls.TextBlock>定义与<xref:System.Windows.FrameworkElement.Margin%2A>值为 4。</span><span class="sxs-lookup"><span data-stu-id="94997-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="94997-106">下面的代码示例演示如何使用<xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A>方法来检索其中的偏移量<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="94997-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="94997-107">包含偏移的值在返回<xref:System.Windows.Vector>值。</span><span class="sxs-lookup"><span data-stu-id="94997-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="94997-108">偏移量将考虑在内<xref:System.Windows.FrameworkElement.Margin%2A>值。</span><span class="sxs-lookup"><span data-stu-id="94997-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="94997-109">在这种情况下，<xref:System.Windows.Vector.X%2A>是 4，和<xref:System.Windows.Vector.Y%2A>为 4。</span><span class="sxs-lookup"><span data-stu-id="94997-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="94997-110">偏移量的返回的值是相对于的父级<xref:System.Windows.Media.Visual>。</span><span class="sxs-lookup"><span data-stu-id="94997-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="94997-111">如果你想要返回不是相对于的父级的偏移量的值<xref:System.Windows.Media.Visual>，使用<xref:System.Windows.Media.Visual.TransformToAncestor%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="94997-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="94997-112">获取的偏移量相对于上级</span><span class="sxs-lookup"><span data-stu-id="94997-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="94997-113">下面的标记的示例演示<xref:System.Windows.Controls.TextBlock>嵌套在两个<xref:System.Windows.Controls.StackPanel>对象。</span><span class="sxs-lookup"><span data-stu-id="94997-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="94997-114">下图显示标记的结果。</span><span class="sxs-lookup"><span data-stu-id="94997-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="94997-115">![对象的偏移量值](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="94997-115">![Offset values of objects](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="94997-116">嵌套在两个 StackPanels 的 TextBlock</span><span class="sxs-lookup"><span data-stu-id="94997-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="94997-117">下面的代码示例演示如何使用<xref:System.Windows.Media.Visual.TransformToAncestor%2A>方法来检索其中的偏移量<xref:System.Windows.Controls.TextBlock>相对于包含<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="94997-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="94997-118">包含偏移的值在返回<xref:System.Windows.Media.GeneralTransform>值。</span><span class="sxs-lookup"><span data-stu-id="94997-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="94997-119">偏移量将考虑在内<xref:System.Windows.FrameworkElement.Margin%2A>中包含的所有对象的值<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="94997-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="94997-120">在这种情况下，<xref:System.Windows.Vector.X%2A>为 28 (16 + 8 + 4) 和<xref:System.Windows.Vector.Y%2A>为 28。</span><span class="sxs-lookup"><span data-stu-id="94997-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="94997-121">偏移量的返回的值是相对的祖先<xref:System.Windows.Media.Visual>。</span><span class="sxs-lookup"><span data-stu-id="94997-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="94997-122">如果你想要返回的是相对于的后代的偏移量的值<xref:System.Windows.Media.Visual>，使用<xref:System.Windows.Media.Visual.TransformToDescendant%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="94997-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="94997-123">获取的偏移量相对于子代</span><span class="sxs-lookup"><span data-stu-id="94997-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="94997-124">下面的标记的示例演示<xref:System.Windows.Controls.TextBlock>包含在<xref:System.Windows.Controls.StackPanel>对象。</span><span class="sxs-lookup"><span data-stu-id="94997-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="94997-125">下面的代码示例演示如何使用<xref:System.Windows.Media.Visual.TransformToDescendant%2A>方法来检索其中的偏移量<xref:System.Windows.Controls.StackPanel>相对于其子级<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="94997-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="94997-126">包含偏移的值在返回<xref:System.Windows.Media.GeneralTransform>值。</span><span class="sxs-lookup"><span data-stu-id="94997-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="94997-127">偏移量将考虑在内<xref:System.Windows.FrameworkElement.Margin%2A>的所有对象的值。</span><span class="sxs-lookup"><span data-stu-id="94997-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="94997-128">在这种情况下，<xref:System.Windows.Vector.X%2A>是-4，和<xref:System.Windows.Vector.Y%2A>是-4。</span><span class="sxs-lookup"><span data-stu-id="94997-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="94997-129">偏移量的值是负值，因为父对象产生负面偏移量相对于其子对象。</span><span class="sxs-lookup"><span data-stu-id="94997-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94997-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94997-130">See Also</span></span>  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="94997-131">WPF 图形呈现概述</span><span class="sxs-lookup"><span data-stu-id="94997-131">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
