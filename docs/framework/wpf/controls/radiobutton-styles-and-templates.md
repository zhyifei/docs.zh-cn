---
title: RadioButton 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: 2d732dc6620cd06c99bdbaedfa5be474477d4917
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283438"
---
# <a name="radiobutton-styles-and-templates"></a>RadioButton 样式和模板
本主题介绍 <xref:System.Windows.Controls.RadioButton> 控件的样式和模板。 您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。  
  
## <a name="radiobutton-parts"></a>单选按钮部件  
 <xref:System.Windows.Controls.RadioButton> 控件没有任何命名部分。  
  
## <a name="radiobutton-states"></a>单选按钮状态  
 下表列出了 <xref:System.Windows.Controls.RadioButton> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|一般|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针悬停在控件上。|  
|已按下|CommonStates|已按下控件。|  
|Disabled|CommonStates|已禁用控件。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
|已选中|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `true`。|  
|无|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 为 `false`。|  
|尚|CheckStates|`true`<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>，<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> `null`。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="radiobutton-controltemplate-example"></a>单选按钮 System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.RadioButton> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 上一示例使用了一个或多个以下资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [控件样式和模板](control-styles-and-templates.md)
- [控件自定义](control-customization.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [为控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)
