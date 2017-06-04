---
title: "DatePicker 样式和模板 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ControlTemplate [WPF], DatePicker"
  - "DatePicker [WPF], 样式和模板"
  - "部件 [WPF], DatePicker"
  - "状态 [WPF], DatePicker"
  - "样式 [WPF], DatePicker"
  - "模板 [WPF], DatePicker"
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# DatePicker 样式和模板
本主题介绍 <xref:System.Windows.Controls.DatePicker> 控件的样式和模板。  您可以修改默认的 <xref:System.Windows.Controls.ControlTemplate>，以便为控件提供一个独特的外观。  有关更多信息，请参见[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
## DatePicker 部件  
 下表列出了 <xref:System.Windows.Controls.DatePicker> 控件的命名部件。  
  
||||  
|-|-|-|  
|组成部分|类型|说明|  
|PART\_Root|<xref:System.Windows.Controls.Grid>|控件的根。|  
|PART\_Button|<xref:System.Windows.Controls.Button>|用于打开和关闭 <xref:System.Windows.Controls.Calendar> 的按钮。|  
|PART\_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|可以输入日期的文本框。|  
|PART\_Popup|<xref:System.Windows.Controls.Primitives.Popup>|<xref:System.Windows.Controls.DatePicker> 控件的弹出窗口。|  
  
## DatePicker 状态  
 下表列出了 <xref:System.Windows.Controls.DatePicker> 控件的可视状态。  
  
||||  
|-|-|-|  
|VisualState 名称|VisualStateGroup 名称|说明|  
|Normal|CommonStates|默认状态。|  
|禁用|CommonStates|<xref:System.Windows.Controls.DatePicker> 已禁用。|  
|Valid|ValidationStates|该控件使用 <xref:System.Windows.Controls.Validation> 类，<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> 附加属性为 `false`。|  
|InvalidFocused|ValidationStates|当 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> 附加属性为 `true` 时，控件具有焦点。|  
|InvalidUnfocused|ValidationStates|当 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> 附加属性为 `true` 时，控件没有焦点。|  
  
## DatePickerTextBox 部件  
 下表列出了 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 控件的命名部件。  
  
||||  
|-|-|-|  
|组成部分|类型|说明|  
|PART\_Watermark|<xref:System.Windows.Controls.ContentControl>|包含 <xref:System.Windows.Controls.DatePicker> 中的初始文本的元素。|  
|PART\_ContentElement|<xref:System.Windows.FrameworkElement>|可以包含 <xref:System.Windows.FrameworkElement> 的可见元素。  在此元素中显示 <xref:System.Windows.Controls.TextBox> 的文本。|  
  
## DatePickerTextBox 状态  
 下表列出了 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 控件的可视状态。  
  
||||  
|-|-|-|  
|VisualState 名称|VisualStateGroup 名称|说明|  
|Normal|CommonStates|默认状态。|  
|禁用|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox> 已禁用。|  
|MouseOver|CommonStates|鼠标指针置于 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 上。|  
|ReadOnly|CommonStates|用户不能更改 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 中的文本。|  
|Focused|FocusStates|控件具有焦点。|  
|Unfocused|FocusStates|控件不具有焦点。|  
|Watermarked|WatermarkStates|控件显示其初始文本。  <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 处于用户尚未输入文本或选择日期时的状态。|  
|Unwatermarked|WatermarkStates|用户已向 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 输入了文本或在 <xref:System.Windows.Controls.DatePicker> 中选择了日期。|  
|Valid|ValidationStates|该控件使用 <xref:System.Windows.Controls.Validation> 类，<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> 附加属性为 `false`。|  
|InvalidFocused|ValidationStates|当 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> 附加属性为 `true` 时，控件具有焦点。|  
|InvalidUnfocused|ValidationStates|当 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> 附加属性为 `true` 时，控件没有焦点。|  
  
## DatePicker ControlTemplate 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.DatePicker> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
 上面的示例使用下面的一个或多个资源。  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参见         [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)（使用 ControlTemplates 设置样式的示例）.  
  
## 请参阅  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Control 样式和模板](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [控件自定义](../../../../docs/framework/wpf/controls/control-customization.md)   
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)