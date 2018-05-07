---
title: 包含 DatePicker 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: 5123cf0ef78d46f5cec30109a34c17eaabe13b38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="datepicker-styles-and-templates"></a>包含 DatePicker 样式和模板
本主题介绍的样式和模板的<xref:System.Windows.Controls.DatePicker>控件。 你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。 有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
## <a name="datepicker-parts"></a>包含 DatePicker 部件  
 下表列出的命名的部件<xref:System.Windows.Controls.DatePicker>控件。  
  
|部件|类型|描述|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|控件的根。|  
|PART_Button|<xref:System.Windows.Controls.Button>|打开和关闭按钮<xref:System.Windows.Controls.Calendar>。|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|文本框中，您可以输入日期。|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|弹出窗口<xref:System.Windows.Controls.DatePicker>控件。|  
  
## <a name="datepicker-states"></a>包含 DatePicker 状态  
 下表列出的可视状态<xref:System.Windows.Controls.DatePicker>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.DatePicker>处于禁用状态。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="datepickertextbox-parts"></a>DatePickerTextBox 部件  
 下表列出的命名的部件<xref:System.Windows.Controls.Primitives.DatePickerTextBox>控件。  
  
|部件|类型|描述|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|包含中的初始文本的元素<xref:System.Windows.Controls.DatePicker>。|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|可以包含一个可见元素<xref:System.Windows.FrameworkElement>。 文本<xref:System.Windows.Controls.TextBox>显示在此元素。|  
  
## <a name="datepickertextbox-states"></a>DatePickerTextBox 状态  
 下表列出的可视状态<xref:System.Windows.Controls.Primitives.DatePickerTextBox>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>处于禁用状态。|  
|MouseOver|CommonStates|鼠标指针置于<xref:System.Windows.Controls.Primitives.DatePickerTextBox>。|  
|ReadOnly|CommonStates|用户不能更改中的文本<xref:System.Windows.Controls.Primitives.DatePickerTextBox>。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
|打水印|WatermarkStates|该控件将显示其初始文本。  <xref:System.Windows.Controls.Primitives.DatePickerTextBox>处于状态，当用户不具有输入文本或选择日期。|  
|Unwatermarked|WatermarkStates|用户输入到文本<xref:System.Windows.Controls.Primitives.DatePickerTextBox>或中选择了日期<xref:System.Windows.Controls.DatePicker>。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="datepicker-controltemplate-example"></a>包含 DatePicker ControlTemplate 示例  
 下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.DatePicker>控件。  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
 上一示例使用了一个或多个以下资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [控件样式和模板](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [控件自定义](../../../../docs/framework/wpf/controls/control-customization.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
