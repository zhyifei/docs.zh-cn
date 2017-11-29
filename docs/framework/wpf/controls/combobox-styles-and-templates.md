---
title: "ComboBox 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd89d2150b2623a749614ab01aa767997dc4bdf3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="combobox-styles-and-templates"></a>ComboBox 样式和模板
本主题介绍的样式和模板的<xref:System.Windows.Controls.ComboBox>控件。 你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。 有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
## <a name="combobox-parts"></a>组合框部件  
 下表列出的命名的部件<xref:System.Windows.Controls.ComboBox>控件。  
  
|部件|类型|描述|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|包含文本的<xref:System.Windows.Controls.ComboBox>。|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|下拉列表包含组合框中的项。|  
  
 当你创建<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ComboBox>，你的模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。 (<xref:System.Windows.Controls.ItemsPresenter>显示中的每一项<xref:System.Windows.Controls.ComboBox>;<xref:System.Windows.Controls.ScrollViewer>使控件内滚动)。  如果<xref:System.Windows.Controls.ItemsPresenter>不的直接子级<xref:System.Windows.Controls.ScrollViewer>，您必须为指定<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。  
  
## <a name="combobox-states"></a>组合框状态  
 下表列出的状态<xref:System.Windows.Controls.ComboBox>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|已禁用控件。|  
|MouseOver|CommonStates|鼠标指针位于<xref:System.Windows.Controls.ComboBox>控件。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
|FocusedDropDown|FocusStates|下拉列表<xref:System.Windows.Controls.ComboBox>具有焦点。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
|可编辑|EditStates|<xref:System.Windows.Controls.ComboBox.IsEditable%2A> 属性为 `true`。|  
|不可编辑状态|EditStates|<xref:System.Windows.Controls.ComboBox.IsEditable%2A> 属性为 `false`。|  
  
## <a name="comboboxitem-parts"></a>ComboBoxItem 部件  
 <xref:System.Windows.Controls.ComboBoxItem>控件不具有任何已命名的部件。  
  
## <a name="comboboxitem-states"></a>ComboBoxItem 状态  
 下表列出的状态<xref:System.Windows.Controls.ComboBoxItem>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|已禁用控件。|  
|MouseOver|CommonStates|鼠标指针位于<xref:System.Windows.Controls.ComboBox>控件。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
|已选定|SelectionStates|当前选择项。|  
|未选定|SelectionStates|未选定该项。|  
|SelectedUnfocused|SelectionStates|该项已选定，但没有焦点。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="combobox-controltemplate-example"></a>组合框的 ControlTemplate 示例  
 下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ComboBox>控件和关联的类型。  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
 上一示例使用了一个或多个以下资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [控件样式和模板](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [控件自定义](../../../../docs/framework/wpf/controls/control-customization.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
