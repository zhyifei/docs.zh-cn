---
title: Popup 放置行为
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 063b309ebaf0944787ce40725eed250e59f09dff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176755"
---
# <a name="popup-placement-behavior"></a>Popup 放置行为
控件<xref:System.Windows.Controls.Primitives.Popup>在浮动在应用程序上的独立窗口中显示内容。 可以使用<xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>、 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>、 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>、 和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性指定相对于控件、鼠标或屏幕的位置。  这些属性协同工作，使您能够灵活地指定 的位置<xref:System.Windows.Controls.Primitives.Popup>。  
  
> [!NOTE]
> <xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ContextMenu>类还定义了这五个属性，并且的行为类似。  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>定位 Popup  
 位置<xref:System.Windows.Controls.Primitives.Popup>可以相对于 或<xref:System.Windows.UIElement>相对于整个屏幕。  下面的示例创建四<xref:System.Windows.Controls.Primitives.Popup>个控件，它们与<xref:System.Windows.UIElement>_，在本例中是图像。 所有<xref:System.Windows.Controls.Primitives.Popup>控件的属性<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>都设置为`image1`，但每个<xref:System.Windows.Controls.Primitives.Popup>控件都具有不同的放置属性的值。  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 下图显示了图像和<xref:System.Windows.Controls.Primitives.Popup>控件  
  
 ![带有四个 Popup 控件的图像](./media/popup-placement-behavior/popup-placement-intro.png "带四个弹出窗口的图像")
  
 此<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>简单示例演示如何设置 和<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性，但通过使用<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>和<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A><xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性，您可以更控制 的位置。 <xref:System.Windows.Controls.Primitives.Popup>  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>术语定义：Popup 解析  
 以下术语<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>有助于了解 、 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>、 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>、 和<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A><xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性如何相互关联以及 ： <xref:System.Windows.Controls.Primitives.Popup>  
  
- “目标对象”  
  
- 目标区域  
  
- 目标原点  
  
- Popup 对齐点  
  
 这些术语提供了一种方便的方式来引用 它<xref:System.Windows.Controls.Primitives.Popup>与之关联的 控件的各个方面。  
  
### <a name="target-object"></a>目标对象  
 *目标对象*是 与其关联的元素<xref:System.Windows.Controls.Primitives.Popup>。 如果设置了<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>该属性，它将指定目标对象。  如果未<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>设置，并且<xref:System.Windows.Controls.Primitives.Popup>有父级，则父对象是目标对象。  如果没有<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>值，也没有父对象，则没有目标对象，<xref:System.Windows.Controls.Primitives.Popup>并且相对于屏幕定位。  
  
 下面的示例创建<xref:System.Windows.Controls.Primitives.Popup>作为 的 子级<xref:System.Windows.Controls.Canvas>的 。  该示例未在<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>上设置 属性<xref:System.Windows.Controls.Primitives.Popup>。 的<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>默认值为<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>，因此<xref:System.Windows.Controls.Primitives.Popup>显示在 的<xref:System.Windows.Controls.Canvas>下面。  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 下图显示 相对于<xref:System.Windows.Controls.Primitives.Popup>定位 的 。 <xref:System.Windows.Controls.Canvas>  
  
 ![没有 PlacementTarget 的 Popup 控件](./media/popup-placement-behavior/popup-placement-no-placement-target.png "没有放置目标的弹出窗口。")  

 下面的示例创建 一<xref:System.Windows.Controls.Primitives.Popup>个 ， 是<xref:System.Windows.Controls.Canvas>的子项，但这次<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>设置为`ellipse1`， 因此弹出窗口显示在 下面<xref:System.Windows.Shapes.Ellipse>。  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 下图显示 相对于<xref:System.Windows.Controls.Primitives.Popup>定位 的 。 <xref:System.Windows.Shapes.Ellipse>  
  
 ![相对于椭圆形定位的 Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "具有 PlacementTarget 的 Popup")
  
> [!NOTE]
> 对于<xref:System.Windows.Controls.ToolTip>， 的<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>默认值为<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>。  对于<xref:System.Windows.Controls.ContextMenu>， 的<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>默认值为<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>。 这些值将在后面的“属性如何协同工作”部分中进行说明。  
  
