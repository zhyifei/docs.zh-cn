---
title: Calendar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
ms.openlocfilehash: 64cb62a3459a3eeea6aa5e91b433a58a88ab08ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283558"
---
# <a name="calendar-styles-and-templates"></a>Calendar 样式和模板
本主题介绍 <xref:System.Windows.Controls.Calendar> 控件的样式和模板。 您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。 有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。  
  
## <a name="calendar-parts"></a>日历部件  
 下表列出了 <xref:System.Windows.Controls.Calendar> 控件的已命名部分。  
  
|部件|Type|描述|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|<xref:System.Windows.Controls.Calendar>上当前显示的月份或年份。|  
|PART_Root|<xref:System.Windows.Controls.Panel>|包含 <xref:System.Windows.Controls.Primitives.CalendarItem>的面板。|  
  
## <a name="calendar-states"></a>日历状态  
 下表列出了 <xref:System.Windows.Controls.Calendar> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|----------------------|---------------------------|-----------------|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="calendaritem-parts"></a>CalendarItem 部件  
 下表列出了 <xref:System.Windows.Controls.Primitives.CalendarItem> 控件的已命名部分。  
  
|部件|Type|描述|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|控件的根。|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|单击此按钮将显示日历的上一页。|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|用于显示单击日历下一页的按钮。|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|用于在月模式、年份模式和十年模式间切换的按钮。|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|按月模式托管内容。|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|在年或十年模式下托管内容。|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|处于禁用状态的覆盖区。|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|描述视觉对象结构的 <xref:System.Windows.DataTemplate>。|  
  
## <a name="calendaritem-states"></a>CalendarItem 状态  
 下表列出了 <xref:System.Windows.Controls.Primitives.CalendarItem> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|正常状态|CommonStates|默认状态。|  
|禁用状态|CommonStates|`false`<xref:System.Windows.UIElement.IsEnabled%2A> 属性时日历的状态。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="calendardaybutton-parts"></a>CalendarDayButton 部件  
 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 控件没有任何命名部分。  
  
## <a name="calendardaybutton-states"></a>CalendarDayButton 状态  
 下表列出了 <xref:System.Windows.Controls.Primitives.CalendarDayButton> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|一般|CommonStates|默认状态。|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton> 处于禁用状态。|  
|MouseOver|CommonStates|鼠标指针置于 <xref:System.Windows.Controls.Primitives.CalendarDayButton>上。|  
|已按下|CommonStates|已按下 <xref:System.Windows.Controls.Primitives.CalendarDayButton>。|  
|已选定|SelectionStates|该按钮处于选中状态。|  
|未选定|SelectionStates|未选择该按钮。|  
|CalendarButtonFocused|CalendarButtonFocusStates|按钮有焦点。|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|按钮没有焦点。|  
|已设定焦点|FocusStates|按钮有焦点。|  
|失去焦点|FocusStates|按钮没有焦点。|  
|活动的|ActiveStates|该按钮处于活动状态。|  
|非活动|ActiveStates|该按钮处于非活动状态。|  
|RegularDay|DayStates|此按钮不表示 <xref:System.DateTime.Today%2A?displayProperty=nameWithType>。|  
|今天|DayStates|按钮表示 <xref:System.DateTime.Today%2A?displayProperty=nameWithType>。|  
|NormalDay|BlackoutDayStates|按钮表示可选择的日期。|  
|BlackoutDay|BlackoutDayStates|此按钮表示不能选择的日期。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="calendarbutton-parts"></a>CalendarButton 部件  
 <xref:System.Windows.Controls.Primitives.CalendarButton> 控件没有任何命名部分。  
  
## <a name="calendarbutton-states"></a>CalendarButton 状态  
 下表列出了 <xref:System.Windows.Controls.Primitives.CalendarButton> 控件的可视状态。  
  
|VisualState 名称|VisualStateGroup 名称|描述|  
|-|-|-|  
|一般|CommonStates|默认状态。|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarButton> 处于禁用状态。|  
|MouseOver|CommonStates|鼠标指针置于 <xref:System.Windows.Controls.Primitives.CalendarButton>上。|  
|已按下|CommonStates|已按下 <xref:System.Windows.Controls.Primitives.CalendarButton>。|  
|已选定|SelectionStates|该按钮处于选中状态。|  
|未选定|SelectionStates|未选择该按钮。|  
|CalendarButtonFocused|CalendarButtonFocusStates|按钮有焦点。|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|按钮没有焦点。|  
|已设定焦点|FocusStates|按钮有焦点。|  
|失去焦点|FocusStates|按钮没有焦点。|  
|活动的|ActiveStates|该按钮处于活动状态。|  
|非活动|ActiveStates|该按钮处于非活动状态。|  
|有效|ValidationStates|控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。|  
  
## <a name="calendar-controltemplate-example"></a>Calendar System.windows.controls.controltemplate> 示例  
 下面的示例演示如何为 <xref:System.Windows.Controls.Calendar> 控件和关联类型定义 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
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
