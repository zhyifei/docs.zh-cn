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
ms.openlocfilehash: c3bcc11dea4b1f223f629415591ab03588881dde
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379778"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="89466-102">如何：使用径向渐变绘制区域</span><span class="sxs-lookup"><span data-stu-id="89466-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="89466-103">此示例演示如何使用<xref:System.Windows.Media.RadialGradientBrush>类，以使用径向渐变绘制区域。</span><span class="sxs-lookup"><span data-stu-id="89466-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89466-104">示例</span><span class="sxs-lookup"><span data-stu-id="89466-104">Example</span></span>  
 <span data-ttu-id="89466-105">下面的示例使用<xref:System.Windows.Media.RadialGradientBrush>绘制一个矩形使用径向渐变的黄色从过渡到红色变为蓝色变为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="89466-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="89466-106">下图显示了前面的示例中的渐变。</span><span class="sxs-lookup"><span data-stu-id="89466-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="89466-107">其中突出显示的渐变停止点。</span><span class="sxs-lookup"><span data-stu-id="89466-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="89466-108">![径向渐变中的梯度停止点](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="89466-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89466-109">本主题中的示例使用默认坐标系来设置控制点。</span><span class="sxs-lookup"><span data-stu-id="89466-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="89466-110">默认坐标系与边界框是：0 指示边界框的 0 %1 指示边界框的 100%。</span><span class="sxs-lookup"><span data-stu-id="89466-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="89466-111">您可以通过设置更改此坐标系<xref:System.Windows.Media.GradientBrush.MappingMode%2A>属性的值<xref:System.Windows.Media.BrushMappingMode.Absolute>。</span><span class="sxs-lookup"><span data-stu-id="89466-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="89466-112">绝对坐标系与范围框无关。</span><span class="sxs-lookup"><span data-stu-id="89466-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="89466-113">值直接在本地空间中解释。</span><span class="sxs-lookup"><span data-stu-id="89466-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="89466-114">有关更多<xref:System.Windows.Media.RadialGradientBrush>示例，请参阅[画笔示例](https://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="89466-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="89466-115">渐变和画笔的其他类型的详细信息，请参阅[使用纯色和渐变概述进行绘制](painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="89466-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
