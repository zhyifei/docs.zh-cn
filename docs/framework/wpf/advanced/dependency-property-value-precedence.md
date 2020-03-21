---
title: 依赖项属性值优先级
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], classes as owners
- dependency properties [WPF], metadata
- classes [WPF], owners of dependency properties
- metadata [WPF], dependency properties
ms.assetid: 1fbada8e-4867-4ed1-8d97-62c07dad7ebc
ms.openlocfilehash: 1d7c644c7f7581a96ffff1a0fe1fcf2adfe071e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186145"
---
# <a name="dependency-property-value-precedence"></a>依赖项属性值优先级
<a name="introduction"></a> 本主题说明 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 属性系统的工作机制如何影响依赖属性的值，并介绍应用于属性有效值的属性系统的各方面所依据的优先级。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>系统必备  
 本主题假定你从 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](dependency-properties-overview.md)。 若要采用本主题中的示例，还应当了解[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 并知道如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序。  
  
<a name="intro"></a>
## <a name="the-wpf-property-system"></a>WPF 属性系统  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 属性系统提供一种强大的方法，使得依赖属性的值由多种因素决定，从而实现诸如实时属性验证、后期绑定以及向相关属性发出有关其他属性值发生更改的通知等功能。 用来确定依赖属性值的确切顺序和逻辑相当复杂。 了解此顺序有助于避免不必要的属性设置，并且还有可能澄清混淆，使你正确了解为何某些影响或预测依赖属性值的尝试最终却没有得出所期望的值。  
  
<a name="multiple_sets"></a>
## <a name="dependency-properties-might-be-set-in-multiple-places"></a>依赖属性可以在多个位置“设置”  
 下面是同一属性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]（<xref:System.Windows.Controls.Control.Background%2A>） 具有可能影响该值的三个不同的"设置"操作的示例。  
  
 [!code-xaml[PropertiesOvwSupport#DPPrecedence](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#dpprecedence)]  
  
 这里，你希望应用什么颜色：红色、绿色还是蓝色？  
  
 本地属性集在设置时具有最高优先级，动画值和强制除外。 如果在本地设置某个值，你可以期待该值优先得到应用，甚至期待其优先级高于任何样式或控件模板。 在此示例中，<xref:System.Windows.Controls.Control.Background%2A>在本地设置为红色。 因此，在此作用域中定义的样式（即使它是隐式样式，否则将应用于该作用域中该类型的所有元素）不是给予<xref:System.Windows.Controls.Control.Background%2A>属性其值的最高优先级。  如果从该 Button 实例中删除本地值“Red”，样式将获得优先级，而按钮将从该样式中获得 Background 值。  在该样式中，触发器具有优先级，因此当鼠标位于按钮上时，按钮为蓝色，其他情况下则为绿色。  
  
<a name="listing"></a>
## <a name="dependency-property-setting-precedence-list"></a>依赖属性设置优先级列表  
 下面是属性系统在分配依赖属性的运行时值时所使用的最终顺序。 最高优先级最先列出。 此列表对[依赖属性概述](dependency-properties-overview.md)中的某些一般化内容进行了扩充。  
  
1. **属性系统强制。** 有关强制的详细信息，请参阅本主题后面的[强制、动画和基值](#animations)。  
  
2. **活动动画或具有 Hold 行为的动画。** 为了获得任何实用效果，属性的动画必须优先于基（未动画）值，即使该值是在本地设置的也是如此。 有关详细信息，请参阅本主题后面的[强制、动画和基值](#animations)。  
  
3. **本地值。** 本地值可以通过"wrapper"属性的便利性进行设置，该属性也等同于在 中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]设置为属性或属性元素，或者通过使用特定实例的属性调用<xref:System.Windows.DependencyObject.SetValue%2A>API。 如果使用绑定或资源来设置本地值，则每个值都按照直接设置值的优先级顺序来应用。  
  
4. **TemplatedParent 模板属性。** <xref:System.Windows.FrameworkElement.TemplatedParent%2A><xref:System.Windows.Controls.ControlTemplate>元素<xref:System.Windows.DataTemplate>具有 有关何时应用此原则的详细信息，请参阅本主题后面的 [TemplatedParent](#templatedparent)。 在模板中，按以下优先级顺序应用：  
  
    1. 来自模板的<xref:System.Windows.FrameworkElement.TemplatedParent%2A>触发器。  
  
    2. 模板中的属性集（[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]通常通过属性）。 <xref:System.Windows.FrameworkElement.TemplatedParent%2A>  
  
5. **隐式样式。** 仅应用于 `Style` 属性。 `Style` 属性是由任何样式资源通过与其类型匹配的键来填充的。 该样式资源必须存在于页面或应用程序中；查找隐式样式资源不会进入到主题中。  
  
6. **样式触发器。** 来自页面或应用程序的样式中的触发器（这些样式可以是显式或隐式样式，但不是来自优先级较低的默认样式）。  
  
7. **模板触发器。** 来自样式中的模板或者直接应用的模板的任何触发器。  
  
8. **样式资源库。** 来自页面或<xref:System.Windows.Setter>应用程序中的样式内的值。  
  
9. **默认（主题）样式。** 有关何时应用此样式以及主题样式如何与主题样式中的模板相关的详细信息，请参阅本主题后面的[默认（主题）样式](#themestyles)。 在默认样式中，按以下优先级顺序应用：  
  
    1. 主题样式中的活动触发器。  
  
    2. 主题样式中的资源库。  
  
10. **继承。** 有几个依赖属性从父元素向子元素继承值，因此不需要在应用程序中的每个元素上专门设置这些属性。 有关详细信息，请参阅[属性值继承](property-value-inheritance.md)。  
  
11. **来自依赖属性元数据的默认值。** 任何给定的依赖属性都可能有一个默认值，它由该特定属性的属性系统注册来确定。 而且，继承依赖属性的派生类可以选择按照类型重写该元数据（包括默认值）。 有关详细信息，请参阅[依赖属性元数据](dependency-property-metadata.md)。 因为继承是在默认值之前检查的，所以对于继承的属性，父元素的默认值优先于子元素。  因此，如果任何地方都没有设置可继承的属性，将使用在根元素或父元素中指定的默认值，而不是子元素的默认值。  
  
<a name="templatedparent"></a>
## <a name="templatedparent"></a>TemplatedParent  
 TemplatedParent 作为一个优先级项并不应用于在标准应用程序标记中直接声明的元素的任何属性。 只有对于通过应用模板而产生的可视化树中的子项而言，才存在 TemplatedParent 概念。 当属性系统搜索<xref:System.Windows.FrameworkElement.TemplatedParent%2A>模板查找值时，它将搜索创建该元素的模板。 模板中<xref:System.Windows.FrameworkElement.TemplatedParent%2A>的属性值通常充当子元素上的本地值，但相对于本地值存在此较小的优先级，因为模板可能共享。 有关详细信息，请参阅<xref:System.Windows.FrameworkElement.TemplatedParent%2A>。  
  
<a name="style_property"></a>
## <a name="the-style-property"></a>Style 属性  
 前面描述的查找顺序适用于所有可能的依赖项属性，但属性<xref:System.Windows.FrameworkElement.Style%2A>除外。 该<xref:System.Windows.FrameworkElement.Style%2A>属性是唯一的，因为它本身无法设置样式，因此优先级项 5 到 8 不适用。 此外，不建议进行动画或强制<xref:System.Windows.FrameworkElement.Style%2A>（动画<xref:System.Windows.FrameworkElement.Style%2A>需要自定义动画类）。 这留下了三种设置<xref:System.Windows.FrameworkElement.Style%2A>属性的方法：  
  
- **显式样式。** 属性<xref:System.Windows.FrameworkElement.Style%2A>是直接设置的。 在大多数情况下，样式不是内联定义的，而是作为资源由显式键进行引用的。 在这种情况下，Style 属性本身就像本地值（优先级项 3）一样来应用。  
  
- **隐式样式。** 属性<xref:System.Windows.FrameworkElement.Style%2A>不是直接设置的。 但是，资源<xref:System.Windows.FrameworkElement.Style%2A>查找序列（页面、应用程序）中的某个级别存在 ，并使用与要应用于样式的类型匹配的资源键进行键控。 在这种情况下，<xref:System.Windows.FrameworkElement.Style%2A>属性本身按序列中标识为项目 5 的优先级执行。 可以通过对<xref:System.Windows.DependencyPropertyHelper><xref:System.Windows.FrameworkElement.Style%2A>属性使用并在结果中查找<xref:System.Windows.BaseValueSource.ImplicitStyleReference>来检测此情况。  
  
- **默认样式**，也称为**主题样式。** 属性<xref:System.Windows.FrameworkElement.Style%2A>不是直接设置的，实际上将读取为`null`运行时。 在这种情况下，样式来自作为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 表示引擎一部分的运行时主题评估。  
  
 对于不在主题中的隐式样式，类型必须完全匹配 -`MyButton``Button`派生类不会隐式使用 样式`Button`。  
  
<a name="themestyles"></a>
## <a name="default-theme-styles"></a>默认（主题）样式  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 附带的每个控件都有一个默认样式。 默认样式可能因主题而异，这就是默认样式有时候称为主题样式的原因。  
  
 控件的默认样式中找到的最重要信息是控件模板，该模板作为其<xref:System.Windows.Controls.Control.Template%2A>属性的 setter 存在于主题样式中。 如果默认样式中没有模板，自定义样式中没有自定义模板的控件将根本没有可视化外观。 默认样式中的模板为每个控件的可视化外观提供一个基本结构，还定义在模板的可视化树中定义的属性与对应的控件类之间的联系。 每个控件都公开一组属性，这些属性可以影响控件的可视化外观，而无需完全替换模板。 例如，请考虑<xref:System.Windows.Controls.Primitives.Thumb>控件的默认可视外观，该外观是 的<xref:System.Windows.Controls.Primitives.ScrollBar>组件。  
  
 A<xref:System.Windows.Controls.Primitives.Thumb>具有某些可自定义的属性。 的默认模板<xref:System.Windows.Controls.Primitives.Thumb>创建一个基本结构/可视化树，其中有多个嵌套<xref:System.Windows.Controls.Border>组件，以创建斜面外观。 如果作为模板一部分的属性打算公开以供<xref:System.Windows.Controls.Primitives.Thumb>类自定义，则该属性必须由模板中的[模板绑定](templatebinding-markup-extension.md)公开。 在 中<xref:System.Windows.Controls.Primitives.Thumb>，这些边框的各种属性共享绑定到 属性（如 或<xref:System.Windows.Controls.Border.Background%2A><xref:System.Windows.Controls.Border.BorderThickness%2A>） 的模板。 但是其他某些属性或可视化排列被硬编码到控件模板中，或者绑定到直接来自主题的值，除了替换整个模板外，不能对其进行更改。 一般而言，如果属性来自模板化的父元素，并且不是通过模板绑定公开的，则不能通过样式进行调整，因为没有简单的方法可以将其设置为目标。 但是，该属性仍然可能受所应用的模板中的属性值继承的影响，或受默认值的影响。  
  
 主题样式将类型用作其定义中的键。 但是，当主题应用于给定元素实例时，通过检查控件上的属性<xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>来执行此类型的主题查找。 这与使用文本类型的隐式样式正好相反。 即使实现者<xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>未更改该属性，也会继承到派生类的值（更改属性的预定方式不是在属性级别重写该属性，而是更改属性元数据中的默认值）。 这种间接方式使基类可以为没有样式（或者该样式中没有模板，因此根本没有默认的可视化外观，这一点更为重要）的派生元素定义主题样式。 因此，您可以派生`MyButton`，<xref:System.Windows.Controls.Button>并且仍将获取<xref:System.Windows.Controls.Button>默认模板。 如果您是 的`MyButton`控件作者，并且需要其他行为，则可以重写<xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>依赖`MyButton`项属性元数据以返回其他键，然后定义相关主题样式，包括必须随`MyButton``MyButton`控件打包的模板。 有关主题、样式和控件创作的更多详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。  
  
<a name="resources"></a>
## <a name="dynamic-resource-references-and-binding"></a>动态资源引用和绑定  
 动态资源引用和绑定操作遵守其设置位置的优先级。 例如，应用于本地值的动态资源作为优先级项 3 进行应用，主题样式中的属性资源库的绑定作为优先级项 9 进行应用，依此类推。 由于动态资源引用和绑定必须都能够从应用程序的运行时状态中获得值，这使确定任何给定属性的属性值优先级的实际处理也将扩展到运行时。  
  
 严格来讲，动态资源引用并不是属性系统的一部分，但它们的确具有自己的查找顺序，该顺序与上面列出的序列交互。 [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)中对该优先级进行了更全面的介绍。 该优先级的基本概括是：元素到页面根元素、应用程序、主题、系统。  
  
 动态资源和绑定具有其设置位置的优先级，但是值会延迟。 这样的一个后果是，如果将动态资源或绑定设置为某个本地值，则对该本地值的任何更改都会完全替换该动态资源或绑定。 即使您调用<xref:System.Windows.DependencyObject.ClearValue%2A>方法以清除本地设置的值，也不会还原动态资源或绑定。 实际上，如果调用<xref:System.Windows.DependencyObject.ClearValue%2A>具有动态资源或绑定的属性（没有文本本地值），则<xref:System.Windows.DependencyObject.ClearValue%2A>调用也会清除它们。  
  
<a name="setcurrentvalue"></a>
## <a name="setcurrentvalue"></a>SetCurrentValue  
 该方法<xref:System.Windows.DependencyObject.SetCurrentValue%2A>是设置属性的另一种方法，但它的优先级顺序不一。 相反，<xref:System.Windows.DependencyObject.SetCurrentValue%2A>使您能够更改属性的值，而无需覆盖前一个值的源。 您可以使用<xref:System.Windows.DependencyObject.SetCurrentValue%2A>任何时间设置值，而不给予该值本地值的优先级。 例如，如果属性由触发器设置，然后通过<xref:System.Windows.DependencyObject.SetCurrentValue%2A>分配另一个值，则属性系统仍尊重触发器，如果触发器的操作发生，该属性将更改。 <xref:System.Windows.DependencyObject.SetCurrentValue%2A>使您能够更改属性的值，而不为属性提供具有更高优先级的源。 同样，可以使用<xref:System.Windows.DependencyObject.SetCurrentValue%2A>更改属性的值而不覆盖绑定。  
  
<a name="animations"></a>
## <a name="coercion-animations-and-base-value"></a>强制、动画和基值  
 强制和动画都作用于此 SDK 中称为"基值"的值。 因此，基值是在各项中通过向上计算一直到第 2 项为止而确定的任何值。  
  
 对于动画，如果没有为某些行为指定“From”和“To”值，或者动画在完成时故意还原为基值，那么基值将影响动画值。 若要了解实际效果，请运行 [From, To, and By Animation Target Values Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)（From、To 和 By 动画目标值示例）。 尝试为示例中的矩形高度设置本地值，使初始本地值不同于动画中的任何“From”值。 你会注意到动画立即使用“From”值开始，并在开始后替换基值。 动画可能指定在动画完成后通过指定 Stop<xref:System.Windows.Media.Animation.FillBehavior>返回到动画之前找到的值。 然后，根据正常优先级来确定基值。  
  
 多个动画可能应用于一个属性，而每个动画可能是从值优先级中的不同点进行定义的。 但是，这些动画的值可能会组合起来，而不仅仅是从较高的优先级开始应用动画。 这完全取决于动画的定义方式以及进行动画处理的值类型。 有关对属性进行动画处理的详细信息，请参阅[动画概述](../graphics-multimedia/animation-overview.md)。  
  
 强制在最高级别应用。 即使正在运行的动画也会受到值强制的制约。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的某些现有的依赖属性具有内置的强制行为。 对于自定义依赖项属性，通过在创建属性时编写 和<xref:System.Windows.CoerceValueCallback>传递回调作为元数据的一部分来定义自定义依赖项属性的强制行为。 还可以通过在派生类中重写现有属性的元数据来重写其强制行为。 强制与基值的交互使强制约束就像当时存在这些约束一样进行应用，但基值仍将保留。 因此，如果强制约束后来被解除，强制将返回与基值最接近的值，并且一旦所有约束都解除，强制对属性的影响可能会立即停止。 有关强制行为的详细信息，请参阅[依赖属性回调和验证](dependency-property-callbacks-and-validation.md)。  
  
<a name="triggers"></a>
## <a name="trigger-behaviors"></a>触发器行为  
 控件常常在主题中将触发器行为定义为其默认样式的一部分。 为控件设置本地属性可能会阻止触发器从视觉或行为上响应用户驱动的事件。 属性触发器的最常见用途是控件或状态属性（如<xref:System.Windows.Controls.Primitives.Selector.IsSelected%2A>） 例如，默认情况下，当禁用<xref:System.Windows.Controls.Button>（为<xref:System.Windows.UIElement.IsEnabled%2A>is`false`的触发器）<xref:System.Windows.Controls.Control.Foreground%2A>时，主题样式中的值是导致控件显示为"灰显"的原因。 但是，如果您设置了本地<xref:System.Windows.Controls.Control.Foreground%2A>值，则即使在此属性触发的方案中，该正常的灰出颜色也会优先于本地属性集来否决。 为具有主题级触发器行为的属性设置值时要倍加小心，并确保不要过度妨碍该控件应有的用户体验。  
  
<a name="clearvalue"></a>
## <a name="clearvalue-and-value-precedence"></a>ClearValue 和值优先级  
 该方法<xref:System.Windows.DependencyObject.ClearValue%2A>提供了一个权宜之计，用于清除在元素上设置的依赖项属性中的任何本地应用值。 但是，调用<xref:System.Windows.DependencyObject.ClearValue%2A>并不保证在属性注册期间在元数据中建立的默认值是新的有效值。 值优先级中的所有其他参与者仍然有效。 只有在本地设置的值才会从优先级序列中删除。 例如，如果调用<xref:System.Windows.DependencyObject.ClearValue%2A>由主题样式设置该属性的属性，则主题值将应用为新值，而不是基于元数据的默认值。 如果要将所有属性值参与者从流程中拉出，并将该值设置为已注册的元数据默认值，则可以通过查询依赖项属性元数据最终获取该默认值，然后可以使用默认值在本地设置具有 调用 的属性<xref:System.Windows.DependencyObject.SetValue%2A>。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.DependencyObject>
- <xref:System.Windows.DependencyProperty>
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖属性](custom-dependency-properties.md)
- [依赖项属性回调和验证](dependency-property-callbacks-and-validation.md)
