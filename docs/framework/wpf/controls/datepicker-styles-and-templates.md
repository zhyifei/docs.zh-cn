---
title: DatePicker 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: 002d1c3271827239dcd3a319621f66fb5bc68d4e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283775"
---
# <a name="datepicker-styles-and-templates"></a>DatePicker 样式和模板
本主题介绍 <xref:System.Windows.Controls.DatePicker> 控件的样式和模板。 您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。  
  
## <a name="datepicker-parts"></a>DatePicker 部件  
 下表列出了 <xref:System.Windows.Controls.DatePicker> 控件的已命名部分。  
  
|部件|类型|说明|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|控件的根。|  
|PART_Button|<xref:System.Windows.Controls.Button>|用于打开和关闭 <xref:System.Windows.Controls.Calendar>的按钮。|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|允许您输入日期的文本框。|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|<xref:System.Windows.Controls.DatePicker> 控件的弹出窗口。|  
  
## <a name="datepicker-states"></a>DatePicker 状态  
 下表列出了 <xref:System.Windows.Controls.DatePicker> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|说明|  
|-|-|-|  
|正常|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.DatePicker> 处于禁用状态。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="datepickertextbox-parts"></a>DatePickerTextBox 部件  
 下表列出了 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 控件的已命名部分。  
  
|部件|类型|说明|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|包含 <xref:System.Windows.Controls.DatePicker>中的初始文本的元素。|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|可包含 <xref:System.Windows.FrameworkElement>的可视元素。 <xref:System.Windows.Controls.TextBox> 的文本显示在此元素中。|  
  
## <a name="datepickertextbox-states"></a>DatePickerTextBox 状态  
 下表列出了 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|说明|  
|-|-|-|  
|正常|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox> 处于禁用状态。|  
|MouseOver|CommonStates|鼠标指针置于 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>上。|  
|ReadOnly|CommonStates|用户无法更改 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>中的文本。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
|打水印|WatermarkStates|控件显示其初始文本。  当用户未输入文本或选择日期时，<xref:System.Windows.Controls.Primitives.DatePickerTextBox> 处于状态。|  
|Unwatermarked|WatermarkStates|用户已将文本输入到 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 或在 <xref:System.Windows.Controls.DatePicker>中选择了日期。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 并且控件具有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 的，该控件没有焦点。|  
  
## <a name="datepicker-controltemplate-example"></a>DatePicker System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.DatePicker> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
