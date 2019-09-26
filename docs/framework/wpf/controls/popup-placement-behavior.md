---
title: Popup 放置行为
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: ca984aa724cf3f076d6073aa8b8179abfb91d26c
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "69951736"
---
# <a name="popup-placement-behavior"></a>Popup 放置行为
<xref:System.Windows.Controls.Primitives.Popup>控件在单独的窗口中显示内容，该窗口浮动在应用程序上。 通过<xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>使用、、 、和<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>属性，可以指定相对于控件、鼠标或屏幕的位置。<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>  这些属性一起使用，使你可以灵活地指定的位置<xref:System.Windows.Controls.Primitives.Popup>。  
  
> [!NOTE]
> <xref:System.Windows.Controls.ToolTip> 和<xref:System.Windows.Controls.ContextMenu>类还定义这五个属性，行为类似。  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>定位 Popup  
 的位置<xref:System.Windows.Controls.Primitives.Popup>可以相对<xref:System.Windows.UIElement>于或整个屏幕。  下面的示例创建了<xref:System.Windows.Controls.Primitives.Popup>四个相对于的<xref:System.Windows.UIElement>控件（在本例中为图像）。 所有控件的<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>属性都设置为`image1`，但对于 "位置<xref:System.Windows.Controls.Primitives.Popup> " 属性，每个控件都有不同的值。 <xref:System.Windows.Controls.Primitives.Popup>  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 下图显示了图像和<xref:System.Windows.Controls.Primitives.Popup>控件  
  
 ![带有四个 popup 控件的图像](./media/popup-placement-behavior/popup-placement-intro.png "带有四个弹出窗口的图像")    
  
 这个简单的示例演示如何设置<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>和<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>，但通过使用、 <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性，您可以更好地控制所定位的<xref:System.Windows.Controls.Primitives.Popup>位置。  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>术语的定义：Popup 的剖析  
 以下术语<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>有助于了解<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.Popup>、、、和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性彼此之间的关系，以及如何相互关联： <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>  
  
- 目标对象  
  
- 目标区域  
  
- 目标原点  
  
- Popup 对齐点  
  
 这些术语提供了一种便捷的方法来引用的<xref:System.Windows.Controls.Primitives.Popup>各个方面以及它所关联的控件。  
  
### <a name="target-object"></a>目标对象  
 *目标对象*是与关联的元素<xref:System.Windows.Controls.Primitives.Popup> 。 如果设置<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>了属性，它将指定目标对象。  如果<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>未设置， <xref:System.Windows.Controls.Primitives.Popup>并且具有父，则父对象是目标对象。  如果没有任何<xref:System.Windows.Controls.Primitives.Popup> 值，并且没有父对象，则没有目标对象，并且相对于<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>屏幕进行定位。  
  
 下面的示例创建一个<xref:System.Windows.Controls.Primitives.Popup> ，它是的子级。 <xref:System.Windows.Controls.Canvas>  该示例不在<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup>上设置属性。 的默认值<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>为<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType> <xref:System.Windows.Controls.Primitives.Popup> ，<xref:System.Windows.Controls.Canvas>因此显示在下方。  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 下图显示<xref:System.Windows.Controls.Primitives.Popup>了相对于的<xref:System.Windows.Controls.Canvas>定位。  
  
 ![无 system.windows.controls.primitives.popup.placementtarget 的 Popup 控件](./media/popup-placement-behavior/popup-placement-no-placement-target.png "无 system.windows.controls.primitives.popup.placementtarget 的弹出窗口。")  

 下面的示例创建一个<xref:System.Windows.Controls.Primitives.Popup> ，它是的子<xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> ，但这一次将设置为`ellipse1`，因此，popup 显示在<xref:System.Windows.Shapes.Ellipse>下方。  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 下图显示<xref:System.Windows.Controls.Primitives.Popup>了相对于的<xref:System.Windows.Shapes.Ellipse>定位。  
  
 ![相对于椭圆定位的 Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "带 system.windows.controls.primitives.popup.placementtarget 的 Popup")    
  
> [!NOTE]
> 对于<xref:System.Windows.Controls.ToolTip>，的默认<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>值为<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>。  对于<xref:System.Windows.Controls.ContextMenu>，的默认<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>值为<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>。 这些值将在后面的“属性如何协同工作”部分中进行说明。  
  
