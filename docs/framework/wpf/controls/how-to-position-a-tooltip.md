---
title: "如何：定位 ToolTip"
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
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62e86f2adfbe8f8aac000d653e955555c7def750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="99ac6-102">如何：定位 ToolTip</span><span class="sxs-lookup"><span data-stu-id="99ac6-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="99ac6-103">此示例演示如何在屏幕上指定的工具提示的位置。</span><span class="sxs-lookup"><span data-stu-id="99ac6-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99ac6-104">示例</span><span class="sxs-lookup"><span data-stu-id="99ac6-104">Example</span></span>  
 <span data-ttu-id="99ac6-105">您可以使用一组中都定义的五个属性来定位工具提示<xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ToolTipService>类。</span><span class="sxs-lookup"><span data-stu-id="99ac6-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="99ac6-106">下表显示五个属性这两个集，并提供指向其根据类的参考文档。</span><span class="sxs-lookup"><span data-stu-id="99ac6-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="99ac6-107">类根据相应的工具提示属性</span><span class="sxs-lookup"><span data-stu-id="99ac6-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="99ac6-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>类属性</span><span class="sxs-lookup"><span data-stu-id="99ac6-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="99ac6-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>类属性</span><span class="sxs-lookup"><span data-stu-id="99ac6-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="99ac6-110">如果您通过使用定义的工具提示的内容<xref:System.Windows.Controls.ToolTip>对象时，你可以使用其中一个类的属性; 但是，<xref:System.Windows.Controls.ToolTipService>属性优先。</span><span class="sxs-lookup"><span data-stu-id="99ac6-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="99ac6-111">使用<xref:System.Windows.Controls.ToolTipService>属性未定义为的工具提示<xref:System.Windows.Controls.ToolTip>对象。</span><span class="sxs-lookup"><span data-stu-id="99ac6-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="99ac6-112">下图显示如何使用这些属性来定位工具提示。</span><span class="sxs-lookup"><span data-stu-id="99ac6-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="99ac6-113">尽管、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]在这些说明中的示例演示如何设置的属性定义的<xref:System.Windows.Controls.ToolTip>类的对应属性<xref:System.Windows.Controls.ToolTipService>类遵循相同的布局规则。</span><span class="sxs-lookup"><span data-stu-id="99ac6-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="99ac6-114">有关放置属性的可能值的详细信息，请参阅[弹出项放置行为](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="99ac6-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="99ac6-115">![ToolTip 定位](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="99ac6-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="99ac6-116">ToolTip 定位使用放置属性</span><span class="sxs-lookup"><span data-stu-id="99ac6-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="99ac6-117">![通过使用定位矩形 tooltip](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="99ac6-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="99ac6-118">通过使用放置和 PlacementRectangle 属性的 ToolTip 定位</span><span class="sxs-lookup"><span data-stu-id="99ac6-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="99ac6-119">![ToolTip 定位示意图](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="99ac6-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="99ac6-120">通过使用放置、 PlacementRectangle 和偏移量属性的 ToolTip 定位</span><span class="sxs-lookup"><span data-stu-id="99ac6-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="99ac6-121">下面的示例演示如何使用<xref:System.Windows.Controls.ToolTip>属性以指定其内容的工具提示的位置<xref:System.Windows.Controls.ToolTip>对象。</span><span class="sxs-lookup"><span data-stu-id="99ac6-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="99ac6-122">下面的示例演示如何使用<xref:System.Windows.Controls.ToolTipService>属性以指定其内容不属于的工具提示的位置<xref:System.Windows.Controls.ToolTip>对象。</span><span class="sxs-lookup"><span data-stu-id="99ac6-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="99ac6-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="99ac6-123">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="99ac6-124">帮助主题</span><span class="sxs-lookup"><span data-stu-id="99ac6-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="99ac6-125">ToolTip 概述</span><span class="sxs-lookup"><span data-stu-id="99ac6-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [<span data-ttu-id="99ac6-126">使用 ContextMenuService 和 ToolTipService</span><span class="sxs-lookup"><span data-stu-id="99ac6-126">Use the ContextMenuService and ToolTipService</span></span>](http://msdn.microsoft.com/en-us/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
