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
ms.openlocfilehash: 5c058dbaf2ae209a198a8299790d4002447ac443
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559685"
---
# <a name="storyboards-overview"></a>演示图板概述

本主题演示如何使用 <xref:System.Windows.Media.Animation.Storyboard> 对象来组织和应用动画。 它介绍了如何以交互方式操作 <xref:System.Windows.Media.Animation.Storyboard> 对象并描述间接属性目标语法。

## <a name="prerequisites"></a>先决条件

若要了解本主题，应熟悉不同的动画类型及其基本功能。 有关动画的简介，请参阅[动画概述](animation-overview.md)。 还应了解如何使用附加属性。 有关附加属性的详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。

<a name="whatisatimeline"></a>

## <a name="what-is-a-storyboard"></a>什么是情节提要？

动画并非唯一有用的时间线类型。 还提供了其他时间线类来帮助组织时间线集，并将时间线应用于属性。 容器时间线派生自 <xref:System.Windows.Media.Animation.TimelineGroup> 类，并包括 <xref:System.Windows.Media.Animation.ParallelTimeline> 和 <xref:System.Windows.Media.Animation.Storyboard>。

<xref:System.Windows.Media.Animation.Storyboard> 是一种为其所包含的时间线提供目标信息的容器时间线。 情节提要可以包含任何类型的 <xref:System.Windows.Media.Animation.Timeline>，包括其他容器时间线和动画。 使用 <xref:System.Windows.Media.Animation.Storyboard> 对象，您可以将影响各种对象和属性的时间线合并为单个时间线树，以便于组织和控制复杂的计时行为。 例如，假设需要一个执行以下三个操作的按钮。

- 当用户选择该按钮时，按钮增大并更改颜色。

- 当用户单击该按钮时，按钮缩小并恢复其原始大小。

- 当该按钮变为禁用状态时，按钮缩小且不透明度缩减到 50%。

在此情况下，有多组动画适用于同一对象，并且需要根据按钮的状态在不同的时间播放它们。 使用 <xref:System.Windows.Media.Animation.Storyboard> 对象可以组织动画并将其按组应用到一个或多个对象。

<a name="wherecanyouuseastoryboard"></a>

## <a name="where-can-you-use-a-storyboard"></a>何处可以使用情节提要？

<xref:System.Windows.Media.Animation.Storyboard> 可用于对动画处理类的依赖属性进行动画处理（有关如何动画处理类的详细信息，请参阅[动画概述](animation-overview.md)）。 但是，因为情节提要是一个框架级别功能，所以该对象必须属于 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement>的 <xref:System.Windows.NameScope>。

例如，可以使用 <xref:System.Windows.Media.Animation.Storyboard> 来执行以下操作：

- 对绘制按钮背景的 <xref:System.Windows.Media.SolidColorBrush> （非框架元素）进行动画处理（一种 <xref:System.Windows.FrameworkElement>类型），

- 对绘制使用 <xref:System.Windows.Controls.Image> （<xref:System.Windows.FrameworkElement>）显示的 <xref:System.Windows.Media.GeometryDrawing> （非框架元素）的填充的 <xref:System.Windows.Media.SolidColorBrush> （非框架元素）进行动画处理。

- 在代码中，如果 <xref:System.Windows.Media.SolidColorBrush> 将其名称注册到该 <xref:System.Windows.FrameworkElement>，则会对包含 <xref:System.Windows.FrameworkElement>的类声明的 <xref:System.Windows.Media.SolidColorBrush> 进行动画处理。

但是，您不能使用 <xref:System.Windows.Media.Animation.Storyboard> 对未使用 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement>注册其名称的 <xref:System.Windows.Media.SolidColorBrush> 进行动画处理，也不能使用来设置 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement>的属性。

<a name="applyanimationswithastoryboard"></a>

## <a name="how-to-apply-animations-with-a-storyboard"></a>如何使用情节提要应用动画

若要使用 <xref:System.Windows.Media.Animation.Storyboard> 来组织和应用动画，请将动画添加为 <xref:System.Windows.Media.Animation.Storyboard>的子时间线。 <xref:System.Windows.Media.Animation.Storyboard> 类提供 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> 附加属性。 可以在动画上设置这些属性以指定其目标对象和属性。

