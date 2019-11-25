---
title: 创建具有可自定义外观的控件
ms.date: 03/30/2017
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
ms.openlocfilehash: d9cf092cf47d4fb70b15033d039777d3279b633a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283564"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>创建具有可自定义外观的控件

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 使您能够创建可自定义外观的控件。 例如，你可以通过创建新 <xref:System.Windows.Controls.ControlTemplate>来更改 <xref:System.Windows.Controls.CheckBox> 的外观，而不是设置属性将执行的操作。 下图显示了使用默认 <xref:System.Windows.Controls.ControlTemplate> 的 <xref:System.Windows.Controls.CheckBox> 和使用自定义 <xref:System.Windows.Controls.ControlTemplate>的 <xref:System.Windows.Controls.CheckBox>。

![一个具有默认控件模板的复选框。](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
一个具有默认控件模板的复选框

![一个具有自定义控件模板的复选框。](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
一个具有自定义控件模板的复选框

如果在创建控件时遵循 "部件" 和 "状态" 模型，则可自定义控件的外观。 设计器工具（如 Blend for Visual Studio）支持部件和状态模型，因此，在遵循此模型时，可以在这些类型的应用程序中自定义控件。  本主题讨论了部件和状态模型，以及如何在创建自己的控件时执行该操作。 本主题使用自定义控件 `NumericUpDown`的示例，演示此模型的原理。  `NumericUpDown` 控件显示一个数值，用户可以通过单击控件的按钮来增加或减少该值。  下图显示了本主题中讨论的 `NumericUpDown` 控件。

![NumericUpDown 自定义控件。](./media/ndp-numericupdown.png "NDP_NumericUPDown")
自定义 NumericUpDown 控件

本主题包含以下各节：

- [先决条件](#prerequisites)

- [部件和状态模型](#parts_and_states_model)

- [定义 System.windows.controls.controltemplate> 中控件的可视结构和可视行为](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)

- [在代码中使用部分 System.windows.controls.controltemplate>](#using_parts_of_the_controltemplate_in_code)

- [提供控件协定](#providing_the_control_contract)

- [完整示例](#complete_example)

<a name="prerequisites"></a>

## <a name="prerequisites"></a>先决条件

本主题假设你知道如何为现有控件创建新的 <xref:System.Windows.Controls.ControlTemplate>，熟悉控件协定上的元素，并了解在[创建控件模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)中所述的概念。

> [!NOTE]
> 若要创建可自定义其外观的控件，您必须创建一个继承自 <xref:System.Windows.Controls.Control> 类或 <xref:System.Windows.Controls.UserControl>以外的子类之一的控件。  继承自 <xref:System.Windows.Controls.UserControl> 的控件是可快速创建的控件，但不使用 <xref:System.Windows.Controls.ControlTemplate>，因此无法自定义其外观。

<a name="parts_and_states_model"></a>

## <a name="parts-and-states-model"></a>部件和状态模型

部件和状态模型指定如何定义控件的可视结构和可视行为。 若要遵循 "部件" 和 "状态" 模型，应执行以下操作：

- 定义控件 <xref:System.Windows.Controls.ControlTemplate> 中的可视结构和可视行为。

- 当控件的逻辑与控件模板的各个部分进行交互时，请遵循某些最佳实践。

- 提供控件协定以指定 <xref:System.Windows.Controls.ControlTemplate>中应包括的内容。

当你在控件的 <xref:System.Windows.Controls.ControlTemplate> 中定义可视结构和视觉对象行为时，应用程序作者可以通过创建新的 <xref:System.Windows.Controls.ControlTemplate> 而不是编写代码来更改控件的可视结构和视觉行为。   您必须提供一个控制协定，用于告知应用程序作者应在 <xref:System.Windows.Controls.ControlTemplate>中定义 <xref:System.Windows.FrameworkElement> 对象和状态。 当你与 <xref:System.Windows.Controls.ControlTemplate> 中的部件进行交互时，应遵循一些最佳做法，以便控件正确处理不完整的 <xref:System.Windows.Controls.ControlTemplate>。  如果你遵循这三个原则，应用程序作者将能够为你的控件创建 <xref:System.Windows.Controls.ControlTemplate>，就像对随 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供的控件一样。  以下部分详细说明每个建议。

<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>

## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>定义 System.windows.controls.controltemplate> 中控件的可视结构和可视行为

使用 "部件" 和 "状态" 模型创建自定义控件时，可以在其 <xref:System.Windows.Controls.ControlTemplate> 而不是其逻辑中定义控件的可视结构和视觉行为。  控件的可视结构是组成控件 <xref:System.Windows.FrameworkElement> 对象的组合。  视觉对象行为是控件在处于某种状态时的显示方式。   有关创建指定控件的可视结构和可视行为的 <xref:System.Windows.Controls.ControlTemplate> 的详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。

在 `NumericUpDown` 控件的示例中，可视结构包括两个 <xref:System.Windows.Controls.Primitives.RepeatButton> 控件和一个 <xref:System.Windows.Controls.TextBlock>。  如果在 `NumericUpDown` 控件的代码中添加这些控件--在其构造函数中，例如，这些控件的位置将为方式更改。  你应在 <xref:System.Windows.Controls.ControlTemplate>中定义控件的可视结构和可视行为，而不是在其代码中定义它。  然后，应用程序开发人员可以自定义按钮和 <xref:System.Windows.Controls.TextBlock> 的位置，并指定当 `Value` 为负值时所发生的行为，因为 <xref:System.Windows.Controls.ControlTemplate> 可以被替换。

下面的示例演示 `NumericUpDown` 控件的可视结构，其中包括要增加 `Value`的 <xref:System.Windows.Controls.Primitives.RepeatButton>、要减小的 <xref:System.Windows.Controls.Primitives.RepeatButton> `Value`以及用于显示 <xref:System.Windows.Controls.TextBlock> 的 `Value`。

[!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]

`NumericUpDown` 控件的可视行为是：如果该值为负数，则该值为红色。  如果在 `Value` 为负数时更改代码中 <xref:System.Windows.Controls.TextBlock> 的 <xref:System.Windows.Controls.TextBlock.Foreground%2A>，则 `NumericUpDown` 将始终显示一个红色的负值。 您可以通过将 <xref:System.Windows.VisualState> 对象添加到 <xref:System.Windows.Controls.ControlTemplate>指定 <xref:System.Windows.Controls.ControlTemplate> 控件的可视行为。  下面的示例演示了 `Positive` 和 `Negative` 状态的 <xref:System.Windows.VisualState> 对象。  `Positive` 和 `Negative` 互斥（控件始终只是两个），因此该示例将 <xref:System.Windows.VisualState> 对象置于单个 <xref:System.Windows.VisualStateGroup>中。  当控件进入 `Negative` 状态时，<xref:System.Windows.Controls.TextBlock> 的 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 变成红色。  当控件处于 `Positive` 状态时，<xref:System.Windows.Controls.TextBlock.Foreground%2A> 返回到其原始值。  为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)中进一步讨论了在 <xref:System.Windows.Controls.ControlTemplate> 中定义 <xref:System.Windows.VisualState> 对象。

> [!NOTE]
> 请确保在 <xref:System.Windows.Controls.ControlTemplate>的根 <xref:System.Windows.FrameworkElement> 上设置 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 附加属性。

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

<a name="using_parts_of_the_controltemplate_in_code"></a>

## <a name="using-parts-of-the-controltemplate-in-code"></a>在代码中使用部分 System.windows.controls.controltemplate>

<xref:System.Windows.Controls.ControlTemplate> 作者可能 <xref:System.Windows.FrameworkElement> 或错误地省略或 <xref:System.Windows.VisualState> 对象，但控件的逻辑可能需要这些部分才能正常运行。 Parts 和状态模型指定您的控件应对 <xref:System.Windows.Controls.ControlTemplate> 缺少 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.VisualState> 对象。  如果 <xref:System.Windows.Controls.ControlTemplate>中缺少 <xref:System.Windows.FrameworkElement>、<xref:System.Windows.VisualState>或 <xref:System.Windows.VisualStateGroup>，则控件不应引发异常，也不会报告错误。 本部分介绍与 <xref:System.Windows.FrameworkElement> 对象和管理状态交互的建议做法。

### <a name="anticipate-missing-frameworkelement-objects"></a>预计缺少 FrameworkElement 对象

在 <xref:System.Windows.Controls.ControlTemplate>中定义 <xref:System.Windows.FrameworkElement> 对象时，控件的逻辑可能需要与其中一些对象进行交互。  例如，`NumericUpDown` 控件订阅按钮的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件以提高或降低 `Value`，并将 <xref:System.Windows.Controls.TextBlock> 的 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性设置为 `Value`。 如果自定义 <xref:System.Windows.Controls.ControlTemplate> 省略了 <xref:System.Windows.Controls.TextBlock> 或按钮，则控件将失去其某些功能，但应确保控件不会导致错误。 例如，如果 <xref:System.Windows.Controls.ControlTemplate> 不包含更改 `Value`的按钮，`NumericUpDown` 将失去该功能，但使用 <xref:System.Windows.Controls.ControlTemplate> 的应用程序将继续运行。

以下做法可确保控件正确响应缺少的 <xref:System.Windows.FrameworkElement> 对象：

1. 为需要在代码中引用的每个 <xref:System.Windows.FrameworkElement> 设置 `x:Name` 特性。

2. 定义要与之交互的每个 <xref:System.Windows.FrameworkElement> 的专用属性。

3. 订阅和取消订阅 <xref:System.Windows.FrameworkElement> 属性的 set 访问器中控件处理的任何事件。

4. 设置在 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 方法的步骤2中定义的 <xref:System.Windows.FrameworkElement> 属性。 这是可用于控件的 <xref:System.Windows.Controls.ControlTemplate> 中 <xref:System.Windows.FrameworkElement> 的最早的。 使用 <xref:System.Windows.FrameworkElement> 的 `x:Name` 从 <xref:System.Windows.Controls.ControlTemplate>获取它。

5. 在访问其成员之前，请检查是否未 `null` <xref:System.Windows.FrameworkElement>。  如果 `null`，则不报告错误。

下面的示例演示 `NumericUpDown` 控件如何根据前面列表中的建议与 <xref:System.Windows.FrameworkElement> 对象进行交互。

在 <xref:System.Windows.Controls.ControlTemplate>中定义 `NumericUpDown` 控件的可视结构的示例中，增加 `Value` 的 <xref:System.Windows.Controls.Primitives.RepeatButton> 的 `x:Name` 特性设置为 `UpButton`。  下面的示例声明一个名为 `UpButtonElement` 的属性，该属性表示在 <xref:System.Windows.Controls.ControlTemplate>中声明的 <xref:System.Windows.Controls.Primitives.RepeatButton>。 `set` 访问器首先取消订阅按钮的 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件（如果 `UpDownElement` 未 `null`），然后设置属性，然后订阅 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。 另外，还为其他 <xref:System.Windows.Controls.Primitives.RepeatButton>（称为 `DownButtonElement`）定义了一个属性。

[!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
[!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]

下面的示例演示了 `NumericUpDown` 控件的 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>。  该示例使用 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 方法从 <xref:System.Windows.Controls.ControlTemplate>获取 <xref:System.Windows.FrameworkElement> 对象。  请注意，该示例可防止 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 查找指定名称不是预期类型的 <xref:System.Windows.FrameworkElement> 的情况。 如果忽略具有指定 `x:Name` 但类型错误的元素，则这也是一种最佳做法。

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

按照前面示例中所示的做法，确保当 <xref:System.Windows.Controls.ControlTemplate> 缺少 <xref:System.Windows.FrameworkElement>时，控件将继续运行。

### <a name="use-the-visualstatemanager-to-manage-states"></a>使用 VisualStateManager 管理状态

<xref:System.Windows.VisualStateManager> 跟踪控件的状态，并执行在状态之间转换所需的逻辑。 向 <xref:System.Windows.Controls.ControlTemplate>中添加 <xref:System.Windows.VisualState> 对象时，请将它们添加到 <xref:System.Windows.VisualStateGroup>，并将 <xref:System.Windows.VisualStateGroup> 添加到 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 附加属性，以便 <xref:System.Windows.VisualStateManager> 有权访问它们。

下面的示例重复了前面的示例，该示例显示了与控件的 `Positive` 和 `Negative` 状态相对应的 <xref:System.Windows.VisualState> 对象。 `Negative`中的 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.VisualState> 将 <xref:System.Windows.Controls.TextBlock> 的 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 变为红色。   如果 `NumericUpDown` 控件处于 `Negative` 状态，则处于 `Negative` 状态的情节提要将开始。  当控件返回到 `Positive` 状态时，`Negative` 状态中的 <xref:System.Windows.Media.Animation.Storyboard> 将停止。  `Positive`<xref:System.Windows.VisualState> 不需要包含 <xref:System.Windows.Media.Animation.Storyboard>，因为当 `Negative` 的 <xref:System.Windows.Media.Animation.Storyboard> 停止时，<xref:System.Windows.Controls.TextBlock.Foreground%2A> 将恢复为其原始颜色。

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

请注意，<xref:System.Windows.Controls.TextBlock> 被赋予一个名称，但 <xref:System.Windows.Controls.TextBlock> 不在 `NumericUpDown` 的控制协定中，因为该控件的逻辑从不引用该 <xref:System.Windows.Controls.TextBlock>。  <xref:System.Windows.Controls.ControlTemplate> 中引用的元素具有名称，但不需要属于控件协定，因为控件的新 <xref:System.Windows.Controls.ControlTemplate> 可能不需要引用该元素。  例如，为 `NumericUpDown` 创建新 <xref:System.Windows.Controls.ControlTemplate> 的用户可能会通过更改 <xref:System.Windows.Controls.Control.Foreground%2A>来决定不指示 `Value` 为负数。  在这种情况下，代码和 <xref:System.Windows.Controls.ControlTemplate> 都不会按名称引用 <xref:System.Windows.Controls.TextBlock>。

控件的逻辑负责更改控件的状态。 下面的示例演示当 `Value` 为0或更大时，`NumericUpDown` 控件将调用 <xref:System.Windows.VisualStateManager.GoToState%2A> 方法进入 `Positive` 状态，当 `Negative` 小于0时，将调用 `Value` 状态。

[!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
[!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]

<xref:System.Windows.VisualStateManager.GoToState%2A> 方法执行相应的启动和停止演示图板所需的逻辑。 如果控件调用 <xref:System.Windows.VisualStateManager.GoToState%2A> 来更改其状态，则 <xref:System.Windows.VisualStateManager> 执行以下操作：

- 如果控件将具有 <xref:System.Windows.Media.Animation.Storyboard><xref:System.Windows.VisualState>，则情节提要将开始。 然后，如果控件所来自的 <xref:System.Windows.VisualState> 具有 <xref:System.Windows.Media.Animation.Storyboard>，则情节提要将结束。

- 如果控件已经处于指定的状态，<xref:System.Windows.VisualStateManager.GoToState%2A> 不会执行任何操作并返回 `true`。

- 如果指定的状态不存在于 `control`的 <xref:System.Windows.Controls.ControlTemplate> 中，则 <xref:System.Windows.VisualStateManager.GoToState%2A> 不会执行任何操作并返回 `false`。

#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>使用 VisualStateManager 的最佳做法

建议您执行以下操作来维护控件的状态：

- 使用属性跟踪其状态。

- 创建用于在状态间转换的帮助器方法。

`NumericUpDown` 控件使用其 `Value` 属性来跟踪它是否处于 `Positive` 或 `Negative` 状态。  `NumericUpDown` 控件还定义了 `Focused` 和 `UnFocused` 状态，这将跟踪 <xref:System.Windows.UIElement.IsFocused%2A> 属性。 如果使用的状态并不自然对应于控件的属性，则可以定义一个私有属性来跟踪状态。

更新所有状态的单个方法会将调用集中到 <xref:System.Windows.VisualStateManager> 并使代码保持可管理。 下面的示例演示 `NumericUpDown` 控件的帮助器方法，`UpdateStates`。 当 `Value` 大于或等于0时，<xref:System.Windows.Controls.Control> 处于 `Positive` 状态。  当 `Value` 小于0时，控件处于 `Negative` 状态。  当 `true`<xref:System.Windows.UIElement.IsFocused%2A> 时，控件处于 `Focused` 状态;否则，它处于 `Unfocused` 状态。  无论什么状态发生变化，控件都可以在需要更改其状态时调用 `UpdateStates`。

[!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
[!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]

如果在控件已经处于该状态时将状态名称传递到 <xref:System.Windows.VisualStateManager.GoToState%2A>，则 <xref:System.Windows.VisualStateManager.GoToState%2A> 不会执行任何操作，因此不需要检查控件的当前状态。  例如，如果 `Value` 从一个负数更改为另一个负数，则 `Negative` 状态的情节提要不会中断，用户将看不到控件中的更改。

<xref:System.Windows.VisualStateManager> 使用 <xref:System.Windows.VisualStateGroup> 对象确定在调用 <xref:System.Windows.VisualStateManager.GoToState%2A>时要退出的状态。 对于在其 <xref:System.Windows.Controls.ControlTemplate> 中定义的每个 <xref:System.Windows.VisualStateGroup>，控件始终处于一种状态，并且仅当进入同一 <xref:System.Windows.VisualStateGroup>的另一状态时才会离开状态。 例如，`NumericUpDown` 控件的 <xref:System.Windows.Controls.ControlTemplate> 定义一个 <xref:System.Windows.VisualState> 中的 `Positive` 和 `Negative`<xref:System.Windows.VisualStateGroup> 对象，而在另一个 `Focused` 中定义 `Unfocused`和 <xref:System.Windows.VisualState> 对象。 （当控件从 `Positive` 状态转为 `Negative` 状态时，可以查看本主题的 "[完整示例](#complete_example)" 部分中定义的 `Focused` 和 `Unfocused`<xref:System.Windows.VisualState>，反之亦然，控件仍处于 `Focused` 或 `Unfocused` 状态。

有三个典型位置，控件的状态可能会发生更改：

- 将 <xref:System.Windows.Controls.ControlTemplate> 应用于 <xref:System.Windows.Controls.Control>。

- 当属性发生更改时。

- 事件发生时。

下面的示例演示如何在这些情况下更新 `NumericUpDown` 控件的状态。

应在 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 方法中更新控件的状态，以便在应用 <xref:System.Windows.Controls.ControlTemplate> 时，控件显示为正确的状态。 下面的示例在 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 中调用 `UpdateStates`，以确保控件处于适当的状态。  例如，假设您创建一个 `NumericUpDown` 控件，然后将其 <xref:System.Windows.Controls.Control.Foreground%2A> 设置为绿色，并 `Value` 设置为-5。  如果在将 <xref:System.Windows.Controls.ControlTemplate> 应用到 `NumericUpDown` 控件时不调用 `UpdateStates`，则控件不处于 `Negative` 状态，并且值为绿色而不是红色。  必须调用 `UpdateStates` 将控件置于 `Negative` 状态。

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

当属性更改时，通常需要更新控件的状态。 下面的示例演示了整个 `ValueChangedCallback` 方法。 由于在 `Value` 更改时调用 `ValueChangedCallback`，因此该方法会调用 `UpdateStates`，以防 `Value` 从正值变为负，反之亦然。 当 `Value` 更改但保持为正数或负数时，可以接受调用 `UpdateStates`，因为在这种情况下，控件将不会更改状态。

[!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
[!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]

可能还需要在发生事件时更新状态。 下面的示例演示 `NumericUpDown` 对 <xref:System.Windows.Controls.Control> 调用 `UpdateStates` 来处理 <xref:System.Windows.UIElement.GotFocus> 事件。

[!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
[!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]

<xref:System.Windows.VisualStateManager> 可帮助你管理控件的状态。 通过使用 <xref:System.Windows.VisualStateManager>，可以确保控件正确地在状态之间转换。  如果遵循本部分中所述的建议来处理 <xref:System.Windows.VisualStateManager>，则控件的代码将保持可读和可维护性。

<a name="providing_the_control_contract"></a>

## <a name="providing-the-control-contract"></a>提供控件协定

提供控件协定，以便 <xref:System.Windows.Controls.ControlTemplate> 作者知道要在模板中放置的内容。 控件协定具有三个元素：

- 控件逻辑使用的可视元素。

- 控件状态和每种状态所属的组。

- 以可视方式影响控件的公共属性。

创建新 <xref:System.Windows.Controls.ControlTemplate> 的人员需要知道控件的逻辑使用的 <xref:System.Windows.FrameworkElement> 对象、每个对象的类型以及其名称。 <xref:System.Windows.Controls.ControlTemplate> 作者还需要知道控件可处于的每个可能状态的名称，以及该状态 <xref:System.Windows.VisualStateGroup>。

返回 `NumericUpDown` 示例，控件要求 <xref:System.Windows.Controls.ControlTemplate> 具有以下 <xref:System.Windows.FrameworkElement> 对象：

- 名为 `UpButton`的 <xref:System.Windows.Controls.Primitives.RepeatButton>。

- 名为 `DownButton.` 的 <xref:System.Windows.Controls.Primitives.RepeatButton>

 控件可以处于以下状态：

- 在 `ValueStates`<xref:System.Windows.VisualStateGroup>

  - `Positive`

  - `Negative`

- 在 `FocusStates`<xref:System.Windows.VisualStateGroup>

  - `Focused`

  - `Unfocused`

若要指定控件需要的 <xref:System.Windows.FrameworkElement> 对象，请使用 <xref:System.Windows.TemplatePartAttribute>，它指定预期元素的名称和类型。  若要指定控件的可能状态，请使用 <xref:System.Windows.TemplateVisualStateAttribute>，它指定状态的名称以及它所属 <xref:System.Windows.VisualStateGroup>。  将 <xref:System.Windows.TemplatePartAttribute> 和 <xref:System.Windows.TemplateVisualStateAttribute> 放在控件的类定义上。

任何影响控件外观的公共属性也属于控件协定。

下面的示例为 `NumericUpDown` 控件指定 <xref:System.Windows.FrameworkElement> 对象和状态。

[!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
[!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]

<a name="complete_example"></a>

## <a name="complete-example"></a>完整的示例

下面的示例是 `NumericUpDown` 控件的整个 <xref:System.Windows.Controls.ControlTemplate>。

[!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]

下面的示例演示了 `NumericUpDown`的逻辑。

[!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
[!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]

## <a name="see-also"></a>另请参阅

- [为控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)
- [控件自定义](control-customization.md)
