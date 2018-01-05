---
title: "如何：创建复合绘图"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 424f77b076344ad86db992614175243d1473886d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="2be36-102">如何：创建复合绘图</span><span class="sxs-lookup"><span data-stu-id="2be36-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="2be36-103">此示例演示如何使用<xref:System.Windows.Media.DrawingGroup>来通过组合多个创建复杂图形<xref:System.Windows.Media.Drawing>到单个复合绘图的对象。</span><span class="sxs-lookup"><span data-stu-id="2be36-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2be36-104">示例</span><span class="sxs-lookup"><span data-stu-id="2be36-104">Example</span></span>  
 <span data-ttu-id="2be36-105">下面的示例使用<xref:System.Windows.Media.DrawingGroup>若要创建一个复合从图形<xref:System.Windows.Media.GeometryDrawing>和<xref:System.Windows.Media.ImageDrawing>对象。</span><span class="sxs-lookup"><span data-stu-id="2be36-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="2be36-106">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="2be36-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="2be36-107">![具有多个绘图的 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="2be36-107">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="2be36-108">通过 DrawingGroup 创建复合绘图</span><span class="sxs-lookup"><span data-stu-id="2be36-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="2be36-109">请注意显示绘制的边界的灰色边框。</span><span class="sxs-lookup"><span data-stu-id="2be36-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="2be36-110">你可以使用<xref:System.Windows.Media.DrawingGroup>应用<xref:System.Windows.Media.DrawingGroup.Transform%2A>，<xref:System.Windows.Media.DrawingGroup.Opacity%2A>设置， <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>， <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>， <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>，或<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>到它所包含的绘图。</span><span class="sxs-lookup"><span data-stu-id="2be36-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="2be36-111">因为<xref:System.Windows.Media.DrawingGroup>也<xref:System.Windows.Media.Drawing>，它可以包含其他<xref:System.Windows.Media.DrawingGroup>对象。</span><span class="sxs-lookup"><span data-stu-id="2be36-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="2be36-112">下面的示例是类似于前面的示例中，只不过它使用其他<xref:System.Windows.Media.DrawingGroup>要应用于某些图形的位图效果并不透明蒙版的对象。</span><span class="sxs-lookup"><span data-stu-id="2be36-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="2be36-113">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="2be36-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="2be36-114">![具有多个绘图的 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="2be36-114">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="2be36-115">复合绘制都具有多个 DrawingGroup 对象</span><span class="sxs-lookup"><span data-stu-id="2be36-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="2be36-116">请注意显示绘制的边界的灰色边框。</span><span class="sxs-lookup"><span data-stu-id="2be36-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="2be36-117">有关详细信息<xref:System.Windows.Media.Drawing>对象，请参阅[绘制对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2be36-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be36-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2be36-118">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [<span data-ttu-id="2be36-119">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="2be36-119">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