### <a name="target-area"></a>目标区域  
 *目标区域*是 屏幕上<xref:System.Windows.Controls.Primitives.Popup>相对的区域。 在前面的示例中，<xref:System.Windows.Controls.Primitives.Popup>与目标对象的边界对齐，但在某些情况下，<xref:System.Windows.Controls.Primitives.Popup>即使<xref:System.Windows.Controls.Primitives.Popup>具有目标对象，也会与其他边界对齐。  如果设置了<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>该属性，则目标区域与目标对象的边界不同。  
  
 下面的示例创建两<xref:System.Windows.Controls.Canvas>个对象，每个对象包含<xref:System.Windows.Shapes.Rectangle>和<xref:System.Windows.Controls.Primitives.Popup>。  在这两种情况下，的目标对象<xref:System.Windows.Controls.Primitives.Popup>是 。 <xref:System.Windows.Controls.Canvas> 第<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Canvas>一<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>个集具有集，其<xref:System.Windows.Rect.X%2A>、<xref:System.Windows.Rect.Y%2A><xref:System.Windows.Rect.Width%2A>和<xref:System.Windows.Rect.Height%2A>属性分别设置为 50、50、50 和 100。 第<xref:System.Windows.Controls.Primitives.Popup>二<xref:System.Windows.Controls.Canvas>个没有集<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>。  因此，<xref:System.Windows.Controls.Primitives.Popup>第一个位于 下方，<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>第二<xref:System.Windows.Controls.Primitives.Popup>个位于 的<xref:System.Windows.Controls.Canvas>下方。 每个<xref:System.Windows.Controls.Canvas>还包含与<xref:System.Windows.Shapes.Rectangle>第<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>一<xref:System.Windows.Controls.Primitives.Popup>个 具有相同的边界。  请注意，<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>不会在应用程序中创建可见元素，该示例创建<xref:System.Windows.Shapes.Rectangle>表示 的<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>。  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 下图显示前面示例的结果。  
  
 ![具有和没有 PlacementRectangle 的 Popup](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "弹出窗口带和没有放置矩形。")  

### <a name="target-origin-and-popup-alignment-point"></a>目标原点和目标对齐点  
 *目标原点*和 *Popup 对齐点*分别是目标区域和 Popup 上用于定位定位的参照点。 可以使用 和<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A><xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性从目标区域偏移弹出窗口。  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>相对于目标原点和弹出对齐<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>点。 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性的值确定目标原点和弹出对齐点的位置。  
  
 下面的示例创建 和<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>将 和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性设置为 20。  属性<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>（默认值），因此目标原点是目标区域的左下角，弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>左上角。  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 下图显示前面示例的结果。  
  
 ![使用目标原点对齐点的 Popup 放置](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "带水平偏移和垂直偏移的弹出窗口。")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>属性如何协同工作  
 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A><xref:System.Windows.Controls.Primitives.Popup.Placement%2A>的值和 需要一起考虑，以找出正确的目标区域、目标原点和<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>弹出对齐点。  例如，如果 值<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>为<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>，则没有目标对象，<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>则忽略 ，并且目标区域是鼠标指针的边界。 另一<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>方面，如果 为<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>，<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或 父项确定目标对象<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>并确定目标区域。  
  
 下表描述了目标对象、目标区域、目标原点和弹出对齐点，并指示是否<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A><xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>和用于每个<xref:System.Windows.Controls.Primitives.PlacementMode>枚举值。  
  
