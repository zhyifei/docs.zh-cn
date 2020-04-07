---
title: ToggleButton 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805921"
---
# <a name="togglebutton-styles-and-templates"></a>ToggleButton 样式和模板

本主题介绍控件的<xref:System.Windows.Controls.Primitives.ToggleButton>样式和模板。 您可以修改默认值<xref:System.Windows.Controls.ControlTemplate>，为控件提供唯一的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。

## <a name="togglebutton-parts"></a>切换按钮零件

该<xref:System.Windows.Controls.Primitives.ToggleButton>控件没有任何命名部件。

## <a name="togglebutton-states"></a>切换按钮状态

下表列出了控件的<xref:System.Windows.Controls.Primitives.ToggleButton>可视状态。

|VisualState 名称|VisualStateGroup 名称|说明|
|-|-|-|
|一般|CommonStates|默认状态。|
|MouseOver|CommonStates|鼠标指针悬停在控件上方。|
|已按下|CommonStates|已按下控件。|
|已禁用|CommonStates|已禁用控件。|
|已设定焦点|FocusStates|控件有焦点。|
|失去焦点|FocusStates|控件没有焦点。|
|已选中|检查状态|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。|
|未选中|检查状态|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。|
|定|检查状态|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> 为 `true` 且 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `null`。|
|有效|ValidationStates|控件使用 类<xref:System.Windows.Controls.Validation>，<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加属性为`false`。|
|InvalidFocused|ValidationStates|附加<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>属性是`true`，控件具有焦点。|
|InvalidUnfocused|ValidationStates|附加<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>属性为`true`，控件没有焦点。|

> [!NOTE]
> 如果控件模板中不存在不确定的可视状态，则"未选中的可视状态"将用作默认可视状态。

## <a name="togglebutton-controltemplate-example"></a>切换按钮控制模板示例

下面的示例演示如何为<xref:System.Windows.Controls.ControlTemplate><xref:System.Windows.Controls.Primitives.ToggleButton>控件定义 。

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

上一示例使用了一个或多个以下资源。

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Control 样式和模板](control-styles-and-templates.md)
- [控件自定义](control-customization.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [为控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)
