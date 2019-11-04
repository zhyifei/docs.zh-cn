---
title: TreeView 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
ms.openlocfilehash: f6dbe54324a5ad5e2f85719d819c035abfd644b1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460183"
---
# <a name="treeview-styles-and-templates"></a>TreeView 样式和模板
本主题介绍 <xref:System.Windows.Controls.TreeView> 控件的样式和模板。 您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。 有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。  
  
## <a name="treeview-parts"></a>TreeView 部件  
 <xref:System.Windows.Controls.TreeView> 控件没有任何命名部分。  
  
 为 <xref:System.Windows.Controls.TreeView>创建 <xref:System.Windows.Controls.ControlTemplate> 时，模板可能包含 <xref:System.Windows.Controls.ScrollViewer>中的 <xref:System.Windows.Controls.ItemsPresenter>。 （<xref:System.Windows.Controls.ItemsPresenter> 显示 <xref:System.Windows.Controls.TreeView>中的每一项; <xref:System.Windows.Controls.ScrollViewer> 允许在控件中滚动）。  如果 <xref:System.Windows.Controls.ItemsPresenter> 不是 <xref:System.Windows.Controls.ScrollViewer>的直接子级，则必须为 <xref:System.Windows.Controls.ItemsPresenter> 指定名称 `ItemsPresenter`。  
  
## <a name="treeview-states"></a>TreeView 状态  
 下表列出了 <xref:System.Windows.Controls.TreeView> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem 部件  
 下表列出了 <xref:System.Windows.Controls.TreeViewItem> 控件的已命名部分。  
  
|部件|键入|描述|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|一个包含 <xref:System.Windows.Controls.TreeView> 控件标题内容的视觉元素。|  
  
## <a name="treeviewitem-states"></a>TreeViewItem 状态  
 下表列出了 <xref:System.Windows.Controls.TreeViewItem> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|普通|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针置于 <xref:System.Windows.Controls.TreeViewItem>上。|  
|Disabled|CommonStates|<xref:System.Windows.Controls.TreeViewItem> 处于禁用状态。|  
|已设定焦点|FocusStates|<xref:System.Windows.Controls.TreeViewItem> 具有焦点。|  
|失去焦点|FocusStates|<xref:System.Windows.Controls.TreeViewItem> 没有焦点。|  
|展开|ExpansionStates|展开 <xref:System.Windows.Controls.TreeViewItem> 控件。|  
|Collapsed|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem> 控件已折叠。|  
|HasItems|HasItemsStates|<xref:System.Windows.Controls.TreeViewItem> 具有项。|  
|NoItems|HasItemsStates|<xref:System.Windows.Controls.TreeViewItem> 没有项。|  
|已选定|SelectionStates|选择 <xref:System.Windows.Controls.TreeViewItem>。|  
|SelectedInactive|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 处于选中状态，但不处于活动状态。|  
|未选定|SelectionStates|未选择 <xref:System.Windows.Controls.TreeViewItem>。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="treeview-controltemplate-example"></a>TreeView System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.TreeView> 控件及其关联的类型定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 上一示例使用了一个或多个以下资源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [控件样式和模板](control-styles-and-templates.md)
- [控件自定义](control-customization.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)