|PlacementMode|“目标对象”|目标区域|目标原点|Popup 对齐点|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|不适用。 已忽略 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>。|屏幕，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>设置了。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于屏幕的。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|不适用。 已忽略 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>。|屏幕，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>设置了。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于屏幕的。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父项。|目标对象，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>已设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于目标对象的。|目标区域的左下角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父项。|目标对象，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>已设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于目标对象的。|目标区域的中心。|的中心<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父项。|目标对象，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>已设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于目标对象的。|由 定义<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>。|由 定义<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父项。|目标对象，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>已设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于目标对象的。|目标区域的左上角。|的右上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|不适用。 已忽略 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>。|鼠标指针的边界。 已忽略 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>。|目标区域的左下角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|不适用。 已忽略 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>。|鼠标指针的边界。 已忽略 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父项。|目标对象，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>已设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于目标对象的。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父项。|目标对象，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>已设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于目标对象的。|目标区域的左上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父项。|目标对象，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>已设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于目标对象的。|目标区域的右上角。|的左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父项。|目标对象，或者如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>已设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>是相对于目标对象的。|目标区域的左上角。|的左下角<xref:System.Windows.Controls.Primitives.Popup>。|  
  
 下图显示了 每个<xref:System.Windows.Controls.Primitives.Popup><xref:System.Windows.Controls.Primitives.PlacementMode>值的目标区域、目标原点和弹出对齐点。 在每个图形中，目标区域为黄色，并且<xref:System.Windows.Controls.Primitives.Popup>为蓝色。  
  
 ![采用 Absolute 或 AbsolutePoint 定位的 Popup](./media/popup-placement-behavior/popup-placement-absolute.png "放置是绝对或绝对点。")
  
 ![采用 Bottom 定位的 Popup](./media/popup-placement-behavior/popup-placement-bottom.png "放置是底部。")
  
 ![采用 Center 定位的 Popup](./media/popup-placement-behavior/popup-placement-center.png "放置是中心。")
  
 ![采用 Left 定位的 Popup](./media/popup-placement-behavior/popup-placement-left.png "放置为"左"。")
  
 ![采用 Mouse 定位的 Popup](./media/popup-placement-behavior/popup-placement-mouse.png "放置是鼠标。")  
  
 ![采用 MousePoint 定位的 Popup](./media/popup-placement-behavior/popup-placement-mousepoint.png "放置是鼠标点。")  
  
 ![采用 Relative 或 RelativePoint 定位的 Popup](./media/popup-placement-behavior/popup-placement-relative.png "放置是相对点或相对点。")
  
 ![采用 Right 定位的 Popup](./media/popup-placement-behavior/popup-placement-right.png "放置是正确的。")
  
 ![采用 Top 定位的 Popup](./media/popup-placement-behavior/popup-placement-top.png "位置是顶部。")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>当 Popup 到达屏幕边缘时  
 出于安全原因，<xref:System.Windows.Controls.Primitives.Popup>无法隐藏在屏幕边缘。 遇到屏幕边缘时<xref:System.Windows.Controls.Primitives.Popup>会发生以下三种情况之一：  
  
- 弹出窗口沿屏幕边缘重新调整自身，这将遮盖 。 <xref:System.Windows.Controls.Primitives.Popup>  
  
- Popup 使用其他 Popup 对齐点。  
  
- Popup 使用其他目标原点和 Popup 对齐点。  
  
 将在本部分后面进一步介绍这些选项。  
  
 遇到屏幕边缘<xref:System.Windows.Controls.Primitives.Popup>时的行为取决于<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性的值以及弹出窗口遇到的屏幕边缘。 下表总结了当<xref:System.Windows.Controls.Primitives.Popup>遇到每个<xref:System.Windows.Controls.Primitives.PlacementMode>值的屏幕边缘时的行为。  
  
|PlacementMode|上边缘|下边缘|左边缘|右边缘|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|与上边缘对齐。|弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>左下角。|与左边缘对齐。|弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|与上边缘对齐。|目标原点更改为目标区域的左上角，弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>左下角。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|与上边缘对齐。|与下边缘对齐。|目标原点更改为目标区域的右上角，弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>左上角。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|与上边缘对齐。|目标原点更改为目标区域的左上角（鼠标指针的边界），弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>左下角。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|与上边缘对齐。|弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>左下角。|与左边缘对齐。|Popup 对齐点更改为 Popup 的右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|与上边缘对齐。|弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>左下角。|与左边缘对齐。|Popup 对齐点更改为 Popup 的右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|目标原点更改为目标区域的左上角，弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|目标原点更改为目标区域的左下角，弹出对齐点将更改为 的<xref:System.Windows.Controls.Primitives.Popup>左上角。 实际上，这与 时<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>相同。 <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
  
### <a name="aligning-to-the-screen-edge"></a>对屏幕边缘对齐  
 A<xref:System.Windows.Controls.Primitives.Popup>可以通过重新定位自身来与屏幕边缘对齐，以便整个屏幕<xref:System.Windows.Controls.Primitives.Popup>可见。  发生这种情况时，目标原点和弹出对齐点之间的距离可能与 和<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A><xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>的值不同。 当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A><xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>是<xref:System.Windows.Controls.Primitives.PlacementMode.Center>、<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>或<xref:System.Windows.Controls.Primitives.Popup>时，将自身与每个屏幕边缘对齐。  例如，<xref:System.Windows.Controls.Primitives.Popup>假设 a 已<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>设置为<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>100。  如果屏幕的下边缘隐藏 全部或部分<xref:System.Windows.Controls.Primitives.Popup>，则沿屏幕底部边缘的<xref:System.Windows.Controls.Primitives.Popup>重新定位自身，目标原点和弹出对齐点之间的垂直距离小于 100。 下图演示了此情况。  
  
 ![与屏幕边缘对齐的 Popup](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "弹出窗口与屏幕边缘对齐。")
  
