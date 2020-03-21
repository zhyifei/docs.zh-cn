---
title: 如何：定位 ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 0f52703e4fe127daa40f220280f084b2026580cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186939"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="0730c-102">如何：定位 ToolTip</span><span class="sxs-lookup"><span data-stu-id="0730c-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="0730c-103">此示例演示如何在屏幕上指定工具提示的位置。</span><span class="sxs-lookup"><span data-stu-id="0730c-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0730c-104">示例</span><span class="sxs-lookup"><span data-stu-id="0730c-104">Example</span></span>  
 <span data-ttu-id="0730c-105">可以使用 在 和<xref:System.Windows.Controls.ToolTip><xref:System.Windows.Controls.ToolTipService>类 中定义的一组五个属性来定位工具提示。</span><span class="sxs-lookup"><span data-stu-id="0730c-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="0730c-106">下表显示了这两组五个属性，并根据类提供指向其参考文档的链接。</span><span class="sxs-lookup"><span data-stu-id="0730c-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="0730c-107">根据类对应的工具提示属性</span><span class="sxs-lookup"><span data-stu-id="0730c-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="0730c-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>类属性</span><span class="sxs-lookup"><span data-stu-id="0730c-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="0730c-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>类属性</span><span class="sxs-lookup"><span data-stu-id="0730c-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="0730c-110">如果使用对象定义工具提示的内容，则可以使用任一类的属性<xref:System.Windows.Controls.ToolTip>;如果使用对象定义工具提示的内容，则可以使用任一类的属性。但是，<xref:System.Windows.Controls.ToolTipService>属性优先。</span><span class="sxs-lookup"><span data-stu-id="0730c-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="0730c-111">对未<xref:System.Windows.Controls.ToolTipService>定义为<xref:System.Windows.Controls.ToolTip>对象的工具提示使用属性。</span><span class="sxs-lookup"><span data-stu-id="0730c-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="0730c-112">下图显示了如何使用这些属性定位工具提示。</span><span class="sxs-lookup"><span data-stu-id="0730c-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="0730c-113">尽管这些插图[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中的示例演示如何设置由<xref:System.Windows.Controls.ToolTip>类定义的属性，但类的<xref:System.Windows.Controls.ToolTipService>相应属性遵循相同的布局规则。</span><span class="sxs-lookup"><span data-stu-id="0730c-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="0730c-114">有关放置属性的可能值的详细信息，请参阅[弹出放置行为](popup-placement-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="0730c-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="0730c-115">下图显示了使用"放置"属性的工具提示放置：</span><span class="sxs-lookup"><span data-stu-id="0730c-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![使用放置属性显示工具提示放置的图表。](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="0730c-117">下图使用"放置"和"放置矩形"属性显示工具提示放置：</span><span class="sxs-lookup"><span data-stu-id="0730c-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![使用放置矩形属性显示工具提示放置位置的图表。](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="0730c-119">下图使用"放置"、放置矩形和偏移属性显示工具提示放置：</span><span class="sxs-lookup"><span data-stu-id="0730c-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![使用"偏移"属性显示工具提示放置位置的图表。](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="0730c-121">下面的示例演示如何使用<xref:System.Windows.Controls.ToolTip>属性来指定其内容为<xref:System.Windows.Controls.ToolTip>对象的工具提示的位置。</span><span class="sxs-lookup"><span data-stu-id="0730c-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="0730c-122">下面的示例演示如何使用<xref:System.Windows.Controls.ToolTipService>属性来指定其内容不是<xref:System.Windows.Controls.ToolTip>对象的工具提示的位置。</span><span class="sxs-lookup"><span data-stu-id="0730c-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="0730c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0730c-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="0730c-124">如何使用主题</span><span class="sxs-lookup"><span data-stu-id="0730c-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="0730c-125">ToolTip 概述</span><span class="sxs-lookup"><span data-stu-id="0730c-125">ToolTip Overview</span></span>](tooltip-overview.md)
