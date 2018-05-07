---
title: Popup 放置行为
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 3aef3d7863bc02aa4164b1fc9ef4464fbe799cb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="popup-placement-behavior"></a>Popup 放置行为
A<xref:System.Windows.Controls.Primitives.Popup>控件浮动转移的应用程序的单独窗口中显示内容。 你可以指定的位置<xref:System.Windows.Controls.Primitives.Popup>相对于控件、 鼠标或通过使用屏幕<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>， <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>， <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>，和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性。  这些属性协同工作以使你在指定的位置的灵活地<xref:System.Windows.Controls.Primitives.Popup>。  
  
> [!NOTE]
>  <xref:System.Windows.Controls.ToolTip>和<xref:System.Windows.Controls.ContextMenu>类还定义这些五个属性和行为相似。  
  

  
<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>定位 Popup  
 放置<xref:System.Windows.Controls.Primitives.Popup>可以是相对于<xref:System.Windows.UIElement>或整个屏幕。  下面的示例创建四个<xref:System.Windows.Controls.Primitives.Popup>都与之相关的控件<xref:System.Windows.UIElement>— 在这种情况下，映像中。 所有<xref:System.Windows.Controls.Primitives.Popup>控件具有<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>属性设置为`image1`，但其中每个<xref:System.Windows.Controls.Primitives.Popup>具有不同的位置属性的值。  
  
 [!code-xaml[PopupPositionSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 下图显示的图像和<xref:System.Windows.Controls.Primitives.Popup>控件  
  
 ![具有四个弹出控件的图像](../../../../docs/framework/wpf/controls/media/popupplacementintro.png "PopupPlacementIntro")  
带有四个 Popup 的图像  
  
 这个简单的示例演示如何设置<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>和<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性，但通过使用<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>， <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>，和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性，你可以更多控制在何处<xref:System.Windows.Controls.Primitives.Popup>定位。  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>术语定义：Popup 解析  
 以下术语可了解如何<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>， <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>， <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>，和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性将互相关联起来与<xref:System.Windows.Controls.Primitives.Popup>:  
  
-   目标对象  
  
-   目标区域  
  
-   目标原点  
  
-   Popup 对齐点  
  
 这些条款提供一种简便的方式来指代的各个方面<xref:System.Windows.Controls.Primitives.Popup>以及与之关联的控件。  
  
### <a name="target-object"></a>目标对象  
 *目标对象*是元素的<xref:System.Windows.Controls.Primitives.Popup>与相关联。 如果<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>属性设置，它指定的目标对象。  如果<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>未设置，和<xref:System.Windows.Controls.Primitives.Popup>父级的父级是目标对象。  如果没有任何<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>值和没有父级，没有目标对象，与<xref:System.Windows.Controls.Primitives.Popup>位于相对于屏幕。  
  
 下面的示例创建<xref:System.Windows.Controls.Primitives.Popup>的子级<xref:System.Windows.Controls.Canvas>。  该示例不会设置<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>属性<xref:System.Windows.Controls.Primitives.Popup>。 默认值为<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>，因此<xref:System.Windows.Controls.Primitives.Popup>如下所示<xref:System.Windows.Controls.Canvas>。  
  
 [!code-xaml[PopupPositionSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 下图显示<xref:System.Windows.Controls.Primitives.Popup>位于相对于<xref:System.Windows.Controls.Canvas>。  
  
 ![没有 placementtarget 的 popup 控件](../../../../docs/framework/wpf/controls/media/popupplacementnoplacementtarget.PNG "PopupPlacementNoPlacementTarget")  
没有 PlacementTarget 的 Popup  
  
 下面的示例创建<xref:System.Windows.Controls.Primitives.Popup>的子级<xref:System.Windows.Controls.Canvas>，但这次<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>设置为`ellipse1`，因此弹出窗口出现下面<xref:System.Windows.Shapes.Ellipse>。  
  
 [!code-xaml[PopupPositionSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 下图显示<xref:System.Windows.Controls.Primitives.Popup>位于相对于<xref:System.Windows.Shapes.Ellipse>。  
  
 ![相对于椭圆定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementwithplacementtarget.PNG "PopupPlacementWithPlacementTarget")  
具有 PlacementTarget 的 Popup  
  
> [!NOTE]
>  有关<xref:System.Windows.Controls.ToolTip>，默认值的<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>。  有关<xref:System.Windows.Controls.ContextMenu>，默认值的<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>。 这些值将在后面的“属性如何协同工作”部分中进行说明。  
  
### <a name="target-area"></a>目标区域  
 *目标区域*是在屏幕上的区域，<xref:System.Windows.Controls.Primitives.Popup>是相对于。 在前面的示例中，<xref:System.Windows.Controls.Primitives.Popup>对齐边界的目标对象，但在某些情况下，<xref:System.Windows.Controls.Primitives.Popup>对齐到其他边界，即使<xref:System.Windows.Controls.Primitives.Popup>具有的目标对象。  如果<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>属性设置，则目标区域是不同于目标对象的边界。  
  
 下面的示例创建两个<xref:System.Windows.Controls.Canvas>对象，包含每个<xref:System.Windows.Shapes.Rectangle>和<xref:System.Windows.Controls.Primitives.Popup>。  在这两种情况下，目标对象<xref:System.Windows.Controls.Primitives.Popup>是<xref:System.Windows.Controls.Canvas>。 <xref:System.Windows.Controls.Primitives.Popup>中第一个<xref:System.Windows.Controls.Canvas>具有<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>设置，使用其<xref:System.Windows.Rect.X%2A>， <xref:System.Windows.Rect.Y%2A>， <xref:System.Windows.Rect.Width%2A>，和<xref:System.Windows.Rect.Height%2A>属性分别设置为 50，50、 50、 和 100。 <xref:System.Windows.Controls.Primitives.Popup>在第二个<xref:System.Windows.Controls.Canvas>没有<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>设置。  因此，第一个<xref:System.Windows.Controls.Primitives.Popup>下面定位<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>和第二个<xref:System.Windows.Controls.Primitives.Popup>下面定位<xref:System.Windows.Controls.Canvas>。 每个<xref:System.Windows.Controls.Canvas>还包含<xref:System.Windows.Shapes.Rectangle>具有相同的边界<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>的第一个<xref:System.Windows.Controls.Primitives.Popup>。  请注意，<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>不会在该应用程序; 创建可见的元素的示例创建<xref:System.Windows.Shapes.Rectangle>来表示<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>。  
  
 [!code-xaml[PopupPositionSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 下图显示前面示例的结果。  
  
 ![弹出窗口具有和没有 PlacementRectangle](../../../../docs/framework/wpf/controls/media/popupplacementplacementrectangle.PNG "PopupPlacementPlacementRectangle")  
具有和没有 PlacementRectangle 的 Popup  
  
### <a name="target-origin-and-popup-alignment-point"></a>目标原点和目标对齐点  
 *目标原点*和 *Popup 对齐点*分别是目标区域和 Popup 上用于定位定位的参照点。 你可以使用<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性以偏移量从目标区域弹出窗口。  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>是相对于目标原点和 popup 对齐点。 值<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性确定目标原点和弹出项对齐点所在的位置。  
  
 下面的示例创建<xref:System.Windows.Controls.Primitives.Popup>和设置<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>属性设置为 20。  <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>（默认值），因此目标原点是目标区域左下角，而 popup 对齐点的左上角<xref:System.Windows.Controls.Primitives.Popup>。  
  
 [!code-xaml[PopupPositionSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 下图显示前面示例的结果。  
  
 ![与目标原点为对齐点的 popup 定位](../../../../docs/framework/wpf/controls/media/popupplacementtargetoriginalignmentpoint.PNG "PopupPlacementTargetOriginAlignmentPoint")  
具有 HorizontalOffset 和 VerticalOffset 的 Popup  
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>属性如何协同工作  
 值<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>， <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>，和<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>需要综合考虑以了解正确的目标区域、 目标原点和 popup 对齐点。  例如，如果值<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>，没有目标对象，<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>将被忽略，和目标区域是鼠标指针的边界。 另一方面，如果<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>、<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>或父确定目标对象和<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>确定目标区域。  
  
 下表描述目标对象、 目标区域、 目标原点和 popup 对齐点，并指示是否<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>和<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>用于每种<xref:System.Windows.Controls.Primitives.PlacementMode>枚举值。  
  
|PlacementMode|目标对象|目标区域|目标原点|Popup 对齐点|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|不适用。 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 将被忽略。|屏幕上，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于屏幕。|目标区域的左上角。|左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|不适用。 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 将被忽略。|屏幕上，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于屏幕。|目标区域的左上角。|左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 或父对象。|目标对象，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象。|目标区域的左下角。|左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 或父对象。|目标对象，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象。|目标区域的中心。|中心<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 或父对象。|目标对象，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象。|通过定义<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>。|通过定义<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 或父对象。|目标对象，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象。|目标区域的左上角。|右上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|不适用。 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 将被忽略。|鼠标指针的边界。 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 将被忽略。|目标区域的左下角。|左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|不适用。 <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 将被忽略。|鼠标指针的边界。 <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> 将被忽略。|目标区域的左上角。|左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 或父对象。|目标对象，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象。|目标区域的左上角。|左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 或父对象。|目标对象，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象。|目标区域的左上角。|左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 或父对象。|目标对象，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象。|目标区域的右上角。|左上角<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> 或父对象。|目标对象，或<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>如果将其设置。  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>相对于目标对象。|目标区域的左上角。|左下角<xref:System.Windows.Controls.Primitives.Popup>。|  
  
 如下图所示<xref:System.Windows.Controls.Primitives.Popup>，每个点的目标区域、 目标原点和弹出项对齐<xref:System.Windows.Controls.Primitives.PlacementMode>值。 在每个图中，目标区域为黄色，和<xref:System.Windows.Controls.Primitives.Popup>为蓝色。  
  
 ![采用 Absolute 或 absolutepoint 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementabsolute.png "PopupPlacementAbsolute")  
Placement 为 Absolute 或 AbsolutePoint  
  
 ![采用 Bottom 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementbottom.png "PopupPlacementBottom")  
Placement 为 Bottom  
  
 ![采用 Center 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementcenter.png "PopupPlacementCenter")  
Placement 为 Center  
  
 ![采用 Left 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementleft.png "PopupPlacementLeft")  
Placement 为 Left  
  
 ![采用 Mouse 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementmouse.png "PopupPlacementMouse")  
Placement 为 Mouse  
  
 ![采用 mousepoint 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementmousepoint.png "PopupPlacementMousePoint")  
Placement 为 MousePoint  
  
 ![采用 Relative 或 relativepoint 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementrelative.png "PopupPlacementRelative")  
Placement 为 Relative 或 RelativePoint  
  
 ![采用 Right 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementright.png "PopupPlacementRight")  
Placement 为 Right  
  
 ![采用 Top 定位的 popup](../../../../docs/framework/wpf/controls/media/popupplacementtop.png "PopupPlacementTop")  
Placement 为 Top  
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>当 Popup 到达屏幕边缘时  
 出于安全原因，<xref:System.Windows.Controls.Primitives.Popup>无法由屏幕的边缘隐藏。 将发生以下三种情况之一时<xref:System.Windows.Controls.Primitives.Popup>遇到屏幕边缘：  
  
-   弹出窗口将沿将遮蔽的屏幕边缘沿<xref:System.Windows.Controls.Primitives.Popup>。  
  
-   Popup 使用其他 Popup 对齐点。  
  
-   Popup 使用其他目标原点和 Popup 对齐点。  
  
 将在本部分后面进一步介绍这些选项。  
  
 行为<xref:System.Windows.Controls.Primitives.Popup>时遇到屏幕边缘取决于值<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性和屏幕的边缘遇到弹出窗口。 下表汇总了的行为时<xref:System.Windows.Controls.Primitives.Popup>遇到每个屏幕边缘<xref:System.Windows.Controls.Primitives.PlacementMode>值。  
  
|PlacementMode|上边缘|下边缘|左边缘|右边缘|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|与上边缘对齐。|Popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|Popup 对齐点更改为右上角的<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|与上边缘对齐。|目标原点更改到目标区域的左上角，而 popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|与上边缘对齐。|与下边缘对齐。|目标原点更改到的目标区域右上角，而 popup 对齐点更改为的左上角<xref:System.Windows.Controls.Primitives.Popup>。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|与上边缘对齐。|目标原点更改到目标区域 （鼠标指针的边界） 的左上角，而 popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|与上边缘对齐。|Popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|Popup 对齐点更改为 Popup 的右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|与上边缘对齐。|Popup 对齐点更改为的左下角<xref:System.Windows.Controls.Primitives.Popup>。|与左边缘对齐。|Popup 对齐点更改为 Popup 的右上角。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|与上边缘对齐。|与下边缘对齐。|与左边缘对齐。|目标原点更改到目标区域的左上角，而 popup 对齐点更改为右上角的<xref:System.Windows.Controls.Primitives.Popup>。|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|目标原点更改到的目标区域左下角，而 popup 对齐点更改为的左上角<xref:System.Windows.Controls.Primitives.Popup>。 实际上，这是当相同<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>。|与下边缘对齐。|与左边缘对齐。|与右边缘对齐。|  
  
### <a name="aligning-to-the-screen-edge"></a>对屏幕边缘对齐  
 A<xref:System.Windows.Controls.Primitives.Popup>可以对齐到屏幕边缘通过因此重新定位自身整个<xref:System.Windows.Controls.Primitives.Popup>屏幕上是否可见。  值时出现这种情况，可能会与不同目标原点和弹出项对齐点之间的距离<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>。 当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>， <xref:System.Windows.Controls.Primitives.PlacementMode.Center>，或<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>、<xref:System.Windows.Controls.Primitives.Popup>与每个屏幕边缘对齐本身。  例如，假定<xref:System.Windows.Controls.Primitives.Popup>具有<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>设置为<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>和<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>设置为 100。  如果屏幕的底部边缘隐藏全部或部分<xref:System.Windows.Controls.Primitives.Popup>、<xref:System.Windows.Controls.Primitives.Popup>重新定位自身沿下边缘的屏幕和目标原点和弹出项之间的垂直距离对齐点将变为小于 100。 下图演示了此情况。  
  
 ![与屏幕边缘对齐的弹出窗口](../../../../docs/framework/wpf/controls/media/popupplacementrelativescreenedge.png "PopupPlacementRelativeScreenEdge")  
Popup 与屏幕边缘对齐  
  
### <a name="changing-the-popup-alignment-point"></a>更改 Popup 对齐点  
 如果<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>， <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>，或<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>，popup 对齐点更改当弹出窗口遇到底部或屏幕右边缘。  
  
 下图演示了当底部屏幕边缘隐藏全部或部分<xref:System.Windows.Controls.Primitives.Popup>，而 popup 对齐点是的左下角<xref:System.Windows.Controls.Primitives.Popup>。  
  
 ![由于底部屏幕边缘而产生的新对齐点](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointscreenedge.png "PopupPlacementRelativePointScreenEdge")  
Popup 到达屏幕下边缘，并更改 Popup 对齐点  
  
 下图演示当<xref:System.Windows.Controls.Primitives.Popup>隐藏屏幕右边缘，而 popup 对齐点是右上角的<xref:System.Windows.Controls.Primitives.Popup>。  
  
 ![由于屏幕边缘而产生的新 popup 对齐点](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointrightscreenedge.png "PopupPlacementRelativePointRightScreenEdge")  
Popup 到达屏幕右边缘，并更改 Popup 对齐点  
  
 如果<xref:System.Windows.Controls.Primitives.Popup>遇到的底部和右侧屏幕边缘而 popup 对齐点是右下角的<xref:System.Windows.Controls.Primitives.Popup>。  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>更改目标原点和 Popup 对齐点  
 当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>， <xref:System.Windows.Controls.Primitives.PlacementMode.Left>， <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>， <xref:System.Windows.Controls.Primitives.PlacementMode.Right>，或<xref:System.Windows.Controls.Primitives.PlacementMode.Top>，目标原点和弹出项对齐点更改，如果遇到某些屏幕边缘。  取决于要更改的位置将导致屏幕边缘<xref:System.Windows.Controls.Primitives.PlacementMode>值。  
  
 下图演示当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>和<xref:System.Windows.Controls.Primitives.Popup>遇到底部屏幕边缘，目标原点是目标区域的左上角，而 popup 对齐点的左下角<xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![由于底部屏幕边缘而产生的新对齐点](../../../../docs/framework/wpf/controls/media/popupplacementbottomscreenedge.png "PopupPlacementBottomScreenEdge")  
Placement 为 Bottom，并且 Popup 到达屏幕下边缘  
  
 下图演示当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Left>和<xref:System.Windows.Controls.Primitives.Popup>到达左侧的屏幕边缘时，目标原点是目标区的右上角，而 popup 对齐点是左上角<xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![由于左侧的屏幕边缘而产生的新对齐点](../../../../docs/framework/wpf/controls/media/popupplacementleftscreenedge.png "PopupPlacementLeftScreenEdge")  
Placement 为 Left，并且 Popup 到达屏幕左边缘  
  
 下图演示当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Right>和<xref:System.Windows.Controls.Primitives.Popup>遇到屏幕右边缘，目标原点是目标区域的左上角，而 popup 对齐点的右上角<xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![由于右侧屏幕边缘而产生的新对齐点](../../../../docs/framework/wpf/controls/media/popupplacementrightscreenedge.png "PopupPlacementRightScreenEdge")  
Placement 为 Right，并且 Popup 到达屏幕右边缘  
  
 下图演示当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Top>和<xref:System.Windows.Controls.Primitives.Popup>到达顶部屏幕边缘时，目标原点是目标区域左下角，而 popup 对齐点的左上角<xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![由于顶部屏幕边缘而产生的新对齐点](../../../../docs/framework/wpf/controls/media/popupplacementtopscreenedge.png "PopupPlacementTopScreenEdge")  
Placement 为 Top，并且 Popup 到达屏幕上边缘  
  
 下图演示当<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>是<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>和<xref:System.Windows.Controls.Primitives.Popup>遇到底部屏幕边缘，目标原点将目标区域 （鼠标指针的边界） 和弹出项对齐的左上角点是左下角的<xref:System.Windows.Controls.Primitives.Popup>。  
  
 ![由于鼠标接近屏幕边缘而产生的新对齐点](../../../../docs/framework/wpf/controls/media/popupplacementmousescreenedge.png "PopupPlacementMouseScreenEdge")  
Placement 为 Mouse，并且 Popup 到达屏幕下边缘  
  
### <a name="customizing-popup-placement"></a>自定义 Popup 放置  
 可以通过设置自定义目标原点和弹出项对齐点<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>属性<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>。 然后定义<xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>返回一组的可能放置点和主轴 （按首选项的顺序） 的委托<xref:System.Windows.Controls.Primitives.Popup>。 显示的最大一部分的点<xref:System.Windows.Controls.Primitives.Popup>选择。  位置<xref:System.Windows.Controls.Primitives.Popup>如果自动调整<xref:System.Windows.Controls.Primitives.Popup>隐藏的屏幕边缘。 有关示例，请参阅[指定自定义 Popup 位置](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md)。  
  
## <a name="see-also"></a>请参阅  
 [Popup 放置示例](http://go.microsoft.com/fwlink/?LinkID=160032)
