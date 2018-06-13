---
title: 如何：使用径向渐变绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: d794f85ce4968e1cf1759df5358834f3b4cdfb50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560636"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="43422-102">如何：使用径向渐变绘制区域</span><span class="sxs-lookup"><span data-stu-id="43422-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="43422-103">此示例演示如何使用<xref:System.Windows.Media.RadialGradientBrush>类，以使用径向渐变绘制区域。</span><span class="sxs-lookup"><span data-stu-id="43422-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43422-104">示例</span><span class="sxs-lookup"><span data-stu-id="43422-104">Example</span></span>  
 <span data-ttu-id="43422-105">下面的示例使用<xref:System.Windows.Media.RadialGradientBrush>来绘制一个具有红色以蓝色和浅绿色从黄色转换的径向渐变的矩形。</span><span class="sxs-lookup"><span data-stu-id="43422-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="43422-106">下图显示了前面示例中的渐变。</span><span class="sxs-lookup"><span data-stu-id="43422-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="43422-107">其中突出显示的渐变停止点。</span><span class="sxs-lookup"><span data-stu-id="43422-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="43422-108">![径向渐变中的梯度停止点](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="43422-108">![Gradient stops in a radial gradient](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43422-109">本主题中的示例使用默认坐标系统设置控点。</span><span class="sxs-lookup"><span data-stu-id="43422-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="43422-110">默认坐标系统是相对于边界框： 0 表示的边界框中，0%和 1 表示 100%的边界框。</span><span class="sxs-lookup"><span data-stu-id="43422-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="43422-111">你可以通过设置来更改此坐标系<xref:System.Windows.Media.GradientBrush.MappingMode%2A>属性值<xref:System.Windows.Media.BrushMappingMode.Absolute>。</span><span class="sxs-lookup"><span data-stu-id="43422-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="43422-112">绝对坐标系与范围框无关。</span><span class="sxs-lookup"><span data-stu-id="43422-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="43422-113">值直接在本地空间中解释。</span><span class="sxs-lookup"><span data-stu-id="43422-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="43422-114">有关其他<xref:System.Windows.Media.RadialGradientBrush>示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="43422-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="43422-115">有关渐变和画笔的其他类型的详细信息，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="43422-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