### <a name="target-area"></a>目标区域  
 *目标区域*是屏幕<xref:System.Windows.Controls.Primitives.Popup>上相关的区域。 在前面的示例中， <xref:System.Windows.Controls.Primitives.Popup>与目标对象的边界对齐，但在某些情况下<xref:System.Windows.Controls.Primitives.Popup> ，即使<xref:System.Windows.Controls.Primitives.Popup>有目标对象，也与其他边界对齐。  如果设置<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>了属性，则目标区域不同于目标对象的边界。  
  
 下面的示例创建两<xref:System.Windows.Controls.Canvas>个对象，每个对象<xref:System.Windows.Shapes.Rectangle>都包含<xref:System.Windows.Controls.Primitives.Popup>一个和一个。  在这两种情况下，的目标<xref:System.Windows.Controls.Primitives.Popup>对象<xref:System.Windows.Controls.Canvas>是。 <xref:System.Windows.Rect.X%2A>第一<xref:System.Windows.Controls.Canvas> 项具有<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>集，其、<xref:System.Windows.Rect.Y%2A> 、<xref:System.Windows.Rect.Width%2A>和属性<xref:System.Windows.Rect.Height%2A>分别设置为50、50、50和100。 <xref:System.Windows.Controls.Primitives.Popup> 在<xref:System.Windows.Controls.Primitives.Popup>第二个<xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>中，没有设置。  因此，第<xref:System.Windows.Controls.Primitives.Popup>一个位于<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>下， <xref:System.Windows.Controls.Canvas>第二个<xref:System.Windows.Controls.Primitives.Popup>位于下。 每<xref:System.Windows.Controls.Canvas>个还<xref:System.Windows.Shapes.Rectangle>包含与第<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup>一个具有相同边界的。  请注意， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>不会在应用程序中创建可见的元素; 此示例将<xref:System.Windows.Shapes.Rectangle>创建一个来<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>表示。  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 下图显示前面示例的结果。  
  
 ![具有和没有 system.windows.controls.primitives.popup.placementrectangle 的 Popup](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "具有和没有 system.windows.controls.primitives.popup.placementrectangle 的 Popup。")  

### <a name="target-origin-and-popup-alignment-point"></a>目标原点和目标对齐点  
 *目标原点*和 *Popup 对齐点*分别是目标区域和 Popup 上用于定位定位的参照点。 您可以使用<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性来从目标区域偏移弹出窗口。  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> 和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>相对于目标原点和 popup 对齐点。 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性的值确定目标原点和 popup 对齐点的位置。  
  
 下面的示例创建一个<xref:System.Windows.Controls.Primitives.Popup> ，并<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>将和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性设置为20。  属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> （默认值），因此目标原点是目标区域的左下角，popup 对齐点是的左上角<xref:System.Windows.Controls.Primitives.Popup>。 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 下图显示前面示例的结果。  
  
 ![与目标原点对齐点的 Popup 放置](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "带 system.windows.controls.primitives.popup.horizontaloffset 和 system.windows.controls.primitives.popup.verticaloffset 的弹出窗口。")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>属性如何协同工作  
 、 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>和的值都需要组合在一起，以确定正确的目标区域、目标原点和popup对齐点。<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>  例如，如果的<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>值为<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>，则没有目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>将忽略，并且目标区域是鼠标指针的边界。 另一方面，如果<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>为<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>， <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>则或父级确定目标对象并<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>确定目标区域。  
  
 下表介绍目标对象、目标区域、目标原点和 popup 对齐点，并指示是否<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>将和<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>用于每个<xref:System.Windows.Controls.Primitives.PlacementMode>枚举值。  
  
