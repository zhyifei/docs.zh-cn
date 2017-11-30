---
title: "Calendar 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b27049c63faa9bf84dc5febd210a29a530f175a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="calendar-styles-and-templates"></a>Calendar 样式和模板
本主题介绍的样式和模板的<xref:System.Windows.Controls.Calendar>控件。 你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。 有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。  
  
## <a name="calendar-parts"></a>日历部件  
 下表列出的命名的部件<xref:System.Windows.Controls.Calendar>控件。  
  
|部件|类型|描述|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|当前显示的月或年<xref:System.Windows.Controls.Calendar>。|  
|PART_Root|<xref:System.Windows.Controls.Panel>|包含的面板<xref:System.Windows.Controls.Primitives.CalendarItem>。|  
  
## <a name="calendar-states"></a>日历状态  
 下表列出的可视状态<xref:System.Windows.Controls.Calendar>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="calendaritem-parts"></a>日历项目部分  
 下表列出的命名的部件<xref:System.Windows.Controls.Primitives.CalendarItem>控件。  
  
|部件|类型|描述|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|控件的根。|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|该按钮将显示日历的前一页，单击时其。|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|该按钮将显示日历的下一页上，单击时其。|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|允许月模式、 年模式和十年模式之间切换按钮。|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|承载在月模式下的内容。|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|承载在年份或十年中的模式下的内容。|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|在覆盖区上的已禁用状态。|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|<xref:System.Windows.DataTemplate>描述可视结构。|  
  
## <a name="calendaritem-states"></a>日历项目状态  
 下表列出的可视状态<xref:System.Windows.Controls.Primitives.CalendarItem>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|正常状态|CommonStates|默认状态。|  
|已禁用状态|CommonStates|日历的状态时<xref:System.Windows.UIElement.IsEnabled%2A>属性是`false`。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="calendardaybutton-parts"></a>CalendarDayButton 部件  
 <xref:System.Windows.Controls.Primitives.CalendarDayButton>控件不具有任何已命名的部件。  
  
## <a name="calendardaybutton-states"></a>CalendarDayButton 状态  
 下表列出的可视状态<xref:System.Windows.Controls.Primitives.CalendarDayButton>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>处于禁用状态。|  
|MouseOver|CommonStates|鼠标指针置于<xref:System.Windows.Controls.Primitives.CalendarDayButton>。|  
|已按下|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton>按下。|  
|已选定|SelectionStates|按钮处于选中状态。|  
|未选定|SelectionStates|未选择按钮。|  
|CalendarButtonFocused|CalendarButtonFocusStates|按钮有焦点。|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|按钮有焦点。|  
|已设定焦点|FocusStates|按钮有焦点。|  
|失去焦点|FocusStates|按钮有焦点。|  
|活动|ActiveStates|按钮处于活动状态。|  
|非活动状态|ActiveStates|按钮处于非活动状态。|  
|RegularDay|DayStates|按钮不表示<xref:System.DateTime.Today%2A?displayProperty=nameWithType>。|  
|今天|DayStates|此按钮表示<xref:System.DateTime.Today%2A?displayProperty=nameWithType>。|  
|NormalDay|BlackoutDayStates|此按钮表示可以选择一天。|  
|BlackoutDay|BlackoutDayStates|此按钮表示不能选择一天。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="calendarbutton-parts"></a>CalendarButton 部件  
 <xref:System.Windows.Controls.Primitives.CalendarButton>控件不具有任何已命名的部件。  
  
## <a name="calendarbutton-states"></a>CalendarButton 状态  
 下表列出的可视状态<xref:System.Windows.Controls.Primitives.CalendarButton>控件。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|普通|CommonStates|默认状态。|  
|已禁用|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>处于禁用状态。|  
|MouseOver|CommonStates|鼠标指针置于<xref:System.Windows.Controls.Primitives.CalendarButton>。|  
|已按下|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton>按下。|  
|已选定|SelectionStates|按钮处于选中状态。|  
|未选定|SelectionStates|未选择按钮。|  
|CalendarButtonFocused|CalendarButtonFocusStates|按钮有焦点。|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|按钮有焦点。|  
|已设定焦点|FocusStates|按钮有焦点。|  
|失去焦点|FocusStates|按钮有焦点。|  
|活动|ActiveStates|按钮处于活动状态。|  
|非活动状态|ActiveStates|按钮处于非活动状态。|  
|有效|ValidationStates|该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。|  
  
## <a name="calendar-controltemplate-example"></a>日历 ControlTemplate 示例  
 下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Calendar>控件和关联的类型。  
  
 [!code-xaml[ControlTemplateExamples#Calendar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
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
