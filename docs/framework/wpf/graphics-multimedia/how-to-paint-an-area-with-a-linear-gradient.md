---
title: "如何：绘制带有线性渐变的区域"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eec4ec2fc7ba99081eaafa6803d20c99bebc6c2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="8c645-102">如何：绘制带有线性渐变的区域</span><span class="sxs-lookup"><span data-stu-id="8c645-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="8c645-103">此示例演示如何使用<xref:System.Windows.Media.LinearGradientBrush>类，以使用线性渐变绘制区域。</span><span class="sxs-lookup"><span data-stu-id="8c645-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="8c645-104">在下面的示例中，<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>用黄色从过渡到红色以蓝色和浅绿色对角线方向线性渐变绘制。</span><span class="sxs-lookup"><span data-stu-id="8c645-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c645-105">示例</span><span class="sxs-lookup"><span data-stu-id="8c645-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="8c645-106">下图显示了前面的示例所创建的渐变。</span><span class="sxs-lookup"><span data-stu-id="8c645-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="8c645-107">![对角线方向线性渐变](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="8c645-107">![Diagonal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="8c645-108">若要创建的水平线性渐变，更改<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>和<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>的<xref:System.Windows.Media.LinearGradientBrush>到 (0,0.5) 和 (1,0.5)。</span><span class="sxs-lookup"><span data-stu-id="8c645-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="8c645-109">在下面的示例中，<xref:System.Windows.Shapes.Rectangle>使用水平线性渐变绘制。</span><span class="sxs-lookup"><span data-stu-id="8c645-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="8c645-110">下图显示了前面的示例所创建的渐变。</span><span class="sxs-lookup"><span data-stu-id="8c645-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="8c645-111">![水平线性渐变](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="8c645-111">![A horizontal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="8c645-112">若要创建垂直线性渐变，更改<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>和<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>的<xref:System.Windows.Media.LinearGradientBrush>到 (0.5，0) 和 (0.5，1)。</span><span class="sxs-lookup"><span data-stu-id="8c645-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="8c645-113">在下面的示例中，<xref:System.Windows.Shapes.Rectangle>使用垂直线性渐变绘制。</span><span class="sxs-lookup"><span data-stu-id="8c645-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="8c645-114">下图显示了前面的示例所创建的渐变。</span><span class="sxs-lookup"><span data-stu-id="8c645-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="8c645-115">![垂直线性渐变](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="8c645-115">![Vertical linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c645-116">本主题中的示例使用默认坐标系统，用于设置的起始点和终结点。</span><span class="sxs-lookup"><span data-stu-id="8c645-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="8c645-117">默认坐标系统是相对于边界框： 0 表示的边界框中，0%和 1 表示 100%的边界框。</span><span class="sxs-lookup"><span data-stu-id="8c645-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="8c645-118">你可以通过设置来更改此坐标系<xref:System.Windows.Media.GradientBrush.MappingMode%2A>属性值<xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="8c645-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8c645-119">绝对坐标系与范围框无关。</span><span class="sxs-lookup"><span data-stu-id="8c645-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="8c645-120">值直接在本地空间中解释。</span><span class="sxs-lookup"><span data-stu-id="8c645-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="8c645-121">有关其他示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="8c645-121">For additional examples, see [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="8c645-122">有关渐变和画笔的其他类型的详细信息，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8c645-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