|PlacementMode|目标对象|目标区域|目标原点|Popup 对齐点|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|不适用。 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>将被忽略。|屏幕或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> （如果已设置）。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于屏幕。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|不适用。 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>将被忽略。|屏幕或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> （如果已设置）。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于屏幕。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父。|目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果已设置，则为。  是<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象的。|目标区域的左下角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父。|目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果已设置，则为。  是<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象的。|目标区域的中心。|的中心<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父。|目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果已设置，则为。  是<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象的。|由<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>定义。|由<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>定义。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父。|目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果已设置，则为。  是<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象的。|目标区域的左上角。|的右上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|不适用。 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>将被忽略。|鼠标指针的边界。 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>将被忽略。|目标区域的左下角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|不适用。 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>将被忽略。|鼠标指针的边界。 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>将被忽略。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父。|目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果已设置，则为。  是<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象的。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父。|目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果已设置，则为。  是<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象的。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父。|目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果已设置，则为。  是<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象的。|目标区域的右上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父。|目标对象， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果已设置，则为。  是<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象的。|目标区域的左上角。|的左下角<xref:System.Windows.Controls.Primitives.Popup>。|  
  
 下图显示每个<xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.PlacementMode>值的、目标区域、目标原点和 popup 对齐点。 在每个图中，目标区域为黄色， <xref:System.Windows.Controls.Primitives.Popup>为蓝色。  
  
 ![具有绝对或 absolutepoint 定位定位的 Popup](./media/popup-placement-behavior/popup-placement-absolute.png "放置是绝对的或 absolutepoint 定位的。")    
  
 ![靠下放置的弹出窗口](./media/popup-placement-behavior/popup-placement-bottom.png "放置为底端。")   
  
 ![带有中心位置的弹出窗口](./media/popup-placement-behavior/popup-placement-center.png "放置是中心。")    
  
 ![具有左侧位置的弹出窗口](./media/popup-placement-behavior/popup-placement-left.png "位置为左。")   
  
 ![带有鼠标定位的 Popup](./media/popup-placement-behavior/popup-placement-mouse.png "位置为鼠标。")  
  
 ![带有 mousepoint 定位定位的 Popup](./media/popup-placement-behavior/popup-placement-mousepoint.png "放置是 mousepoint 定位的。")  
  
 ![具有相对或 relativepoint 定位位置的 Popup](./media/popup-placement-behavior/popup-placement-relative.png "位置是相对的或 relativepoint 定位的。")    
  
 ![带有右位置的弹出窗口](./media/popup-placement-behavior/popup-placement-right.png "放置是正确的。")    
  
 ![带有顶部位置的弹出窗口](./media/popup-placement-behavior/popup-placement-top.png "位置为 Top。")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>当 Popup 到达屏幕边缘时  
 出于安全原因， <xref:System.Windows.Controls.Primitives.Popup>无法通过屏幕边缘隐藏。 当<xref:System.Windows.Controls.Primitives.Popup>遇到屏幕边缘时，会出现以下三种情况之一：  
  
- 弹出式窗口边缘的 popup，将会掩盖<xref:System.Windows.Controls.Primitives.Popup>。  
  
- Popup 使用其他 Popup 对齐点。  
  
- Popup 使用其他目标原点和 Popup 对齐点。  
  
 将在本部分后面进一步介绍这些选项。  
  
 <xref:System.Windows.Controls.Primitives.Popup>当遇到屏幕边缘时的行为取决于<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性的值以及 popup 遇到的屏幕边缘。 下表总结了在<xref:System.Windows.Controls.Primitives.Popup>遇到每个<xref:System.Windows.Controls.Primitives.PlacementMode>值的屏幕边缘时的行为。  
  
|PlacementMode|上边缘|下边缘|左边缘|右边缘|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|与上边缘对齐。|Popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|Popup 对齐点更改为的右上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|与上边缘对齐。|目标原点更改为目标区域的左上角，而 popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|与上边缘对齐。|与下边缘对齐。|目标原点更改为目标区域的右上角，popup 对齐点更改为的左上角<xref:System.Windows.Controls.Primitives.Popup>。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|与上边缘对齐。|目标原点更改为目标区域（鼠标指针的边界）的左上角，而 popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|与上边缘对齐。|Popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|Popup 对齐点更改为 Popup 的右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|与上边缘对齐。|Popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|Popup 对齐点更改为 Popup 的右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|目标原点更改为目标区域的左上角，而 popup 对齐点更改为的<xref:System.Windows.Controls.Primitives.Popup>右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|目标原点更改为目标区域的左下角，popup 对齐点更改为的左上角<xref:System.Windows.Controls.Primitives.Popup>。 实际上，这与在时<xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>相同。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
  
### <a name="aligning-to-the-screen-edge"></a>对屏幕边缘对齐  
 可以通过重新定位自身来使屏幕边缘对齐，使整个<xref:System.Windows.Controls.Primitives.Popup>在屏幕上可见。 <xref:System.Windows.Controls.Primitives.Popup>  出现这种情况时，目标原点和 popup 对齐点之间的距离可能与<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>的值不同。 当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>为<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>、或<xref:System.Windows.Controls.Primitives.PlacementMode.Center>时，<xref:System.Windows.Controls.Primitives.Popup>将自身与每个屏幕边缘对齐。 <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>  例如<xref:System.Windows.Controls.Primitives.Popup> ，假定<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>将设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>并<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>将设置为100。  如果屏幕的下边缘隐藏全部或部分<xref:System.Windows.Controls.Primitives.Popup>，则会在<xref:System.Windows.Controls.Primitives.Popup>屏幕的下边缘重新定位自身，目标原点和 popup 对齐点之间的垂直距离小于100。 下图演示了此情况。  
  
 ![与屏幕边缘对齐的 Popup](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "弹出项与屏幕边缘对齐。")    
  
