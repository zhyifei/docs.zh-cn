---
title: "创建具有可自定义外观的控件"
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
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4da96c3e33c6f7827619b408568fbbfe96c50a11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>创建具有可自定义外观的控件
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]使你能够创建可以自定义其外观的控件。 例如，你可以更改外观<xref:System.Windows.Controls.CheckBox>超越设置属性即可通过创建新<xref:System.Windows.Controls.ControlTemplate>。 下图显示<xref:System.Windows.Controls.CheckBox>使用默认<xref:System.Windows.Controls.ControlTemplate>和<xref:System.Windows.Controls.CheckBox>使用自定义<xref:System.Windows.Controls.ControlTemplate>。  
  
 ![一个具有默认控件模板的复选框。] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
一个具有默认控件模板的复选框  
  
 ![一个具有自定义控件模板的复选框。] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
一个具有自定义控件模板的复选框  
  
 如果你按照部件和状态模型创建的控件时，，将可自定义控件的外观。 如 Microsoft Expression Blend 的设计器工具支持的部件和状态的模型，因此当你按照此模型将在这些类型的应用程序中可自定义控件。  本主题讨论的部件和状态的模型以及如何创建您自己的控件时遵循它。 本主题使用的自定义控件，示例`NumericUpDown`，来说明此模型的基本原理。  `NumericUpDown`控件将显示一个数字的值，用户可以增加或减少通过单击控件的按钮。  下图显示`NumericUpDown`本主题中讨论的控件。  
  
 ![NumericUpDown 自定义控件。] (../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP_NumericUPDown")  
自定义的 NumericUpDown 控件  
  
 本主题包含以下各节：  
  
-   [先决条件](#prerequisites)  
  
-   [部件和状态模型](#parts_and_states_model)  
  
-   [在 ControlTemplate 中定义的可视结构和控件的可视行为](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [使用代码中的 ControlTemplate 的部分](#using_parts_of_the_controltemplate_in_code)  
  
-   [提供控件协定](#providing_the_control_contract)  
  
-   [完整的示例](#complete_example)  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>系统必备  
 本主题假定你知道如何创建一个新<xref:System.Windows.Controls.ControlTemplate>为现有控件，熟悉控件协定上的元素是什么，并了解中所述的概念[自定义的现有控件的外观创建 ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
> [!NOTE]
>  若要创建可以具有自定义其外观的控件，你必须创建继承自一个控件<xref:System.Windows.Controls.Control>类或它的某个子类以外的其他<xref:System.Windows.Controls.UserControl>。  继承自的控件<xref:System.Windows.Controls.UserControl>是一个控件，可以快速创建，但它不使用<xref:System.Windows.Controls.ControlTemplate>并且也不能自定义其外观。  
  
<a name="parts_and_states_model"></a>   
## <a name="parts-and-states-model"></a>部件和状态模型  
 部件和状态模型指定如何定义可视结构和控件的可视行为。 若要执行的部件和状态的模型，应执行以下操作：  
  
-   定义可视结构和可视行为<xref:System.Windows.Controls.ControlTemplate>的控件。  
  
-   控件的逻辑进行交互的控件模板部件时，请遵循某些最佳做法。  
  
-   提供控件协定，以指定应中包含什么<xref:System.Windows.Controls.ControlTemplate>。  
  
 在定义可视结构和可视行为<xref:System.Windows.Controls.ControlTemplate>的控件，应用程序的作者可以更改 visual 结构和你的控件的可视行为通过创建新<xref:System.Windows.Controls.ControlTemplate>而不编写代码。   必须提供控件协定，以告知应用程序作者其中<xref:System.Windows.FrameworkElement>对象和状态应在定义<xref:System.Windows.Controls.ControlTemplate>。 中的部件交互时，应遵循的一些最佳做法<xref:System.Windows.Controls.ControlTemplate>，以便你控件正确处理不完整<xref:System.Windows.Controls.ControlTemplate>。  如果你遵循这三个原则，应用程序的作者将能够创建<xref:System.Windows.Controls.ControlTemplate>为您的控件只是它们一样轻松可以控件随[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。  以下部分说明了每个详细信息中的这些建议。  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>在 ControlTemplate 中定义的可视结构和控件的可视行为  
 当使用的部件和状态的模型创建自定义控件时，你定义控件的可视结构和可视行为其<xref:System.Windows.Controls.ControlTemplate>而不是其逻辑中。  控件的可视结构是的复合<xref:System.Windows.FrameworkElement>构成控件的对象。  可视行为是在某个特定状态时，会出现控件的方法。   有关创建<xref:System.Windows.Controls.ControlTemplate>，用于指定可视结构和控件的可视行为，请参阅[通过创建 ControlTemplate 自定义现有的控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
 在示例中的`NumericUpDown`控件，可视结构包含两个<xref:System.Windows.Controls.Primitives.RepeatButton>控件和<xref:System.Windows.Controls.TextBlock>。  如果你的代码中添加这些控件`NumericUpDown`控件-在其构造函数，例如中的这些控件的位置将无法更改。  定义而不是在其代码中定义控件的可视结构和可视行为，你应在<xref:System.Windows.Controls.ControlTemplate>。  然后应用程序开发人员自定义按钮的位置和<xref:System.Windows.Controls.TextBlock>并指定所发生的行为时`Value`为负因为<xref:System.Windows.Controls.ControlTemplate>可替换。  
  
 下面的示例演示的可视结构`NumericUpDown`控件，其中包括<xref:System.Windows.Controls.Primitives.RepeatButton>以提高`Value`、<xref:System.Windows.Controls.Primitives.RepeatButton>以减少`Value`，和一个<xref:System.Windows.Controls.TextBlock>以显示`Value`。  
  
 [!code-xaml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 可视行为`NumericUpDown`控件是如果它是负数的值是以红色字体。  如果你更改<xref:System.Windows.Controls.TextBlock.Foreground%2A>的<xref:System.Windows.Controls.TextBlock>时在代码`Value`为负，`NumericUpDown`会始终显示为红色的负值。 指定在将控件的可视行为<xref:System.Windows.Controls.ControlTemplate>通过添加<xref:System.Windows.VisualState>对象添加到<xref:System.Windows.Controls.ControlTemplate>。  下面的示例演示<xref:System.Windows.VisualState>对象`Positive`和`Negative`状态。  `Positive`和`Negative`是互斥的 （控件将始终在两个中恰好有一个），因此该示例放入<xref:System.Windows.VisualState>到单个对象<xref:System.Windows.VisualStateGroup>。  当控件将进入`Negative`状态，<xref:System.Windows.Controls.TextBlock.Foreground%2A>的<xref:System.Windows.Controls.TextBlock>变为红色。  当控件处于`Positive`状态，<xref:System.Windows.Controls.TextBlock.Foreground%2A>返回到其原始值。  定义<xref:System.Windows.VisualState>中的对象<xref:System.Windows.Controls.ControlTemplate>中进一步讨论如何[通过创建 ControlTemplate 自定义现有的控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
> [!NOTE]
>  请务必设置<xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType>附加属性的根上<xref:System.Windows.FrameworkElement>的<xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## <a name="using-parts-of-the-controltemplate-in-code"></a>使用代码中的 ControlTemplate 的部分  
 A<xref:System.Windows.Controls.ControlTemplate>作者可能会省略<xref:System.Windows.FrameworkElement>或<xref:System.Windows.VisualState>对象，有意或误，但控件的逻辑可能需要这些部件才能正常运行。 部件和状态模型指定控件应该能够应对<xref:System.Windows.Controls.ControlTemplate>缺少<xref:System.Windows.FrameworkElement>或<xref:System.Windows.VisualState>对象。  你的控件时，应该不引发异常或报表错误<xref:System.Windows.FrameworkElement>， <xref:System.Windows.VisualState>，或<xref:System.Windows.VisualStateGroup>中缺少<xref:System.Windows.Controls.ControlTemplate>。 本部分介绍与之进行交互的建议的做法<xref:System.Windows.FrameworkElement>对象和管理状态。  
  
### <a name="anticipate-missing-frameworkelement-objects"></a>预计缺少 FrameworkElement 对象  
 在定义<xref:System.Windows.FrameworkElement>中的对象<xref:System.Windows.Controls.ControlTemplate>，控件的逻辑可能需要与其中一些进行交互。  例如，`NumericUpDown`控制订阅的按钮的<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件来增加或减少`Value`和设置<xref:System.Windows.Controls.TextBlock.Text%2A>属性<xref:System.Windows.Controls.TextBlock>到`Value`。 如果自定义<xref:System.Windows.Controls.ControlTemplate>省略<xref:System.Windows.Controls.TextBlock>或按钮，它是可接受的在控件失去其部分功能，但你应确保控件不会导致错误。 例如，如果<xref:System.Windows.Controls.ControlTemplate>不包含要更改的按钮`Value`、`NumericUpDown`丢失该功能，但使用的应用程序<xref:System.Windows.Controls.ControlTemplate>将继续运行。  
  
 下列方案将确保你的控件响应正确缺少<xref:System.Windows.FrameworkElement>对象：  
  
1.  设置`x:Name`每个属性<xref:System.Windows.FrameworkElement>，你需要在代码中引用。  
  
2.  定义了每个私有属性<xref:System.Windows.FrameworkElement>，需要进行交互。  
  
3.  订阅和取消订阅你的控件以处理任何事件<xref:System.Windows.FrameworkElement>属性的 set 访问器。  
  
4.  设置<xref:System.Windows.FrameworkElement>中定义的属性步骤 2<xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>方法。 这是最早的<xref:System.Windows.FrameworkElement>中<xref:System.Windows.Controls.ControlTemplate>供控件。 使用`x:Name`的<xref:System.Windows.FrameworkElement>即可使用它从<xref:System.Windows.Controls.ControlTemplate>。  
  
5.  检查<xref:System.Windows.FrameworkElement>不`null`之前访问其成员。  如果它是`null`，不报告错误。  
  
 下面的示例演示如何`NumericUpDown`与控件交互<xref:System.Windows.FrameworkElement>根据上面的列表中的建议的对象。  
  
 在以下示例中定义的可视结构`NumericUpDown`中控制<xref:System.Windows.Controls.ControlTemplate>、<xref:System.Windows.Controls.Primitives.RepeatButton>增加`Value`具有其`x:Name`属性设置为`UpButton`。  下面的示例声明一个名为属性`UpButtonElement`表示<xref:System.Windows.Controls.Primitives.RepeatButton>中声明<xref:System.Windows.Controls.ControlTemplate>。 `set`访问器首先取消订阅按钮的<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件如果`UpDownElement`不`null`，则会将设置属性，然后它所订阅的<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。 另外，还有定义，但不是下面所示，另一个属性<xref:System.Windows.Controls.Primitives.RepeatButton>、 调用`DownButtonElement`。  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 下面的示例演示<xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>为`NumericUpDown`控件。  该示例使用<xref:System.Windows.FrameworkElement.GetTemplateChild%2A>方法以获取<xref:System.Windows.FrameworkElement>对象从<xref:System.Windows.Controls.ControlTemplate>。  请注意，该示例能防范情况<xref:System.Windows.FrameworkElement.GetTemplateChild%2A>查找<xref:System.Windows.FrameworkElement>具有指定名称，并且不属于预期类型。 它也是一种最佳的做法，若要忽略具有指定的元素`x:Name`但将引起的错误的类型。  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 按照上一示例所示的做法，确保你的控件将继续运行时<xref:System.Windows.Controls.ControlTemplate>缺少<xref:System.Windows.FrameworkElement>。  
  
### <a name="use-the-visualstatemanager-to-manage-states"></a>使用 VisualStateManager 来管理状态  
 <xref:System.Windows.VisualStateManager>跟踪控件的状态以及执行状态间转换所需的逻辑。 当你将添加<xref:System.Windows.VisualState>对象添加到<xref:System.Windows.Controls.ControlTemplate>，你将其添加到<xref:System.Windows.VisualStateGroup>并添加<xref:System.Windows.VisualStateGroup>到<xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType>附加属性，以便<xref:System.Windows.VisualStateManager>有权访问它们。  
  
 下面的示例重复前面的示例显示<xref:System.Windows.VisualState>对象对应于`Positive`和`Negative`控件的状态。 <xref:System.Windows.Media.Animation.Storyboard>中`Negative`<xref:System.Windows.VisualState>变为<xref:System.Windows.Controls.TextBlock.Foreground%2A>的<xref:System.Windows.Controls.TextBlock>红色。   当`NumericUpDown`控件处于`Negative`状态时，在情节提要`Negative`状态开始。  则<xref:System.Windows.Media.Animation.Storyboard>中`Negative`状态将停止，当控件返回到`Positive`状态。  `Positive` <xref:System.Windows.VisualState>不需要包含<xref:System.Windows.Media.Animation.Storyboard>因为时<xref:System.Windows.Media.Animation.Storyboard>为`Negative`停止，<xref:System.Windows.Controls.TextBlock.Foreground%2A>返回到其原始的颜色。  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 请注意，<xref:System.Windows.Controls.TextBlock>指定一个名称，但<xref:System.Windows.Controls.TextBlock>不在的控件协定`NumericUpDown`因为控件的逻辑永远不会引用<xref:System.Windows.Controls.TextBlock>。  元素中引用<xref:System.Windows.Controls.ControlTemplate>具有名称，但不是需要将其控件协定的一部分，因为新<xref:System.Windows.Controls.ControlTemplate>控件可能不需要引用该元素。  例如，创建一个新的人<xref:System.Windows.Controls.ControlTemplate>为`NumericUpDown`可能会决定不指示`Value`通过更改为负<xref:System.Windows.Controls.Control.Foreground%2A>。  在这种情况下，都不的代码也不<xref:System.Windows.Controls.ControlTemplate>引用<xref:System.Windows.Controls.TextBlock>按名称。  
  
 控件的逻辑负责更改控件的状态。 下面的示例演示`NumericUpDown`控制调用<xref:System.Windows.VisualStateManager.GoToState%2A>方法进入`Positive`状态时`Value`0 或更高版本和`Negative`状态时`Value`小于 0。  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 <xref:System.Windows.VisualStateManager.GoToState%2A>方法执行所需启动和停止将情节提要相应的逻辑。 当控件调用<xref:System.Windows.VisualStateManager.GoToState%2A>以更改其状态，<xref:System.Windows.VisualStateManager>执行下列任务：  
  
-   如果<xref:System.Windows.VisualState>控件转到具有<xref:System.Windows.Media.Animation.Storyboard>，情节提要开始。 然后，如果<xref:System.Windows.VisualState>来自控件具有<xref:System.Windows.Media.Animation.Storyboard>，情节提要结束。  
  
-   如果控件已处于指定，则状态<xref:System.Windows.VisualStateManager.GoToState%2A>不执行任何操作并返回`true`。  
  
-   如果指定的状态中不存在<xref:System.Windows.Controls.ControlTemplate>的`control`，<xref:System.Windows.VisualStateManager.GoToState%2A>不执行任何操作并返回`false`。  
  
#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>用于使用 VisualStateManager 的最佳做法  
 建议你以下操作来维护控件的状态：  
  
-   使用属性来跟踪其状态。  
  
-   创建一个帮助器方法状态之间转换。  
  
 `NumericUpDown`控件使用其`Value`属性来跟踪它是否处于`Positive`或`Negative`状态。  `NumericUpDown`控件还定义`Focused`和`UnFocused`状态，哪些跟踪<xref:System.Windows.UIElement.IsFocused%2A>属性。 如果使用不自然对应于控件的属性的状态，则可以定义一个私有属性来跟踪的状态。  
  
 单个方法来更新所有状态集中调用<xref:System.Windows.VisualStateManager>并使代码更易于管理。 下面的示例演示`NumericUpDown`控件的帮助器方法， `UpdateStates`。 当`Value`大于或等于 0，<xref:System.Windows.Controls.Control>处于`Positive`状态。  当`Value`是小于 0，控件是否处于`Negative`状态。  当<xref:System.Windows.UIElement.IsFocused%2A>是`true`，该控件处于`Focused`状态; 否则为它是在`Unfocused`状态。  控件可以调用`UpdateStates`每当它需要更改其状态，而不考虑什么状态发生更改。  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 如果传递到的状态名称<xref:System.Windows.VisualStateManager.GoToState%2A>时控件已处于该状态<xref:System.Windows.VisualStateManager.GoToState%2A>不执行任何操作，因此无需检查控件的当前状态。  例如，如果`Value`从一个负数更改为另一个负数的情节提要`Negative`状态是否未中断，用户将不会看到在控件中的更改。  
  
 <xref:System.Windows.VisualStateManager>使用<xref:System.Windows.VisualStateGroup>对象以确定要退出时调用哪种状态<xref:System.Windows.VisualStateManager.GoToState%2A>。 控件将始终处于一种状态为每个<xref:System.Windows.VisualStateGroup>中定义其<xref:System.Windows.Controls.ControlTemplate>，才离开一种状态时将它放入另一种状态从同一个<xref:System.Windows.VisualStateGroup>。 例如，<xref:System.Windows.Controls.ControlTemplate>的`NumericUpDown`控件定义`Positive`和`Negative`<xref:System.Windows.VisualState>中一个对象<xref:System.Windows.VisualStateGroup>和`Focused`和`Unfocused`<xref:System.Windows.VisualState>中另一个对象。 (你可以看到`Focused`和`Unfocused`<xref:System.Windows.VisualState>中定义[完整示例](#complete_example)当控件从本主题中的部分`Positive`状态`Negative`状态，或者反之亦然，控件将保持在`Focused`或`Unfocused`状态。  
  
 有以下三个典型位置，其中可能会更改控件的状态：  
  
-   当<xref:System.Windows.Controls.ControlTemplate>应用于<xref:System.Windows.Controls.Control>。  
  
-   属性更改时。  
  
-   事件发生时。  
  
 下面的示例演示正在更新的状态`NumericUpDown`在这些情况下的控件。  
  
 你应更新中的控件的状态<xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>方法，以便该控件会出现在正确状态时<xref:System.Windows.Controls.ControlTemplate>应用。 下面的示例调用`UpdateStates`中<xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>以确保该控件是否处于适当的状态。  例如，假设你创建`NumericUpDown`控制，并将其<xref:System.Windows.Controls.Control.Foreground%2A>为绿色和`Value`为-5。  如果不调用`UpdateStates`时<xref:System.Windows.Controls.ControlTemplate>应用于`NumericUpDown`控件，该控件不在`Negative`状态，并且值为绿色而不是红色。  必须调用`UpdateStates`以将控件放入`Negative`状态。  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 通常需要更新在属性更改时控件的状态。 下面的示例演示整个`ValueChangedCallback`方法。 因为`ValueChangedCallback`时，将调用`Value`发生更改，方法调用`UpdateStates`以防`Value`更改，不再是正为负，反之亦然。 是可接受调用`UpdateStates`时`Value`更改但仍保持正数或负数，因为在这种情况下，该控件不会更改状态。  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 你可能还需要更新状态事件发生时。 下面的示例演示`NumericUpDown`调用`UpdateStates`上<xref:System.Windows.Controls.Control>来处理<xref:System.Windows.UIElement.GotFocus>事件。  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 <xref:System.Windows.VisualStateManager>可帮助你管理控件的状态。 通过使用<xref:System.Windows.VisualStateManager>，确保你的控件正确状态之间转换。  如果你按照用于使用本节中所述的建议<xref:System.Windows.VisualStateManager>，控件的代码将继续保持具可读性且更容易维护。  
  
<a name="providing_the_control_contract"></a>   
## <a name="providing-the-control-contract"></a>提供控件协定  
 提供控件协定以便<xref:System.Windows.Controls.ControlTemplate>作者将知道要在模板中放置的内容。 控件协定具有三个元素：  
  
-   控件逻辑使用的可视元素。  
  
-   控件状态和每种状态所属的组。  
  
-   以可视方式影响控件的公共属性。  
  
 创建一个新的人员<xref:System.Windows.Controls.ControlTemplate>需要知道<xref:System.Windows.FrameworkElement>控件的逻辑使用的对象，哪种类型的每个对象，且其名称。 A<xref:System.Windows.Controls.ControlTemplate>作者还需要知道的控件可以在中，每个可能状态和名称<xref:System.Windows.VisualStateGroup>状态为。  
  
 返回到`NumericUpDown`示例中，控件预期<xref:System.Windows.Controls.ControlTemplate>具有以下<xref:System.Windows.FrameworkElement>对象：  
  
-   A<xref:System.Windows.Controls.Primitives.RepeatButton>调用`UpButton`。  
  
-   A<xref:System.Windows.Controls.Primitives.RepeatButton>调用`DownButton.`  
  
 控件可以处于以下状态：  
  
-   在`ValueStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   在`FocusStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 若要指定什么<xref:System.Windows.FrameworkElement>对象控件预期，则使用<xref:System.Windows.TemplatePartAttribute>，它指定的名称和预期元素的类型。  指定控件的可能的状态，则使用<xref:System.Windows.TemplateVisualStateAttribute>，它指定状态的名称以及哪些<xref:System.Windows.VisualStateGroup>它属于。  Put<xref:System.Windows.TemplatePartAttribute>和<xref:System.Windows.TemplateVisualStateAttribute>上控件的类定义。  
  
 任何会影响你的控件的外观的公共属性还是控件协定的一部分。  
  
 下面的示例指定<xref:System.Windows.FrameworkElement>对象和状态`NumericUpDown`控件。  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>完整的示例  
 下面的示例是整个<xref:System.Windows.Controls.ControlTemplate>为`NumericUpDown`控件。  
  
 [!code-xaml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 下面的示例演示的逻辑`NumericUpDown`。  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## <a name="see-also"></a>请参阅  
 [通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)  
 [控件自定义](../../../../docs/framework/wpf/controls/control-customization.md)
