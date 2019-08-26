---
title: 通过创建 ControlTemplate 自定义现有控件的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
ms.openlocfilehash: 63a0b724b71c4a4901c2dedcf502045a75ec405c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933720"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>通过创建 ControlTemplate 自定义现有控件的外观
<a name="introduction"></a><xref:System.Windows.Controls.ControlTemplate> 指定视觉结构和控件的视觉行为。 可以通过向控件提供一个新的<xref:System.Windows.Controls.ControlTemplate> 对控件外观进行自定义。 创建 <xref:System.Windows.Controls.ControlTemplate> 时，仅替换现有控件的外观，而不会更改其功能。 例如，可在应用程序中将按钮设置为圆形而不是默认的方形，但按钮仍将引发 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。  
  
 本主题介绍了<xref:System.Windows.Controls.ControlTemplate>的各个部分, 演示如何创建一个简单<xref:System.Windows.Controls.ControlTemplate>的<xref:System.Windows.Controls.Button>, 并说明如何理解控件的控制协定, 以便您可以自定义控件的外观。 由于你在中<xref:System.Windows.Controls.ControlTemplate>创建[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]了, 因此你可以在不编写任何代码的情况下更改控件的外观。 还可以使用设计器（如 Microsoft Expression Blend）创建自定义控件模板。 本主题演示了[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]自定义外观<xref:System.Windows.Controls.Button>的中的示例, 并列出了本主题末尾的完整示例。 有关使用 Expression Blend 的详细信息，请参阅[设置支持模板的控件的样式](https://go.microsoft.com/fwlink/?LinkId=161153)。  
  
 下图显示了一个<xref:System.Windows.Controls.Button> , 它<xref:System.Windows.Controls.ControlTemplate>使用在本主题中创建的。  
  
 ![带有自定义控件模板的按钮。](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
使用自定义控件模板的按钮  
  
 ![带有红色边框的按钮。](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
使用自定义控件模板并将鼠标指针悬停在上方的按钮  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 本主题假设用户了解如何创建和使用[控件](index.md)中讨论的控件和样式。 本主题中讨论的概念适用于从<xref:System.Windows.Controls.Control>类继承的元素, 但除外。 <xref:System.Windows.Controls.UserControl> 不能将应用<xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.UserControl>于。  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>何时应创建 ControlTemplate  
 控件具有许多属性 (例如<xref:System.Windows.Controls.Border.Background%2A>、 <xref:System.Windows.Controls.Control.Foreground%2A>和<xref:System.Windows.Controls.Control.FontFamily%2A>), 您可以将其设置为指定控件外观的不同方面, 但您可以通过设置这些属性进行的更改将受到限制。 例如, 可以将的<xref:System.Windows.Controls.Control.Foreground%2A>属性设置为蓝色, <xref:System.Windows.Controls.Control.FontStyle%2A>将设置为斜体<xref:System.Windows.Controls.CheckBox>。  
  
 如果没有为控件创建新<xref:System.Windows.Controls.ControlTemplate>的功能, 则基于每个[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序中的所有控件都将具有相同的常规外观, 这将限制创建具有自定义外观的应用程序的能力。 默认情况下, <xref:System.Windows.Controls.CheckBox>每个都具有类似的特征。 例如, 的<xref:System.Windows.Controls.CheckBox>内容始终位于选择指示器的右侧, 并且复选标记始终用于指示<xref:System.Windows.Controls.CheckBox>已选择。  
  
 <xref:System.Windows.Controls.ControlTemplate>如果要自定义控件的外观, 而不是控件上的其他属性将执行的操作, 请创建。 在的示例<xref:System.Windows.Controls.CheckBox>中, 假设您希望复选框的内容位于选择指示器之上, 并且您希望 X 指示<xref:System.Windows.Controls.CheckBox>选中了。 在的中<xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>指定这些更改。  
  
 下图显示了一个<xref:System.Windows.Controls.CheckBox>使用默认值<xref:System.Windows.Controls.ControlTemplate>的。  
  
 ![具有默认控件模板的复选框。](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
一个具有默认控件模板的复选框  
  
 下图显示了一个<xref:System.Windows.Controls.CheckBox> , 它使用自<xref:System.Windows.Controls.ControlTemplate>定义将<xref:System.Windows.Controls.CheckBox>上的内容置于<xref:System.Windows.Controls.CheckBox>选择指示器上方, 并在选择时显示 X。  
  
 ![带有自定义控件模板的复选框。](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
一个具有自定义控件模板的复选框  
  
 在此示例中, 的与相对较为复杂, 因此本主题使用<xref:System.Windows.Controls.Button>的是<xref:System.Windows.Controls.ControlTemplate>为创建的一个更简单的示例。 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>更改控件的可视结构  
 在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中, 控件通常是复合<xref:System.Windows.FrameworkElement>对象。 当你创建<xref:System.Windows.Controls.ControlTemplate>时, 将组合<xref:System.Windows.FrameworkElement>对象以生成单个控件。 只能有一个<xref:System.Windows.FrameworkElement>作为其根元素。 <xref:System.Windows.Controls.ControlTemplate> 根元素通常包含其他<xref:System.Windows.FrameworkElement>对象。 对象组合构成控件的可视结构。  
  
 下面的示例<xref:System.Windows.Controls.Button>为创建了<xref:System.Windows.Controls.ControlTemplate>一个自定义。 创建的可视结构<xref:System.Windows.Controls.Button>。 <xref:System.Windows.Controls.ControlTemplate> 在按钮上方移动鼠标指针或单击它时，此示例不会更改按钮的外观。 本主题后面部分将讨论当按钮处于其他状态时更改它的外观。  
  
 在本示例中，可视结构包括以下部分：  
  
- 一个<xref:System.Windows.Controls.Border> <xref:System.Windows.FrameworkElement>名`RootElement`为的, 用作模板的根。  
  
- 一个<xref:System.Windows.Controls.Grid> , 它是的`RootElement`子级。  
  
- <xref:System.Windows.Controls.ContentPresenter>显示按钮内容的。 <xref:System.Windows.Controls.ContentPresenter>启用要显示的任何类型的对象。  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>使用 TemplateBinding 保留控件属性的功能  
 创建新<xref:System.Windows.Controls.ControlTemplate>的时, 您仍可能想要使用公共属性来更改控件的外观。 [TemplateBinding](../advanced/templatebinding-markup-extension.md)标记扩展将中<xref:System.Windows.Controls.ControlTemplate>元素的属性绑定到由控件定义的公共属性。 使用 [TemplateBinding](../advanced/templatebinding-markup-extension.md) 时，可让控件属性用作模板参数。 换言之，设置控件属性后，该值将传递到包含 [TemplateBinding](../advanced/templatebinding-markup-extension.md) 的元素。  
  
 下面的示例重复了前面示例的部分, 该部分使用[TemplateBinding](../advanced/templatebinding-markup-extension.md)标记扩展将中<xref:System.Windows.Controls.ControlTemplate>元素的属性绑定到由按钮定义的公共属性。  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 在此示例中, <xref:System.Windows.Controls.Grid>将其<xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>属性模板绑定到<xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>。 由于<xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>是绑定了模板, 因此你可以创建多个使用相同<xref:System.Windows.Controls.ControlTemplate>的按钮, <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>并在每个按钮上将设置为不同的值。 如果<xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>未将模板绑定到<xref:System.Windows.Controls.ControlTemplate>中的元素的属性, 则设置<xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>按钮的将不会影响按钮的外观。  
  
 请注意，两个属性的名称不必一样。 在前面的示例中, <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType>的<xref:System.Windows.Controls.Button>属性<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>是绑定到的<xref:System.Windows.Controls.ContentPresenter>属性的模板。 这样可以水平放置按钮的内容。 <xref:System.Windows.Controls.ContentPresenter>没有名为`HorizontalContentAlignment`的属性, 但<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType>可以绑定到<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>。 在通过模板绑定属性时，请确保目标属性和源属性属于同一类型。  
  
 <xref:System.Windows.Controls.Control>类定义一些属性, 控件模板必须使用这些属性才能在设置控件时对控件产生影响。 <xref:System.Windows.Controls.ControlTemplate>使用属性的方式取决于属性。 <xref:System.Windows.Controls.ControlTemplate>必须通过以下方式之一使用属性:  
  
- <xref:System.Windows.Controls.ControlTemplate>模板中的元素将绑定到属性。  
  
- 中<xref:System.Windows.Controls.ControlTemplate>的元素从父<xref:System.Windows.FrameworkElement>对象继承属性。  
  
 下表列出了由<xref:System.Windows.Controls.Control>类中的控件继承的视觉对象属性。 它还指示控件的默认控件模板是使用继承的属性值，还是必须通过模板绑定。  
  
|Property|使用方法|  
|--------------|------------------|  
|<xref:System.Windows.Controls.Control.Background%2A>|模板绑定|  
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|模板绑定|  
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|模板绑定|  
|<xref:System.Windows.Controls.Control.FontFamily%2A>|属性继承或模板绑定|  
|<xref:System.Windows.Controls.Control.FontSize%2A>|属性继承或模板绑定|  
|<xref:System.Windows.Controls.Control.FontStretch%2A>|属性继承或模板绑定|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|属性继承或模板绑定|  
|<xref:System.Windows.Controls.Control.Foreground%2A>|属性继承或模板绑定|  
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|模板绑定|  
|<xref:System.Windows.Controls.Control.Padding%2A>|模板绑定|  
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|模板绑定|  
  
 该表仅列出从<xref:System.Windows.Controls.Control>类继承的视觉对象属性。 除了表中列出的属性以外, 控件还可以继承父框架元素<xref:System.Windows.FrameworkElement.DataContext%2A>中<xref:System.Windows.FrameworkElement.Language%2A>的、 <xref:System.Windows.Controls.TextBlock.TextDecorations%2A>和属性。  
  
 此外<xref:System.Windows.Controls.ContentPresenter> , 如果位于的<xref:System.Windows.Controls.ControlTemplate>中<xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ContentPresenter>则将自动绑定到<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>和<xref:System.Windows.Controls.ContentControl.Content%2A>属性。 同样<xref:System.Windows.Controls.ItemsPresenter> , 位于的<xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ControlTemplate>中的将自动绑定到<xref:System.Windows.Controls.ItemsControl.Items%2A>和<xref:System.Windows.Controls.ItemsPresenter>属性。  
  
 下面的示例创建了两个按钮, <xref:System.Windows.Controls.ControlTemplate>这些按钮使用前面的示例中定义的。 该示例设置每<xref:System.Windows.Controls.Control.Background%2A>个<xref:System.Windows.Controls.Control.Foreground%2A>按钮的<xref:System.Windows.Controls.Control.FontSize%2A> 、和属性。 设置属性会产生影响, 因为它是中的<xref:System.Windows.Controls.ControlTemplate>模板绑定。 <xref:System.Windows.Controls.Control.Background%2A> 即使和<xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A>属性不是模板绑定的, 设置它们也有影响, 因为它们的值是继承的。  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 前面的示例生成类似于下图的输出。  
  
 ![两个按钮, 一个蓝色, 一个紫色。](./media/ndp-buttontwo.png "NDP_ButtonTwo")  
背景色不同的两个按钮  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>根据控件状态更改它的外观  
 显示默认外观的按钮与前面示例中按钮的差异在于，默认按钮在处于不同状态时会略有变化。 例如，在按下按钮或鼠标指针悬停在它的上方时，默认按钮的外观将发生变化。 尽管不<xref:System.Windows.Controls.ControlTemplate>会更改控件的功能, 但它确实更改了控件的可视行为。 可视行为描述控件处于某种状态下的外观。 若要了解控件功能和可视行为之间的差异，请考虑按钮示例。 按钮的功能是在单击<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件时引发事件, 但按钮的视觉行为是在指向或按下时更改其外观。  
  
 使用<xref:System.Windows.VisualState>对象可指定控件在处于某种状态时的外观。 包含一个<xref:System.Windows.Media.Animation.Storyboard> , 它更改中的<xref:System.Windows.Controls.ControlTemplate>元素的外观。 <xref:System.Windows.VisualState> 无需编写任何代码即可执行此操作, 因为控件的逻辑通过使用<xref:System.Windows.VisualStateManager>更改状态。 当控件输入<xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType>属性指定的状态时, 将<xref:System.Windows.Media.Animation.Storyboard>开始。 当控件退出状态时, 将<xref:System.Windows.Media.Animation.Storyboard>停止。  
  
 下面的示例演示<xref:System.Windows.VisualState> <xref:System.Windows.Controls.Button>当鼠标指针位于其上方时更改的外观。 通过更改的`BorderBrush`颜色来更改按钮的边框颜色。<xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Controls.ControlTemplate>如果你引用本主题开头部分的示例, 你将想起, 这<xref:System.Windows.Media.SolidColorBrush> `BorderBrush`是分配给<xref:System.Windows.Controls.Border.Background%2A>的<xref:System.Windows.Controls.Border>的名称。  
  
 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 该控件负责将各种状态定义为控件协定的一部分，这将在本主题后面的[通过了解控件协定自定义其他控件](#customizing_other_controls_by_understanding_the_control_contract)中进行详细讨论。 下表列出了为<xref:System.Windows.Controls.Button>指定的状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|普通|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针悬停在控件上方。|  
|已按下|CommonStates|已按下控件。|  
|已禁用|CommonStates|已禁用控件。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
  
 `CommonStates` `Normal` `MouseOver` `Pressed`定义两个状态组: 组包含、、和`Disabled`状态。 <xref:System.Windows.Controls.Button> `FocusStates` 组包含 `Focused` 和 `Unfocused` 状态。 同一状态组中的状态之间相互排斥。 控件在每个组中始终处于一种状态下。 例如, <xref:System.Windows.Controls.Button>即使鼠标指针未悬停在上, 也可以具有焦点, 因此`Focused`状态中的<xref:System.Windows.Controls.Button>可以是`MouseOver`、 `Pressed`或`Normal`状态。  
  
 将对象<xref:System.Windows.VisualState>添加到<xref:System.Windows.VisualStateGroup>对象。 将对象<xref:System.Windows.VisualStateGroup>添加<xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType>到附加属性。 下面的<xref:System.Windows.VisualState>示例定义`Normal`、 `MouseOver`和`Pressed`状态的对象, 这些对象都在组中。`CommonStates` <xref:System.Windows.VisualState.Name%2A>每个<xref:System.Windows.VisualState>的都与上表中的名称匹配。 省略 `Disabled` 状态和 `FocusStates` 组中的各种状态是为了使示例保持简短，但本主题末尾的完整示例将它们包括在内。  
  
> [!NOTE]
> 请确保设置<xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType>的<xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate>根的附加属性。  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 前面的示例生成类似于下图的输出。  
  
 ![带有自定义控件模板的按钮。](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
使用正常状态下的自定义控件模板的按钮  
  
 ![带有红色边框的按钮。](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
使用鼠标悬停状态下的自定义控件模板的按钮  
  
 ![按下的按钮上的边框是透明的。](./media/ndp-buttonpressed.png "NDP_ButtonPressed")  
使用按下状态下的自定义控件模板的按钮  
  
 若要查找附带在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的控件的可视状态，请参阅 [Control 样式和模板](control-styles-and-templates.md)。  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>指定控件在状态之间转换时的行为  
 在前面的示例中，按钮的外观在用户单击它时也会发生更改，但除非按钮按下整整一秒，否则用户将看不到效果。 默认情况下，动画需要一秒才会发生。 由于用户可能会在很少的时间内单击并释放按钮, 因此, 如果您<xref:System.Windows.Controls.ControlTemplate>将处于默认状态, 则视觉反馈将不会生效。  
  
 可以通过将对象添加<xref:System.Windows.VisualTransition> <xref:System.Windows.Controls.ControlTemplate>到来指定动画发生的时间量, 以将控件从一个状态平滑转换到另一个状态。 当你创建<xref:System.Windows.VisualTransition>时, 你可以指定以下一个或多个:  
  
- 在状态之间进行转换所需的时间。  
  
- 在转换的同时，控件外观发生的其他更改。  
  
- 应用于的<xref:System.Windows.VisualTransition>状态。  
  
### <a name="specifying-the-duration-of-a-transition"></a>指定转换的持续时间  
 可以通过设置<xref:System.Windows.VisualTransition.GeneratedDuration%2A>属性来指定转换所用的时间。 前面的示例有一个<xref:System.Windows.VisualState> , 它指定按钮的边框在按下按钮时变得透明, 但如果快速按下并释放按钮, 动画的时间可能会很长。 您可以使用<xref:System.Windows.VisualTransition>来指定控件转换为按下状态所需的时间量。 以下示例指定控件需要百分之一秒进入按下状态。  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>指定转换时控件外观发生的更改  
 <xref:System.Windows.VisualTransition> 包含在控件在状态之间<xref:System.Windows.Media.Animation.Storyboard>转换时开始的。 例如，可以指定控件从 `MouseOver` 状态转换到 `Normal` 状态时发生的某个动画。 下面的示例创建一个<xref:System.Windows.VisualTransition> , 它指定当用户将鼠标指针从按钮上移开时, 按钮的边框将变为蓝色, 然后更改为黄色, 然后在1.5 秒内变为黑色。  
  
 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>指定何时应用 VisualTransition  
 <xref:System.Windows.VisualTransition>可以限制为仅应用于某些状态, 也可以在控件在状态之间转换时应用。 在前面的示例中, <xref:System.Windows.VisualTransition>当控件`MouseOver`从状态转换`Pressed`为`Normal`状态时应用<xref:System.Windows.VisualTransition> ; 在该示例之前, 在控件进入状态时应用。 通过<xref:System.Windows.VisualTransition> 设置和<xref:System.Windows.VisualTransition.From%2A>属性来限制应用的时间。 <xref:System.Windows.VisualTransition.To%2A> 下表描述了从最严限制到最宽松限制的限制级别。  
  
|限制类型|起始值|目标值|  
|-------------------------|-------------------|-----------------|  
|从一个指定状态到另一个指定状态|的名称<xref:System.Windows.VisualState>|的名称<xref:System.Windows.VisualState>|  
|从任意状态到指定状态|未设置|的名称<xref:System.Windows.VisualState>|  
|从指定状态到任意状态|的名称<xref:System.Windows.VisualState>|未设置|  
|从任意状态到其他任意状态|未设置|未设置|  
  
 中可以有多<xref:System.Windows.VisualTransition>个引用相同状态的对象,但它们将按照上表指定的顺序使用。<xref:System.Windows.VisualStateGroup> 在下面的示例中, 有两<xref:System.Windows.VisualTransition>个对象。 当控件`Pressed`从状态转换<xref:System.Windows.VisualTransition> `MouseOver`到状态时, 将使用同时<xref:System.Windows.VisualTransition.From%2A>具有和<xref:System.Windows.VisualTransition.To%2A>的。 当控件从非 `Pressed` 的状态转换为 `MouseOver` 状态时，将使用另一种状态。  
  
 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 <xref:System.Windows.VisualStateGroup> <xref:System.Windows.VisualState> <xref:System.Windows.VisualTransition>具有一个<xref:System.Windows.VisualStateGroup.Transitions%2A>属性, 该属性包含应用于中的对象的对象。 <xref:System.Windows.VisualStateGroup> 作为作者, 你可以随意包含所需的<xref:System.Windows.VisualTransition>任何一个。 <xref:System.Windows.Controls.ControlTemplate> 但是, 如果<xref:System.Windows.VisualTransition.To%2A>将和<xref:System.Windows.VisualTransition.From%2A>属性设置为<xref:System.Windows.VisualTransition>不在中<xref:System.Windows.VisualStateGroup>的状态名称, 则将忽略。  
  
 下面的示例演示<xref:System.Windows.VisualStateGroup> `CommonStates`的。 此示例为每<xref:System.Windows.VisualTransition>个按钮的以下转换定义一个。  
  
- 转换为 `Pressed` 状态。  
  
- 转换为 `MouseOver` 状态。  
  
- 从 `Pressed` 状态转换为 `MouseOver` 状态。  
  
- 从 `MouseOver` 状态转换为 `Normal` 状态。  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>通过了解控件协定自定义其他控件  
 使用<xref:System.Windows.Controls.ControlTemplate>来指定其视觉对象 (通过使用<xref:System.Windows.FrameworkElement>对象) 和可视行为 (通过使用<xref:System.Windows.VisualState>对象) 的控件使用 part 控件模型。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4 附带的许多控件均使用此模型。 <xref:System.Windows.Controls.ControlTemplate>作者需要注意的部分是通过控制协定进行传递的。 了解控件协定的各个部件后，可以自定义使用部件控件模型的任意控件的外观。  
  
 控件协定具有三个元素：  
  
- 控件逻辑使用的可视元素。  
  
- 控件状态和每种状态所属的组。  
  
- 以可视方式影响控件的公共属性。  
  
### <a name="visual-elements-in-the-control-contract"></a>控件协定中的可视元素  
 有时<xref:System.Windows.FrameworkElement> , 控件的逻辑与<xref:System.Windows.Controls.ControlTemplate>中的相交互。 例如，控件可能会处理它的其中一个元素的事件。 当控件需要<xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate>在中查找特定的时, 它必须将该信息<xref:System.Windows.Controls.ControlTemplate>传递给作者。 控件使用<xref:System.Windows.TemplatePartAttribute>来传递所需的元素类型以及该元素的名称。 不<xref:System.Windows.Controls.Button>具有<xref:System.Windows.FrameworkElement>其控件协定中的部分, 但其他<xref:System.Windows.Controls.ComboBox>控件 (如) 执行。  
  
 下面的示例演示<xref:System.Windows.TemplatePartAttribute>在<xref:System.Windows.Controls.ComboBox>类上指定的对象。 的<xref:System.Windows.Controls.ComboBox>逻辑应在其`PART_Popup` <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.TextBox> 中<xref:System.Windows.Controls.ControlTemplate>找到名`PART_EditableTextBox`为的和命名的。  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 下面的示例演示了的<xref:System.Windows.Controls.ControlTemplate>简化<xref:System.Windows.Controls.ComboBox> , 其中包括<xref:System.Windows.Controls.ComboBox>类中的<xref:System.Windows.TemplatePartAttribute>对象指定的元素。  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>控件协定中的状态  
 控件状态也属于控件协定。 <xref:System.Windows.Controls.ControlTemplate>为创建的示例<xref:System.Windows.Controls.Button>演示如何根据其状态指定的外观。 <xref:System.Windows.Controls.Button> 为每个<xref:System.Windows.VisualState>指定的状态创建一个<xref:System.Windows.VisualStateGroup>, 并<xref:System.Windows.VisualState>将共享<xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A>中的所有对象放入中, 如[更改控件的外观 (具体取决](#changing_the_appearance_of_a_control_depending_on_its_state)于本主题前面部分的状态所述)。 第三方控件应使用<xref:System.Windows.TemplateVisualStateAttribute>来指定状态, 这使设计器工具 (如 Expression Blend) 能够公开控件的状态以创作控件模板。  
  
 若要查找 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中随附的控件的控件协定，请参阅 [Control 样式和模板](control-styles-and-templates.md)。  
  
### <a name="properties-in-the-control-contract"></a>控件协定中的属性  
 以可视方式影响控件的公共属性也包含在控件协定中。 可以设置这些属性来更改控件的外观, 而无需创建新<xref:System.Windows.Controls.ControlTemplate>的。 还可以使用[TemplateBinding](../advanced/templatebinding-markup-extension.md)标记扩展将中<xref:System.Windows.Controls.ControlTemplate>元素的属性绑定到由<xref:System.Windows.Controls.Button>定义的公共属性。  
  
 以下示例展示了按钮的控件协定。  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 创建<xref:System.Windows.Controls.ControlTemplate>时, 通常最简单的方法是从现有<xref:System.Windows.Controls.ControlTemplate>的开始, 对其进行更改。 可以执行以下操作之一来更改现有<xref:System.Windows.Controls.ControlTemplate>的:  
  
- 使用设计器（例如 Expression Blend），它可以提供用于创建控件模板的图形用户界面。 有关详细信息，请参阅[设置支持模板的控件的样式](https://go.microsoft.com/fwlink/?LinkId=161153)。  
  
- 获取默认值<xref:System.Windows.Controls.ControlTemplate>并对其进行编辑。 若要查找 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 随附的默认控件模板，请参阅[默认 WPF 主题](https://go.microsoft.com/fwlink/?LinkID=158252)。  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>完整的示例  
 下面的示例演示本主题<xref:System.Windows.Controls.Button>中讨论的完整<xref:System.Windows.Controls.ControlTemplate> 。  
  
 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>请参阅

- [样式设置和模板化](styling-and-templating.md)
