---
title: 演示图板概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
ms.openlocfilehash: 36922dce795443a4c1136f6442eff1c297f3c641
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566894"
---
# <a name="storyboards-overview"></a>演示图板概述
本主题演示如何使用<xref:System.Windows.Media.Animation.Storyboard>对象来组织和应用动画。 它描述如何以交互方式操作<xref:System.Windows.Media.Animation.Storyboard>对象，并说明间接属性目标语法。  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 若要了解本主题，应熟悉不同的动画类型及其基本功能。 有关动画的简介，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。 还应了解如何使用附加属性。 有关附加属性的详细信息，请参阅[附加属性概述](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)。  
  
<a name="whatisatimeline"></a>   
## <a name="what-is-a-storyboard"></a>什么是情节提要？  
 动画并非唯一有用的时间线类型。 还提供了其他时间线类来帮助组织时间线集，并将时间线应用于属性。 容器时间线派生自<xref:System.Windows.Media.Animation.TimelineGroup>类，并包含<xref:System.Windows.Media.Animation.ParallelTimeline>和<xref:System.Windows.Media.Animation.Storyboard>。  
  
 A<xref:System.Windows.Media.Animation.Storyboard>是一种为它包含的时间线提供目标信息的容器时间线。 情节提要可以包含任何类型的<xref:System.Windows.Media.Animation.Timeline>，包括其他容器时间线和动画。 <xref:System.Windows.Media.Animation.Storyboard> 对象使您能够合并影响各种对象和属性条时间线树，就可以更轻松来组织和控制复杂计时行为的时间线。 例如，假设需要一个执行以下三个操作的按钮。  
  
-   当用户选择该按钮时，按钮增大并更改颜色。  
  
-   当用户单击该按钮时，按钮缩小并恢复其原始大小。  
  
-   当该按钮变为禁用状态时，按钮缩小且不透明度缩减到 50%。  
  
 在此情况下，有多组动画适用于同一对象，并且需要根据按钮的状态在不同的时间播放它们。 <xref:System.Windows.Media.Animation.Storyboard> 对象可用于组织动画和组中将其应用到一个或多个对象。  
  
<a name="wherecanyouuseastoryboard"></a>   
## <a name="where-can-you-use-a-storyboard"></a>何处可以使用情节提要？  
 A<xref:System.Windows.Media.Animation.Storyboard>可用来进行动画处理的可进行动画处理的类的依赖项属性 (有关如何使类可进行动画处理的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md))。 但是，由于情节提要是框架级功能，该对象必须属于<xref:System.Windows.NameScope>的<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。  
  
 例如，可以使用<xref:System.Windows.Media.Animation.Storyboard>以执行以下操作：  
  
-   进行动画处理<xref:System.Windows.Media.SolidColorBrush>（非 framework 元素） 绘制背景的按钮 (一种<xref:System.Windows.FrameworkElement>)，  
  
-   进行动画处理<xref:System.Windows.Media.SolidColorBrush>（非 framework 元素） 绘制的填充<xref:System.Windows.Media.GeometryDrawing>（非 framework 元素） 显示使用<xref:System.Windows.Controls.Image>(<xref:System.Windows.FrameworkElement>)。  
  
-   在代码中，进行动画处理<xref:System.Windows.Media.SolidColorBrush>声明由类还包含<xref:System.Windows.FrameworkElement>，如果<xref:System.Windows.Media.SolidColorBrush>注册其名称与该<xref:System.Windows.FrameworkElement>。  
  
 但是，你无法使用<xref:System.Windows.Media.Animation.Storyboard>要进行动画处理<xref:System.Windows.Media.SolidColorBrush>，没有注册其名称前的使用<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>，或未使用设置的属性<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>。  
  