### <a name="changing-the-popup-alignment-point"></a>更改 Popup 对齐点  
 如果<xref:System.Windows.Controls.Primitives.Popup.Placement%2A><xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>是<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>、<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>或 ，则弹出窗口遇到底部或右屏幕边缘时，弹出窗口对齐点将发生变化。  
  
 下图演示了当底部屏幕边缘隐藏 的全部或部分<xref:System.Windows.Controls.Primitives.Popup>时，弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>左下角。  
  
 ![由于底部屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "弹出窗口遇到屏幕的下边缘并更改弹出对齐点。")  

 下图演示了当 被隐藏在<xref:System.Windows.Controls.Primitives.Popup>右屏幕边缘时，弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>右上角。  
  
 ![由于屏幕边缘而产生的新 Popup 对齐点](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "弹出窗口遇到屏幕的右边缘并更改弹出对齐点。")
  
 如果<xref:System.Windows.Controls.Primitives.Popup>遇到屏幕底部和右侧边缘，则弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>右下角。  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>更改目标原点和 Popup 对齐点  
 如果<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>遇到<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>特定<xref:System.Windows.Controls.Primitives.PlacementMode.Left>屏幕<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>边缘<xref:System.Windows.Controls.Primitives.PlacementMode.Right>，<xref:System.Windows.Controls.Primitives.PlacementMode.Top>则目标原点和弹出对齐点何时更改。  导致位置更改的屏幕边缘取决于该<xref:System.Windows.Controls.Primitives.PlacementMode>值。  
  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>下图演示了当和<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom><xref:System.Windows.Controls.Primitives.Popup>遇到下屏边缘时，目标原点是目标区域的左上角，弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>左下角。  
  
 ![由于底部屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "放置是底部，弹出窗口遇到屏幕的底部边缘。")
  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>下图演示了当和<xref:System.Windows.Controls.Primitives.PlacementMode.Left><xref:System.Windows.Controls.Primitives.Popup>遇到左屏幕边缘时，目标原点是目标区域的右上角，弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>左上角。  
  
 ![由于左侧屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "放置是"左"，弹出窗口遇到屏幕的左边缘。")  
  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>下图演示了当和<xref:System.Windows.Controls.Primitives.PlacementMode.Right><xref:System.Windows.Controls.Primitives.Popup>遇到右屏幕边缘时，目标原点是目标区域的左上角，弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>右上角。  
  
 ![由于右侧屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "放置正确，弹出窗口遇到屏幕的右边缘。")  

 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>下图演示了当和<xref:System.Windows.Controls.Primitives.PlacementMode.Top><xref:System.Windows.Controls.Primitives.Popup>遇到顶部屏幕边缘时，目标原点是目标区域的左下角，弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>左上角。  
  
 ![由于顶部屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "放置是顶部，弹出窗口遇到屏幕的上边缘。")  
  
 <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>下图演示了当和<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse><xref:System.Windows.Controls.Primitives.Popup>遇到底部屏幕边缘时，目标原点是目标区域的左上角（鼠标指针的边界），弹出对齐点是 的<xref:System.Windows.Controls.Primitives.Popup>左下角。  
  
 ![由于鼠标接近屏幕边缘而产生的新对齐点](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "放置是鼠标，弹出窗口遇到屏幕的底部边缘。")
  
### <a name="customizing-popup-placement"></a>自定义 Popup 放置  
 通过将<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>，可以自定义目标原点和弹出对齐点。 然后定义一<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>个委托，该委托返回 一<xref:System.Windows.Controls.Primitives.Popup>组可能的放置点和主轴（按首选项顺序排列） 。 所选显示 的最大<xref:System.Windows.Controls.Primitives.Popup>部分的点。  <xref:System.Windows.Controls.Primitives.Popup>如果<xref:System.Windows.Controls.Primitives.Popup>隐藏在屏幕边缘， 则 会自动调整 的位置。 有关示例，请参阅[指定自定义 Popup 位置](how-to-specify-a-custom-popup-position.md)。  
  
## <a name="see-also"></a>另请参阅

- [Popup 放置示例](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