若要将动画应用于其目标，请使用触发器操作或方法开始 <xref:System.Windows.Media.Animation.Storyboard>。 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中，将使用具有 <xref:System.Windows.EventTrigger>、<xref:System.Windows.Trigger>或 <xref:System.Windows.DataTrigger>的 <xref:System.Windows.Media.Animation.BeginStoryboard> 对象。 在代码中，还可以使用 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法。

下表显示支持每个 <xref:System.Windows.Media.Animation.Storyboard> 开始技术的不同位置：每个实例、样式、控件模板和数据模板。 “基于实例”是指直接将动画或情节提要应用于对象实例（而不是在样式、控件模板或数据模板中应用）的技术。

|情节提要开始时使用…|基于实例|格式|控件模板|数据模板|示例|
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和 <xref:System.Windows.EventTrigger>|是|是|是|是|[使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和属性 <xref:System.Windows.Trigger>|否|是|是|是|[在属性值更改时触发动画](how-to-trigger-an-animation-when-a-property-value-changes.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard> 和 <xref:System.Windows.DataTrigger>|否|是|是|是|[如何：在数据更改时触发动画](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法|是|否|否|否|[使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)|

下面的示例使用 <xref:System.Windows.Media.Animation.Storyboard> 对 <xref:System.Windows.Shapes.Rectangle> 元素的 <xref:System.Windows.FrameworkElement.Width%2A> 进行动画处理，并使用 <xref:System.Windows.Media.SolidColorBrush> 绘制该 <xref:System.Windows.Shapes.Rectangle>的 <xref:System.Windows.Media.SolidColorBrush.Color%2A>。

[!code-xaml[storyboards_ovw_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]

[!code-csharp[storyboards_ovw_snip#100](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]

以下部分更详细地介绍了 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 和 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> 附加属性。

<a name="targetingelementsandfreezables"></a>

## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>以框架元素、框架内容元素和 Freezable 元素为目标

上一节提到过，对于要查找其目标的动画，必须知道目标的名称和要进行动画处理的属性。 指定要进行动画处理的属性是一种直接的方式：只需将 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> 设置为要进行动画处理的属性的名称。  通过设置动画的 "<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType>" 属性，可以指定要对其属性进行动画处理的对象的名称。

要使 <xref:System.Windows.Setter.TargetName%2A> 属性有效，目标对象必须具有名称。 将名称分配到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 不同于为 <xref:System.Windows.Freezable> 对象指定名称。

框架元素是从 <xref:System.Windows.FrameworkElement> 类继承的类。 框架元素的示例包括 <xref:System.Windows.Window>、<xref:System.Windows.Controls.DockPanel>、<xref:System.Windows.Controls.Button>和 <xref:System.Windows.Shapes.Rectangle>。 实质上，所有窗口、面板和控件都是元素。 框架内容元素是从 <xref:System.Windows.FrameworkContentElement> 类继承的类。 框架内容元素的示例包括 <xref:System.Windows.Documents.FlowDocument> 和 <xref:System.Windows.Documents.Paragraph>。 如果不确定某个类型是框架元素还是框架内容元素，请查看它是否具有 Name 属性。 如果具有 Name 属性，则可能是框架元素或框架内容元素。 若要进一步确定，请检查其类型页面的“继承性分层”部分。

若要在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中启用框架元素或框架内容元素的目标，请设置其 <xref:System.Windows.FrameworkElement.Name%2A> 属性。 在代码中，还需要使用 <xref:System.Windows.NameScope.RegisterName%2A> 方法来向已为其创建 <xref:System.Windows.NameScope>的元素注册元素的名称。

下面的示例从前面的示例中，将名称指定 `MyRectangle` <xref:System.Windows.Shapes.Rectangle>，<xref:System.Windows.FrameworkElement>类型。

[!code-xaml[storyboards_ovw_snip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]

[!code-csharp[storyboards_ovw_snip#102](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]

在该元素具有名称后，可以对其属性进行动画处理。

[!code-xaml[storyboards_ovw_snip_XAML#5](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]

[!code-csharp[storyboards_ovw_snip#105](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]

<xref:System.Windows.Freezable> 类型是继承自 <xref:System.Windows.Freezable> 类的类。 <xref:System.Windows.Freezable> 的示例包括 <xref:System.Windows.Media.SolidColorBrush>、<xref:System.Windows.Media.RotateTransform>和 <xref:System.Windows.Media.GradientStop>。

若要启用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中的动画的 <xref:System.Windows.Freezable> 目标，请使用[X：Name 指令](../../../desktop-wpf/xaml-services/xname-directive.md)为其分配名称。 在代码中，可以使用 <xref:System.Windows.NameScope.RegisterName%2A> 方法将其名称注册到已为其创建了 <xref:System.Windows.NameScope>的元素。

下面的示例为 <xref:System.Windows.Freezable> 对象分配一个名称。

[!code-xaml[storyboards_ovw_snip_XAML#3](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]

[!code-csharp[storyboards_ovw_snip#103](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]

然后动画便可以该对象为目标。

[!code-xaml[storyboards_ovw_snip_XAML#7](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]

[!code-csharp[storyboards_ovw_snip#107](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]

<xref:System.Windows.Media.Animation.Storyboard> 对象使用名称范围来解析 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 属性。 有关 WPF 名称范围的详细信息，请参阅 [WPF XAML 名称范围](../advanced/wpf-xaml-namescopes.md)。 如果省略 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 属性，动画将以定义它的元素为目标，或在样式的情况下为样式的元素。

有时，不能将名称分配给 <xref:System.Windows.Freezable> 的对象。 例如，如果将 <xref:System.Windows.Freezable> 声明为资源或用于设置样式中的属性值，则不能为其指定名称。 由于该对象没有名称，因此不能直接以它为目标，但可以间接以它为目标。 下面几节描述如何使用间接目标。

<a name="pathsyntaxforchangeable"></a>

## <a name="indirect-targeting"></a>间接目标

有时，动画不能直接作为 <xref:System.Windows.Freezable> 的目标，例如当 <xref:System.Windows.Freezable> 声明为资源或用于设置样式中的属性值时。 在这些情况下，即使您不能直接将其作为目标，您仍然可以对 <xref:System.Windows.Freezable> 对象进行动画处理。 不是用 <xref:System.Windows.Freezable>的名称设置 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 属性，而是向其提供 <xref:System.Windows.Freezable> "所属的元素的名称。" 例如，用于设置矩形元素的 <xref:System.Windows.Shapes.Shape.Fill%2A> 的 <xref:System.Windows.Media.SolidColorBrush> 属于该矩形。 若要对画笔进行动画处理，请使用从框架元素或框架内容元素的属性开始的一系列属性来设置动画的 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty>，并将 <xref:System.Windows.Freezable> 用于设置和结束要进行动画处理的 <xref:System.Windows.Freezable> 属性。

[!code-xaml[storyboards_ovw_snip_XAML#33](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]

[!code-csharp[storyboards_ovw_snip#134](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]

请注意，如果 <xref:System.Windows.Freezable> 已冻结，将进行克隆，并对该克隆进行动画处理。 发生这种情况时，原始对象的 <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> 属性将继续返回 `false`，因为原始对象实际上并未进行动画处理。 有关克隆的详细信息，请参阅 "[冻结对象概述](../advanced/freezable-objects-overview.md)"。

另请注意，当使用间接属性目标时，可能会以不存在的对象为目标。 例如，你可能会假设特定按钮的 <xref:System.Windows.Controls.Control.Background%2A> 是使用 <xref:System.Windows.Media.SolidColorBrush> 设置的，并尝试对其颜色进行动画处理（事实上，使用了 <xref:System.Windows.Media.LinearGradientBrush> 来设置按钮的背景）。 在这些情况下，不会引发异常;由于 <xref:System.Windows.Media.LinearGradientBrush> 不会对 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 属性所做的更改做出反应，动画无法获得明显的效果。

下面几节详细介绍间接属性目标语法。

<a name="xamlsyntaxchangeableproperty"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>在 XAML 中间接以 Freezable 的属性为目标

若要以 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中可冻结的属性为目标，请使用以下语法。

| |
|-|
|*ElementPropertyName* `.` *FreezablePropertyName*|

Where

- *ElementPropertyName*是用于设置 <xref:System.Windows.Freezable> 的 <xref:System.Windows.FrameworkElement> 的属性，以及

- *FreezablePropertyName*是要进行动画处理的 <xref:System.Windows.Freezable> 的属性。

下面的代码演示如何对用于设置矩形元素 <xref:System.Windows.Shapes.Shape.Fill%2A> 的 <xref:System.Windows.Media.SolidColorBrush> 的 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 进行动画处理。

[!code-xaml[storyboards_ovw_snip_XAML#32](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]

有时，需要以集合或数组中包含的 Freezable 为目标。

若要以集合中包含的 Freezable 为目标，可以使用以下路径语法。

| |
|-|
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|

其中， *CollectionIndex*是对象在其数组或集合中的索引。

例如，假设某个矩形有一个应用于其 <xref:System.Windows.UIElement.RenderTransform%2A> 属性的 <xref:System.Windows.Media.TransformGroup> 资源，并且想要对它包含的其中一个转换进行动画处理。

[!code-xaml[storyboards_ovw_snip_XAML#34](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]

下面的代码演示如何对上一个示例中所示 <xref:System.Windows.Media.RotateTransform> 的 <xref:System.Windows.Media.RotateTransform.Angle%2A> 属性进行动画处理。

[!code-xaml[storyboards_ovw_snip_XAML#35](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]

<a name="targetingpropertyofchangeableincode"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>在代码中间接以 Freezable 的属性为目标

在代码中，您将创建一个 <xref:System.Windows.PropertyPath> 对象。 创建 <xref:System.Windows.PropertyPath>时，指定 <xref:System.Windows.PropertyPath.Path%2A> 并 <xref:System.Windows.PropertyPath.PathParameters%2A>。

若要创建 <xref:System.Windows.PropertyPath.PathParameters%2A>，请创建包含依赖项属性标识符字段列表 <xref:System.Windows.DependencyProperty> 类型的数组。 第一个标识符字段用于 <xref:System.Windows.FrameworkElement> 的属性或 <xref:System.Windows.Freezable> 用于设置的 <xref:System.Windows.FrameworkContentElement>。 下一个标识符字段表示目标 <xref:System.Windows.Freezable> 的属性。 将该 <xref:System.Windows.Freezable> 视为一系列属性，这些属性将连接到 <xref:System.Windows.FrameworkElement> 对象。

下面是依赖属性链的一个示例，它以用于设置矩形元素 <xref:System.Windows.Shapes.Shape.Fill%2A> 的 <xref:System.Windows.Media.SolidColorBrush> 为 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 目标。

[!code-csharp[storyboards_ovw_snip#135](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]

还需要指定 <xref:System.Windows.PropertyPath.Path%2A>。 <xref:System.Windows.PropertyPath.Path%2A> 是告诉 <xref:System.Windows.PropertyPath.Path%2A> 如何解释其 <xref:System.Windows.PropertyPath.PathParameters%2A>的 <xref:System.String>。 它使用以下语法。

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|

Where

- *OwnerPropertyArrayIndex*是 <xref:System.Windows.DependencyProperty> 数组的索引，其中包含 <xref:System.Windows.Freezable> 用于设置的 <xref:System.Windows.FrameworkElement> 对象属性的标识符和

- *FreezablePropertyArrayIndex*是包含目标属性的标识符的 <xref:System.Windows.DependencyProperty> 数组的索引。

下面的示例演示了在前面的示例中定义的 <xref:System.Windows.PropertyPath.PathParameters%2A> 附带的 <xref:System.Windows.PropertyPath.Path%2A>。

[!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]

下面的示例合并了前面的示例中的代码，以对用于设置矩形元素 <xref:System.Windows.Shapes.Shape.Fill%2A> 的 <xref:System.Windows.Media.SolidColorBrush> 的 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 进行动画处理。

[!code-csharp[storyboards_ovw_snip#137](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]

有时，需要以集合或数组中包含的 Freezable 为目标。 例如，假设某个矩形有一个应用于其 <xref:System.Windows.UIElement.RenderTransform%2A> 属性的 <xref:System.Windows.Media.TransformGroup> 资源，并且想要对它包含的其中一个转换进行动画处理。

[!code-xaml[storyboards_ovw_snip#142](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]

若要以集合中包含的 <xref:System.Windows.Freezable> 为目标，请使用以下路径语法。

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|

其中， *CollectionIndex*是对象在其数组或集合中的索引。

若要以 <xref:System.Windows.Media.RotateTransform>的 <xref:System.Windows.Media.RotateTransform.Angle%2A> 属性为目标，<xref:System.Windows.Media.TransformGroup>中的第二个转换，请使用以下 <xref:System.Windows.PropertyPath.Path%2A> 和 <xref:System.Windows.PropertyPath.PathParameters%2A>。

[!code-csharp[storyboards_ovw_snip#139](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]

下面的示例演示了用于对包含在 <xref:System.Windows.Media.TransformGroup>内的 <xref:System.Windows.Media.RotateTransform> 的 <xref:System.Windows.Media.RotateTransform.Angle%2A> 进行动画处理的完整代码。

[!code-csharp[storyboards_ovw_snip#138](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]

### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>间接以 Freezable 为目标并将其作为起点

前面的部分介绍了如何通过 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 并创建指向 <xref:System.Windows.Freezable> 子属性的属性链来间接地定位 <xref:System.Windows.Freezable>。 你还可以使用 <xref:System.Windows.Freezable> 作为起点，并间接定位其 <xref:System.Windows.Freezable> 子属性之一。 当使用 <xref:System.Windows.Freezable> 作为间接目标的起点时，另一项限制是适用的：起始 <xref:System.Windows.Freezable> 以及它之间的每个 <xref:System.Windows.Freezable> 与间接目标的子属性之间不得冻结。

<a name="controllable_storyboards"></a>

## <a name="interactively-controlling-a-storyboard-in-xaml"></a>在 XAML 中以交互方式控制情节提要

若要在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中启动情节提要，请使用 <xref:System.Windows.Media.Animation.BeginStoryboard> 的触发器操作。 <xref:System.Windows.Media.Animation.BeginStoryboard> 将动画分散到它们动画处理的对象和属性，并启动情节提要。 （有关此过程的详细信息，请参阅[动画和计时系统概述](animation-and-timing-system-overview.md)。）如果通过指定 <xref:System.Windows.Media.Animation.BeginStoryboard> 的 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 属性为该名称提供名称，则会使其成为可控制的情节提要。 然后，可以在情节提要启动后以交互方式对它进行控制。 下面列出了可与事件触发器一起使用来控制情节提要的可控制情节提要操作。

- <xref:System.Windows.Media.Animation.PauseStoryboard>：暂停情节提要。

- <xref:System.Windows.Media.Animation.ResumeStoryboard>：恢复暂停的情节提要。

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>：更改情节提要的速度。

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>：使情节提要前进到其填充期的末尾（如果有一个）。

- <xref:System.Windows.Media.Animation.StopStoryboard>：停止情节提要。

- <xref:System.Windows.Media.Animation.RemoveStoryboard>：移除情节提要。

在下面的示例中，使用可控制的情节提要操作来以交互方式控制情节提要。

[!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]

<a name="controllable_storyboards_procedural"></a>

## <a name="interactively-controlling-a-storyboard-by-using-code"></a>使用代码以交互方式控制情节提要

前面的示例已演示了如何使用触发器操作进行动画处理。 在代码中，你还可以使用 <xref:System.Windows.Media.Animation.Storyboard> 类的交互式方法控制情节提要。 要使 <xref:System.Windows.Media.Animation.Storyboard> 在代码中成为交互式的，必须使用情节提要的 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 方法的适当重载，并指定 `true` 以使其可控制。 有关详细信息，请参阅<xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29>页。

以下列表显示了可用于在启动 <xref:System.Windows.Media.Animation.Storyboard> 后操作的方法：

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>

使用这些方法的优点是不需要创建 <xref:System.Windows.Trigger> 或 <xref:System.Windows.TriggerAction> 对象;只需引用要操作的可控 <xref:System.Windows.Media.Animation.Storyboard> 即可。

> [!NOTE]
> 在 <xref:System.Windows.Media.Animation.Clock>上执行的所有交互操作，因此也在 <xref:System.Windows.Media.Animation.Storyboard> 会在计时引擎的下一计时周期发生，这将在下一次呈现之前发生。 例如，如果使用 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 方法跳转到动画中的其他点，则属性值不会立即更改，而是在计时引擎的下一计时周期发生变化。

下面的示例演示如何使用 <xref:System.Windows.Media.Animation.Storyboard> 类的交互式方法来应用和控制动画。

[!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
[!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]

<a name="usingstoryboardsinstyles"></a>

## <a name="animate-in-a-style"></a>在样式中进行动画处理

您可以使用 <xref:System.Windows.Media.Animation.Storyboard> 对象来定义 <xref:System.Windows.Style>中的动画。 使用 <xref:System.Windows.Style> 中的 <xref:System.Windows.Media.Animation.Storyboard> 进行动画处理类似于在其他位置使用 <xref:System.Windows.Media.Animation.Storyboard>，但有以下三个例外：

- 不指定 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>;<xref:System.Windows.Media.Animation.Storyboard> 始终以 <xref:System.Windows.Style> 应用到的元素为目标。 若要以 <xref:System.Windows.Freezable> 对象为目标，必须使用间接目标。 有关间接目标的详细信息，请参阅[间接目标](#pathsyntaxforchangeable)部分。

- 不能为 <xref:System.Windows.EventTrigger> 或 <xref:System.Windows.Trigger>指定 <xref:System.Windows.EventTrigger.SourceName%2A>。

- 不能使用动态资源引用或数据绑定表达式来设置 <xref:System.Windows.Media.Animation.Storyboard> 或动画属性值。 这是因为 <xref:System.Windows.Style> 内的所有内容都必须是线程安全的，并且计时系统必须 <xref:System.Windows.Freezable.Freeze%2A><xref:System.Windows.Media.Animation.Storyboard> 对象，以使它们线程安全。 如果 <xref:System.Windows.Media.Animation.Storyboard> 无法冻结，则为; 否则为子时间线包含动态资源引用或数据绑定表达式。 有关冻结和其他 <xref:System.Windows.Freezable> 功能的详细信息，请参阅 "[冻结对象概述](../advanced/freezable-objects-overview.md)"。

- 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中，无法为 <xref:System.Windows.Media.Animation.Storyboard> 或动画事件声明事件处理程序。

有关演示如何在样式中定义情节提要的示例，请参阅在[样式示例中进行动画处理](how-to-animate-in-a-style.md)。

<a name="defineAStoryboardInAControlTemplateSection"></a>

## <a name="animate-in-a-controltemplate"></a>在 ControlTemplate 中进行动画处理

您可以使用 <xref:System.Windows.Media.Animation.Storyboard> 对象来定义 <xref:System.Windows.Controls.ControlTemplate>中的动画。 使用 <xref:System.Windows.Controls.ControlTemplate> 中的 <xref:System.Windows.Media.Animation.Storyboard> 进行动画处理类似于在其他位置使用 <xref:System.Windows.Media.Animation.Storyboard>，但有以下两个例外：

- <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 只能引用 <xref:System.Windows.Controls.ControlTemplate>的子对象。 如果未指定 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>，动画将以 <xref:System.Windows.Controls.ControlTemplate> 应用到的元素为目标。

- <xref:System.Windows.EventTrigger> 或 <xref:System.Windows.Trigger> 的 <xref:System.Windows.EventTrigger.SourceName%2A> 只能引用 <xref:System.Windows.Controls.ControlTemplate>的子对象。

- 不能使用动态资源引用或数据绑定表达式来设置 <xref:System.Windows.Media.Animation.Storyboard> 或动画属性值。 这是因为 <xref:System.Windows.Controls.ControlTemplate> 内的所有内容都必须是线程安全的，并且计时系统必须 <xref:System.Windows.Freezable.Freeze%2A><xref:System.Windows.Media.Animation.Storyboard> 对象，以使它们线程安全。 如果 <xref:System.Windows.Media.Animation.Storyboard> 无法冻结，则为; 否则为子时间线包含动态资源引用或数据绑定表达式。 有关冻结和其他 <xref:System.Windows.Freezable> 功能的详细信息，请参阅 "[冻结对象概述](../advanced/freezable-objects-overview.md)"。

- 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中，无法为 <xref:System.Windows.Media.Animation.Storyboard> 或动画事件声明事件处理程序。

有关演示如何在 <xref:System.Windows.Controls.ControlTemplate>中定义情节提要的示例，请参阅[system.windows.controls.controltemplate> 示例中的动画](how-to-animate-in-a-controltemplate.md)。

<a name="animateWhenAPropertyValueChanges"></a>

## <a name="animate-when-a-property-value-changes"></a>在属性值更改时进行动画处理

在样式和控件模板中，当属性更改时，可以使用 Trigger 对象来启动情节提要。 有关示例，请参阅在 System.windows.controls.controltemplate> 中[更改属性值并对](how-to-trigger-an-animation-when-a-property-value-changes.md)其[进行动画处理](how-to-animate-in-a-controltemplate.md)时触发动画。

<xref:System.Windows.Trigger> 对象应用的动画的行为方式比 <xref:System.Windows.EventTrigger> 动画或使用 <xref:System.Windows.Media.Animation.Storyboard> 方法开始的动画更复杂。  它们使用其他 <xref:System.Windows.Trigger> 对象定义的动画进行 "切换"，但使用 <xref:System.Windows.EventTrigger> 和方法触发动画进行撰写。

## <a name="see-also"></a>另请参阅

- [动画概述](animation-overview.md)
- [属性动画技术概述](property-animation-techniques-overview.md)
- [Freezable 对象概述](../advanced/freezable-objects-overview.md)
