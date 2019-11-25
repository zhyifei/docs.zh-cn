---
title: ListBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
ms.openlocfilehash: cb7043a21020193a4b2a2569ec610f311834a698
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283745"
---
# <a name="listbox-styles-and-templates"></a>ListBox 样式和模板
本主题介绍 <xref:System.Windows.Controls.ListBox> 控件的样式和模板。 您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。  
  
## <a name="listbox-parts"></a>ListBox 部件  
 <xref:System.Windows.Controls.ListBox> 控件没有任何命名部分。  
  
 为 <xref:System.Windows.Controls.ListBox>创建 <xref:System.Windows.Controls.ControlTemplate> 时，模板可能包含 <xref:System.Windows.Controls.ScrollViewer>中的 <xref:System.Windows.Controls.ItemsPresenter>。 （<xref:System.Windows.Controls.ItemsPresenter> 显示 <xref:System.Windows.Controls.ListBox>中的每一项; <xref:System.Windows.Controls.ScrollViewer> 允许在控件中滚动）。  如果 <xref:System.Windows.Controls.ItemsPresenter> 不是 <xref:System.Windows.Controls.ScrollViewer>的直接子级，则必须为 <xref:System.Windows.Controls.ItemsPresenter> 指定名称 `ItemsPresenter`。  
  
## <a name="listbox-states"></a>ListBox 状态  
 下表列出了 <xref:System.Windows.Controls.ListBox> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|有效|ValidationStates|控件有效。|  
|InvalidFocused|ValidationStates|控件无效，但具有焦点。|  
|InvalidUnfocused|ValidationStates|控件无效，并且没有焦点。|  
  
## <a name="listboxitem-parts"></a>ListBoxItem 部件  
 <xref:System.Windows.Controls.ListBoxItem> 控件没有任何命名部分。  
  
## <a name="listboxitem-states"></a>ListBoxItem 状态  
 下表列出了 <xref:System.Windows.Controls.ListBox> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|一般|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针悬停在控件上。|  
|Disabled|CommonStates|该项已禁用。|  
|已设定焦点|FocusStates|该项有焦点。|  
|失去焦点|FocusStates|该项没有焦点。|  
|未选定|SelectionStates|未选定该项。|  
|已选定|SelectionStates|该项当前已选定。|  
|SelectedUnfocused|SelectionStates|该项已选定，但没有焦点。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="listbox-controltemplate-example"></a>ListBox ControlTemplate 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.ListBoxItem> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#ListBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
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