### <a name="changing-the-popup-alignment-point"></a>更改 Popup 对齐点  
 如果<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>为<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>、 <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>或，则当popup遇到下边缘或右边缘时，popup对齐点将发生更改。<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>  
  
 下图演示当下屏幕边缘隐藏全部或部分<xref:System.Windows.Controls.Primitives.Popup>时，popup 对齐点是的左下角。 <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![由于底部屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup 到达屏幕下边缘，并更改 popup 对齐点。")  

 下图演示当右屏幕边缘<xref:System.Windows.Controls.Primitives.Popup>隐藏时，popup 对齐点是的右上角。 <xref:System.Windows.Controls.Primitives.Popup>  
  
 ![由于屏幕边缘而产生的新 popup 对齐点](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup 遇到屏幕的右边缘，并更改 Popup 对齐点。")    
  
 如果遇到屏幕的下边缘和右边缘，则 popup 对齐点为的右下角<xref:System.Windows.Controls.Primitives.Popup>。 <xref:System.Windows.Controls.Primitives.Popup>  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>更改目标原点和 Popup 对齐点  
 当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>为<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>、 、、<xref:System.Windows.Controls.Primitives.PlacementMode.Left>或<xref:System.Windows.Controls.Primitives.PlacementMode.Top>时，如果遇到某个屏幕边缘，则目标原点和 popup 对齐点将发生变化。 <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> <xref:System.Windows.Controls.Primitives.PlacementMode.Right>  导致位置变化的屏幕边缘取决<xref:System.Windows.Controls.Primitives.PlacementMode>于值。  
  
 下图演示当为<xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>并且<xref:System.Windows.Controls.Primitives.Popup>遇到下边缘屏幕边缘时，目标原点是目标区域的左上角，而 popup 对齐点是该区域的左上角<xref:System.Windows.Controls.Primitives.Popup>。  
  
 ![由于底部屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "放置是底部，并且 popup 到达屏幕的下边缘。")    
  
 下图演示当为<xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Left>并且<xref:System.Windows.Controls.Primitives.Popup>遇到屏幕左边缘时，目标原点是目标区域的右上角，popup 对齐点是的左上角。 <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![由于左侧屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "放在左侧，并且 popup 到达屏幕的左边缘。")  
  
 下图演示当为<xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Right>并且<xref:System.Windows.Controls.Primitives.Popup>遇到屏幕右边缘时，目标原点是目标区域的左上角，而 popup 对齐点是位于的右上角<xref:System.Windows.Controls.Primitives.Popup>。  
  
 ![由于右侧屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "放置是正确的，并且 popup 到达屏幕右边缘。")  

 下图演示当为<xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Top>并且<xref:System.Windows.Controls.Primitives.Popup>遇到顶部屏幕边缘时，目标原点是目标区域的左下角，popup 对齐点是的左上角<xref:System.Windows.Controls.Primitives.Popup>。  
  
 ![由于顶部屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "放置为顶部，并且 popup 到达屏幕的上边缘。")  
  
 下图演示当为<xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>并且<xref:System.Windows.Controls.Primitives.Popup>遇到底部屏幕边缘时，目标原点是目标区域（鼠标指针的边界）和弹出项对齐方式的左上角。point 是的左下角<xref:System.Windows.Controls.Primitives.Popup>。  
  
 ![由于鼠标接近屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "放置是鼠标，并且 popup 到达屏幕的下边缘。")    
  
### <a name="customizing-popup-placement"></a>自定义 Popup 放置  
 您可以通过将<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为来<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>自定义目标原点和 popup 对齐点。 然后，定义<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>一个委托，该委托返回一组可能的位置点和主轴（按优先顺序排列<xref:System.Windows.Controls.Primitives.Popup>）。 将选择显示的最大部分<xref:System.Windows.Controls.Primitives.Popup>的点。  如果屏幕边缘隐藏<xref:System.Windows.Controls.Primitives.Popup> ，将自动调整的位置。 <xref:System.Windows.Controls.Primitives.Popup> 有关示例，请参阅[指定自定义 Popup 位置](how-to-specify-a-custom-popup-position.md)。  
  
## <a name="see-also"></a>请参阅

- [Popup 放置示例](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
