---
title: TabControl 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TabControl
- TabControl [WPF], styles and templates [WPF]
- parts [WPF], TabControl
- styles [WPF], TabControl
- states [WPF], TabControl
- templates [WPF], TabControl
ms.assetid: f6b19a30-f10e-4fa1-96ce-f17a54092ab6
ms.openlocfilehash: c1410714660eb1dd867428b85a7cfacc881e5e56
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283707"
---
# <a name="tabcontrol-styles-and-templates"></a>TabControl 样式和模板
本主题介绍 <xref:System.Windows.Controls.TabControl> 控件的样式和模板。 您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。  
  
## <a name="tabcontrol-parts"></a>TabControl 部件  
 下表列出了 <xref:System.Windows.Controls.TabControl> 控件的已命名部分。  
  
|部件|Type|描述|  
|-|-|-|  
|PART_SelectedContentHost|<xref:System.Windows.Controls.ContentPresenter>|显示当前所选 <xref:System.Windows.Controls.TabItem>的内容的对象。|  
  
 为 <xref:System.Windows.Controls.TabControl>创建 <xref:System.Windows.Controls.ControlTemplate> 时，模板可能包含 <xref:System.Windows.Controls.ScrollViewer>中的 <xref:System.Windows.Controls.ItemsPresenter>。 （<xref:System.Windows.Controls.ItemsPresenter> 显示 <xref:System.Windows.Controls.TabControl>中的每一项; <xref:System.Windows.Controls.ScrollViewer> 允许在控件中滚动）。  如果 <xref:System.Windows.Controls.ItemsPresenter> 不是 <xref:System.Windows.Controls.ScrollViewer>的直接子级，则必须为 <xref:System.Windows.Controls.ItemsPresenter> 指定名称 `ItemsPresenter`。  
  
## <a name="tabcontrol-states"></a>TabControl 状态  
 下表列出了 <xref:System.Windows.Controls.TabControl> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|一般|CommonStates|默认状态。|  
|Disabled|CommonStates|已禁用控件。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="tabitem-parts"></a>TabItem 部件  
 <xref:System.Windows.Controls.TabItem> 控件没有任何命名部分。  
  
## <a name="tabitem-states"></a>TabItem 状态  
 下表列出了 <xref:System.Windows.Controls.TabItem> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|一般|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针悬停在控件上。|  
|Disabled|CommonStates|已禁用控件。|  
|已设定焦点|FocusStates|控件有焦点。|  
|失去焦点|FocusStates|控件没有焦点。|  
|已选定|SelectionStates|已选择控件。|  
|未选定|SelectionStates|未选择控件。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="tabcontrol-controltemplate-example"></a>TabControl System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.TabControl> 和 <xref:System.Windows.Controls.TabItem> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#TabControl](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tabcontrol.xaml#tabcontrol)]  
  
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
