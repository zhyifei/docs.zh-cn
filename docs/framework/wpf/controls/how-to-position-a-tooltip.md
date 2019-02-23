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
ms.openlocfilehash: 985c9b7737d979937837d7184f9b96f226ec73c3
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746910"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="59b9b-102">如何：定位 ToolTip</span><span class="sxs-lookup"><span data-stu-id="59b9b-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="59b9b-103">此示例演示如何在屏幕上指定的工具提示的位置。</span><span class="sxs-lookup"><span data-stu-id="59b9b-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b9b-104">示例</span><span class="sxs-lookup"><span data-stu-id="59b9b-104">Example</span></span>  
 <span data-ttu-id="59b9b-105">可以使用一组中都定义的五个属性来定位 tooltip<xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ToolTipService>类。</span><span class="sxs-lookup"><span data-stu-id="59b9b-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="59b9b-106">下表显示了这两个五个属性集，并提供指向其根据类的参考文档。</span><span class="sxs-lookup"><span data-stu-id="59b9b-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="59b9b-107">类根据相应的工具提示属性</span><span class="sxs-lookup"><span data-stu-id="59b9b-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="59b9b-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> 类属性</span><span class="sxs-lookup"><span data-stu-id="59b9b-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="59b9b-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> 类属性</span><span class="sxs-lookup"><span data-stu-id="59b9b-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="59b9b-110">如果您通过使用定义的工具提示内容<xref:System.Windows.Controls.ToolTip>对象，可以使用其中一个类的属性; 但是，<xref:System.Windows.Controls.ToolTipService>属性优先。</span><span class="sxs-lookup"><span data-stu-id="59b9b-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="59b9b-111">使用<xref:System.Windows.Controls.ToolTipService>属性未定义为的工具提示<xref:System.Windows.Controls.ToolTip>对象。</span><span class="sxs-lookup"><span data-stu-id="59b9b-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="59b9b-112">下图显示如何使用这些属性来定位 tooltip。</span><span class="sxs-lookup"><span data-stu-id="59b9b-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="59b9b-113">虽然，则[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]在这些说明中的示例演示如何设置所定义的属性<xref:System.Windows.Controls.ToolTip>类的相应属性<xref:System.Windows.Controls.ToolTipService>类遵循相同的布局规则。</span><span class="sxs-lookup"><span data-stu-id="59b9b-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="59b9b-114">有关位置属性的可能值的详细信息，请参阅[Popup 放置行为](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="59b9b-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="59b9b-115">![工具提示放置](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="59b9b-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="59b9b-116">通过使用放置属性的工具提示放置</span><span class="sxs-lookup"><span data-stu-id="59b9b-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="59b9b-117">![通过使用放置矩形 tooltip](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="59b9b-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="59b9b-118">通过使用放置和 PlacementRectangle 属性的工具提示放置</span><span class="sxs-lookup"><span data-stu-id="59b9b-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="59b9b-119">![ToolTip 定位示意图](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="59b9b-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="59b9b-120">通过使用放置、 PlacementRectangle 和偏移量属性的工具提示放置</span><span class="sxs-lookup"><span data-stu-id="59b9b-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="59b9b-121">下面的示例演示如何使用<xref:System.Windows.Controls.ToolTip>属性来指定其内容的工具提示的位置<xref:System.Windows.Controls.ToolTip>对象。</span><span class="sxs-lookup"><span data-stu-id="59b9b-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="59b9b-122">下面的示例演示如何使用<xref:System.Windows.Controls.ToolTipService>属性来指定其内容不是一个工具提示的位置<xref:System.Windows.Controls.ToolTip>对象。</span><span class="sxs-lookup"><span data-stu-id="59b9b-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="59b9b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="59b9b-123">See also</span></span>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="59b9b-124">帮助主题</span><span class="sxs-lookup"><span data-stu-id="59b9b-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [<span data-ttu-id="59b9b-125">ToolTip 概述</span><span class="sxs-lookup"><span data-stu-id="59b9b-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
