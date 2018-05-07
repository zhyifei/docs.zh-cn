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
ms.openlocfilehash: 3a73127e409a96d5282272bd7a0e55a13a83a849
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="treeview-styles-and-templates"></a>TreeView 样式和模板
本主题介绍的样式和模板的<xref:System.Windows.Controls.TreeView>控件。 你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。 有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
## <a name="treeview-parts"></a>TreeView 部件  
 <xref:System.Windows.Controls.TreeView>控件不具有任何已命名的部件。  
  
 当你创建<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.TreeView>，你的模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。 (<xref:System.Windows.Controls.ItemsPresenter>显示中的每一项<xref:System.Windows.Controls.TreeView>;<xref:System.Windows.Controls.ScrollViewer>使控件内滚动)。  如果<xref:System.Windows.Controls.ItemsPresenter>不的直接子级<xref:System.Windows.Controls.ScrollViewer>，您必须为指定<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。  
  
## <a name="treeview-states"></a>树视图状态  
 下表列出的可视状态<xref:System.Windows.Controls.TreeView>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem 部件  
 下表列出的命名的部件<xref:System.Windows.Controls.TreeViewItem>控件。  
  
|部件|类型|描述|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|包含该标头内容的可视元素<xref:System.Windows.Controls.TreeView>控件。|  
  
## <a name="treeviewitem-states"></a>TreeViewItem 状态  
 下表列出的可视状态<xref:System.Windows.Controls.TreeViewItem>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|普通|CommonStates|默认状态。|  
|MouseOver|CommonStates|鼠标指针置于<xref:System.Windows.Controls.TreeViewItem>。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.TreeViewItem>处于禁用状态。|  
|已设定焦点|FocusStates|<xref:System.Windows.Controls.TreeViewItem>具有焦点。|  
|失去焦点|FocusStates|<xref:System.Windows.Controls.TreeViewItem>不具有焦点。|  
|已展开|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem>控件已展开。|  
|Collapsed|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem>控件处于折叠状态。|  
|HasItems|HasItemsStates|<xref:System.Windows.Controls.TreeViewItem>具有的项。|  
|NoItems|HasItemsStates|<xref:System.Windows.Controls.TreeViewItem>没有项。|  
|已选定|SelectionStates|<xref:System.Windows.Controls.TreeViewItem>选择。|  
|SelectedInactive|SelectionStates|<xref:System.Windows.Controls.TreeViewItem>选但未处于活动状态。|  
|未选定|SelectionStates|<xref:System.Windows.Controls.TreeViewItem>未选中。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="treeview-controltemplate-example"></a>TreeView ControlTemplate 示例  
 下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.TreeView>控件和其关联的类型。  
  
 [!code-xaml[ControlTemplateExamples#TreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
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