<a name="applyanimationswithastoryboard"></a>   
## <a name="how-to-apply-animations-with-a-storyboard"></a>如何使用情节提要应用动画  
 若要使用<xref:System.Windows.Media.Animation.Storyboard>来组织和应用动画，您将动画添加为子时间线的<xref:System.Windows.Media.Animation.Storyboard>。 <xref:System.Windows.Media.Animation.Storyboard>类提供<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType>和<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType>附加属性。 可以在动画上设置这些属性以指定其目标对象和属性。  
  
 若要将动画应用于它们的目标，应先<xref:System.Windows.Media.Animation.Storyboard>使用的触发器操作或方法。 在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你使用<xref:System.Windows.Media.Animation.BeginStoryboard>对象<xref:System.Windows.EventTrigger>， <xref:System.Windows.Trigger>，或<xref:System.Windows.DataTrigger>。 在代码中，你可以使用<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法。  
  
 下表显示不同的位置其中每个<xref:System.Windows.Media.Animation.Storyboard>开始支持技术： 每个实例、 样式、 控件模板和数据模板。 “基于实例”是指直接将动画或情节提要应用于对象实例（而不是在样式、控件模板或数据模板中应用）的技术。  
  
|情节提要开始时使用…|基于实例|样式|控件模板|数据模板|示例|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和 <xref:System.Windows.EventTrigger>|是|是|是|是|[使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和属性 <xref:System.Windows.Trigger>|否|是|是|是|[在属性值更改时触发动画](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和 <xref:System.Windows.DataTrigger>|否|是|是|是|[如何：在数据更改时触发动画](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法|是|No|否|否|[使用情节提要对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 下面的示例使用<xref:System.Windows.Media.Animation.Storyboard>要进行动画处理<xref:System.Windows.FrameworkElement.Width%2A>的<xref:System.Windows.Shapes.Rectangle>元素和<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>用于进行绘制， <xref:System.Windows.Shapes.Rectangle>。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 以下各节描述了<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>和<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>附加更多详细信息中的属性。  
  
<a name="targetingelementsandfreezables"></a>   
## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>以框架元素、框架内容元素和 Freezable 元素为目标  
 上一节提到过，对于要查找其目标的动画，必须知道目标的名称和要进行动画处理的属性。 指定要进行动画处理的属性也是非常简单： 只需设置<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType>替换为要进行动画处理的属性的名称。  指定对象要进行动画处理通过设置其属性的名称<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType>上动画的属性。  
  
 有关<xref:System.Windows.Setter.TargetName%2A>属性起作用，目标的对象必须具有名称。 分配到名称<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]不同于分配到名称<xref:System.Windows.Freezable>对象。  
  
 框架元素是继承自这些类<xref:System.Windows.FrameworkElement>类。 框架元素的示例包括<xref:System.Windows.Window>， <xref:System.Windows.Controls.DockPanel>， <xref:System.Windows.Controls.Button>，和<xref:System.Windows.Shapes.Rectangle>。 实质上，所有窗口、面板和控件都是元素。 Framework 内容元素都是继承自这些类<xref:System.Windows.FrameworkContentElement>类。 Framework 内容元素的示例包括<xref:System.Windows.Documents.FlowDocument>和<xref:System.Windows.Documents.Paragraph>。 如果不确定某个类型是框架元素还是框架内容元素，请查看它是否具有 Name 属性。 如果具有 Name 属性，则可能是框架元素或框架内容元素。 若要进一步确定，请检查其类型页面的“继承性分层”部分。  
  
 若要启用的框架元素或框架中的内容元素的目标[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你将设置其<xref:System.Windows.FrameworkElement.Name%2A>属性。 在代码中，你还需要使用<xref:System.Windows.NameScope.RegisterName%2A>方法以将元素的名称注册为其已创建的元素<xref:System.Windows.NameScope>。  
  
 以下示例中，来自前面的示例中，将名称分配`MyRectangle` <xref:System.Windows.Shapes.Rectangle>，一种<xref:System.Windows.FrameworkElement>。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 在该元素具有名称后，可以对其属性进行动画处理。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable> 类型是继承自这些类<xref:System.Windows.Freezable>类。 示例<xref:System.Windows.Freezable>包括<xref:System.Windows.Media.SolidColorBrush>， <xref:System.Windows.Media.RotateTransform>，和<xref:System.Windows.Media.GradientStop>。  
  
 若要启用的目标<xref:System.Windows.Freezable>通过在动画[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你使用[X:name 指令](../../../../docs/framework/xaml-services/x-name-directive.md)以将其分配一个名称。 在代码中，你使用<xref:System.Windows.NameScope.RegisterName%2A>方法以将其名称注册为其已创建的元素<xref:System.Windows.NameScope>。  
  
 以下示例将分配一个名称与<xref:System.Windows.Freezable>对象。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 然后动画便可以该对象为目标。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard> 对象使用名称作用域来解决<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>属性。 有关 WPF 名称范围的详细信息，请参阅 [WPF XAML 名称范围](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)。 如果<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>省略属性、 动画目标元素上定义的或者，对于样式的样式元素。  
  
 有时，名称不能分配给<xref:System.Windows.Freezable>对象。 例如，如果<xref:System.Windows.Freezable>声明作为资源或用于设置属性值中一种样式，它不能为指定的名称。 由于该对象没有名称，因此不能直接以它为目标，但可以间接以它为目标。 下面几节描述如何使用间接目标。  
  
<a name="pathsyntaxforchangeable"></a>   
## <a name="indirect-targeting"></a>间接目标  
 有时<xref:System.Windows.Freezable>动画，例如，当不能直接针对<xref:System.Windows.Freezable>声明作为资源或用于在样式中设置属性值。 在这些情况下，即使你不能将其作为目标直接，也可以仍具有动画效果<xref:System.Windows.Freezable>对象。 而不是设置<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>属性的同名<xref:System.Windows.Freezable>，你赋予它的元素的名称与其<xref:System.Windows.Freezable>"所属。" 例如，<xref:System.Windows.Media.SolidColorBrush>用于设置<xref:System.Windows.Shapes.Shape.Fill%2A>元素属于该矩形的矩形。 若要进行动画处理画笔，将设置动画的<xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>与开始框架元素或 framework 内容元素的属性的属性的链<xref:System.Windows.Freezable>用于设置和结束的<xref:System.Windows.Freezable>属性进行动画处理。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 请注意，如果<xref:System.Windows.Freezable>是冻结，则将进行克隆，并且该克隆将进行动画处理。 当发生这种情况，原始对象的<xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A>属性会继续返回`false`，因为不实际动画处理的原始对象。 有关克隆的详细信息，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
 另请注意，当使用间接属性目标时，可能会以不存在的对象为目标。 例如，您可能会假定<xref:System.Windows.Controls.Control.Background%2A>特定按钮的设置与<xref:System.Windows.Media.SolidColorBrush>并尝试进行动画处理的颜色时实际上<xref:System.Windows.Media.LinearGradientBrush>用于设置按钮的背景。 在这些情况下，不会引发异常;动画无法具有明显的效果，因为<xref:System.Windows.Media.LinearGradientBrush>没有反应以便将更改到<xref:System.Windows.Media.SolidColorBrush.Color%2A>属性。  
  
 下面几节详细介绍间接属性目标语法。  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>在 XAML 中间接以 Freezable 的属性为目标  
 目标属性中的可冻结[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，使用以下语法。  
  
||  
|-|  
|*ElementPropertyName* `.` *FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName*是的属性<xref:System.Windows.FrameworkElement>其中<xref:System.Windows.Freezable>用于设置，并  
  
-   *FreezablePropertyName*是的属性<xref:System.Windows.Freezable>要进行动画处理。  
  
 下面的代码演示如何进行动画处理<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>用于设置  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> 一个矩形元素。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]  
  
 有时，需要以集合或数组中包含的 Freezable 为目标。  
  
 若要以集合中包含的 Freezable 为目标，可以使用以下路径语法。  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 其中*CollectionIndex*是其数组或集合中对象的索引。  
  
 例如，假设矩形具有<xref:System.Windows.Media.TransformGroup>资源应用于其<xref:System.Windows.UIElement.RenderTransform%2A>属性，并且想要进行动画处理它包含转换之一。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]  
  
 下面的代码演示如何进行动画处理<xref:System.Windows.Media.RotateTransform.Angle%2A>属性<xref:System.Windows.Media.RotateTransform>中前面的示例所示。  
  
 [!code-xaml[storyboards_ovw_snip_XAML#35](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]  
  
<a name="targetingpropertyofchangeableincode"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>在代码中间接以 Freezable 的属性为目标  
 在代码中，你创建<xref:System.Windows.PropertyPath>对象。 当你创建<xref:System.Windows.PropertyPath>，你指定<xref:System.Windows.PropertyPath.Path%2A>和<xref:System.Windows.PropertyPath.PathParameters%2A>。  
  
 若要创建<xref:System.Windows.PropertyPath.PathParameters%2A>，创建类型的数组<xref:System.Windows.DependencyProperty>包含依赖项属性标识符字段的列表。 第一个标识符字段的属性是<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>，<xref:System.Windows.Freezable>用于设置。 下一步的标识符字段所代表的属性<xref:System.Windows.Freezable>到目标。 它看作连接的属性的链<xref:System.Windows.Freezable>到<xref:System.Windows.FrameworkElement>对象。  
  
 以下是一种面向的依赖项属性链<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>用于设置<xref:System.Windows.Shapes.Shape.Fill%2A>的矩形元素。  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 你还需要指定<xref:System.Windows.PropertyPath.Path%2A>。 A<xref:System.Windows.PropertyPath.Path%2A>是<xref:System.String>，告知<xref:System.Windows.PropertyPath.Path%2A>如何解释其<xref:System.Windows.PropertyPath.PathParameters%2A>。 它使用以下语法。  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex*是索引<xref:System.Windows.DependencyProperty>数组，其中包含的标识符<xref:System.Windows.FrameworkElement>对象的属性，<xref:System.Windows.Freezable>用于设置，并  
  
-   *FreezablePropertyArrayIndex*是索引<xref:System.Windows.DependencyProperty>数组，其中包含到目标属性的标识符。  
  
 下面的示例演示<xref:System.Windows.PropertyPath.Path%2A>所附带<xref:System.Windows.PropertyPath.PathParameters%2A>在前面的示例中定义。
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 下面的示例结合要进行动画处理的前一示例中的代码<xref:System.Windows.Media.SolidColorBrush.Color%2A>的<xref:System.Windows.Media.SolidColorBrush>用于设置<xref:System.Windows.Shapes.Shape.Fill%2A>的矩形元素。  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 有时，需要以集合或数组中包含的 Freezable 为目标。 例如，假设矩形具有<xref:System.Windows.Media.TransformGroup>资源应用于其<xref:System.Windows.UIElement.RenderTransform%2A>属性，并且想要进行动画处理它包含转换之一。  
  
 [!code-xaml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 到目标<xref:System.Windows.Freezable>包含在集合中，你使用以下路径语法。  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|  
  
 其中*CollectionIndex*是其数组或集合中对象的索引。  
  
 到目标<xref:System.Windows.Media.RotateTransform.Angle%2A>属性<xref:System.Windows.Media.RotateTransform>中的第二个转换<xref:System.Windows.Media.TransformGroup>，会使用以下<xref:System.Windows.PropertyPath.Path%2A>和<xref:System.Windows.PropertyPath.PathParameters%2A>。  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 下面的示例演示对进行动画处理的完整代码<xref:System.Windows.Media.RotateTransform.Angle%2A>的<xref:System.Windows.Media.RotateTransform>中包含<xref:System.Windows.Media.TransformGroup>。  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>间接以 Freezable 为目标并将其作为起点  
 前面几节描述了如何间接面向<xref:System.Windows.Freezable>利用<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>和创建到的属性链<xref:System.Windows.Freezable>子属性。 你还可以使用<xref:System.Windows.Freezable>作为起始点和间接目标之一其<xref:System.Windows.Freezable>子属性。 一条附加限制适用时使用<xref:System.Windows.Freezable>作为起点间接目标： 起始<xref:System.Windows.Freezable>和每个<xref:System.Windows.Freezable>它和间接目标的子属性之间必须未被冻结。  
  
<a name="controllable_storyboards"></a>   
## <a name="interactively-controlling-a-storyboard-in-xaml"></a>在 XAML 中以交互方式控制情节提要  
 若要在中启动情节提要[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，你使用<xref:System.Windows.Media.Animation.BeginStoryboard>触发操作。 <xref:System.Windows.Media.Animation.BeginStoryboard> 将分发到的对象和属性，它们进行动画处理，并启动情节提要的动画。 (有关此过程的详细信息，请参阅[动画和计时系统概述](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)。)如果你向提供<xref:System.Windows.Media.Animation.BeginStoryboard>通过指定的名称及其<xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>属性，你可以让它从此情节提要。 然后，可以在情节提要启动后以交互方式对它进行控制。 下面列出了可与事件触发器一起使用来控制情节提要的可控制情节提要操作。  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>： 暂停情节提要。  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>： 将恢复暂停的情节提要。  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>： 更改情节提要的速度。  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>： 如果有的话，请转到其填充期间，末尾情节提要。  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>： 停止情节提要。  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>： 移除情节提要。  
  
 在下面的示例中，使用可控制的情节提要操作来以交互方式控制情节提要。  
  
 [!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## <a name="interactively-controlling-a-storyboard-by-using-code"></a>使用代码以交互方式控制情节提要  
 前面的示例已演示了如何使用触发器操作进行动画处理。 在代码中，您也可以控制使用交互式方法的情节提要<xref:System.Windows.Media.Animation.Storyboard>类。 有关<xref:System.Windows.Media.Animation.Storyboard>进行交互式在代码中，你必须使用适当的重载的情节提要的<xref:System.Windows.Media.Animation.Storyboard.Begin%2A>方法并指定`true`使之可以控制。 请参阅<xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29>有关详细信息页。  
  
 以下列表显示可用于操作的方法<xref:System.Windows.Media.Animation.Storyboard>它启动后：  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 使用这些方法的优点是不需要创建<xref:System.Windows.Trigger>或<xref:System.Windows.TriggerAction>对象; 你只需对可控制的引用<xref:System.Windows.Media.Animation.Storyboard>你想要操作。  
  
 **注意：** 采取的所有交互操作<xref:System.Windows.Media.Animation.Clock>，因此同样，在<xref:System.Windows.Media.Animation.Storyboard>将发生的也会很快在下一步呈现之前的计时引擎的下一步刻度线上。 例如，如果你使用<xref:System.Windows.Media.Animation.Storyboard.Seek%2A>方法来跳转到在动画，属性值中的另一个点不会立即更改、 的值而不是，计时引擎的下一步刻度线上发生更改。  
  
 下面的示例演示如何应用和控制使用的交互式方法的动画<xref:System.Windows.Media.Animation.Storyboard>类。  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## <a name="animate-in-a-style"></a>在样式中进行动画处理  
 你可以使用<xref:System.Windows.Media.Animation.Storyboard>对象定义中的动画<xref:System.Windows.Style>。 动画处理与<xref:System.Windows.Media.Animation.Storyboard>中<xref:System.Windows.Style>类似于使用<xref:System.Windows.Media.Animation.Storyboard>在其他位置，有以下三个例外：  
  
-   未指定<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>;<xref:System.Windows.Media.Animation.Storyboard>始终以向其元素为目标<xref:System.Windows.Style>应用。 到目标<xref:System.Windows.Freezable>对象，你必须使用间接的目标。 有关间接目标的详细信息，请参阅[间接目标](#pathsyntaxforchangeable)部分。  
  
-   不能指定<xref:System.Windows.EventTrigger.SourceName%2A>为<xref:System.Windows.EventTrigger>或<xref:System.Windows.Trigger>。  
  
-   你无法使用动态资源引用或数据绑定表达式将设置<xref:System.Windows.Media.Animation.Storyboard>或动画属性值。 这是因为内的所有内容<xref:System.Windows.Style>必须是线程安全的并且计时系统必须<xref:System.Windows.Freezable.Freeze%2A><xref:System.Windows.Media.Animation.Storyboard>对象，以使其线程安全。 A<xref:System.Windows.Media.Animation.Storyboard>如果它或其子时间线包含动态资源引用或数据绑定表达式不能冻结。 有关冻结和其他详细信息<xref:System.Windows.Freezable>功能，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
-   在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，您無法宣告事件处理程序<xref:System.Windows.Media.Animation.Storyboard>或动画事件。  
  
 有关演示如何在样式中定义情节提要的示例，请参阅[动画样式](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md)示例。  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## <a name="animate-in-a-controltemplate"></a>在 ControlTemplate 中进行动画处理  
 你可以使用<xref:System.Windows.Media.Animation.Storyboard>对象定义中的动画<xref:System.Windows.Controls.ControlTemplate>。 动画处理与<xref:System.Windows.Media.Animation.Storyboard>中<xref:System.Windows.Controls.ControlTemplate>类似于使用<xref:System.Windows.Media.Animation.Storyboard>在其他位置，有以下两个例外：  
  
-   <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>只能引用与子对象的<xref:System.Windows.Controls.ControlTemplate>。 如果<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>未指定，则动画目标的元素<xref:System.Windows.Controls.ControlTemplate>应用。  
  
-   <xref:System.Windows.EventTrigger.SourceName%2A>为<xref:System.Windows.EventTrigger>或<xref:System.Windows.Trigger>只能引用与子对象的<xref:System.Windows.Controls.ControlTemplate>。  
  
-   你无法使用动态资源引用或数据绑定表达式将设置<xref:System.Windows.Media.Animation.Storyboard>或动画属性值。 这是因为内的所有内容<xref:System.Windows.Controls.ControlTemplate>必须是线程安全的并且计时系统必须<xref:System.Windows.Freezable.Freeze%2A><xref:System.Windows.Media.Animation.Storyboard>对象，以使其线程安全。 A<xref:System.Windows.Media.Animation.Storyboard>如果它或其子时间线包含动态资源引用或数据绑定表达式不能冻结。 有关冻结和其他详细信息<xref:System.Windows.Freezable>功能，请参阅[可冻结对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)。  
  
-   在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，您無法宣告事件处理程序<xref:System.Windows.Media.Animation.Storyboard>或动画事件。  
  
 有关演示如何定义中的将情节提要的示例<xref:System.Windows.Controls.ControlTemplate>，请参阅[动画中 ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md)示例。  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## <a name="animate-when-a-property-value-changes"></a>在属性值更改时进行动画处理  
 在样式和控件模板中，当属性更改时，可以使用 Trigger 对象来启动情节提要。 有关示例，请参阅[触发动画时属性值更改](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)和[动画中 ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md)。  
  
 属性应用动画<xref:System.Windows.Trigger>的对象行为比更复杂的方式<xref:System.Windows.EventTrigger>动画开始使用<xref:System.Windows.Media.Animation.Storyboard>方法。  它们"提交"时使用动画定义由其他<xref:System.Windows.Trigger>对象，但 compose 与<xref:System.Windows.EventTrigger>和方法，触发动画。  
  
## <a name="see-also"></a>请参阅  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Freezable 对象概述](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
