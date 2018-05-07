---
title: Calendar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: b706ec6236b7e3e10865eee9fd32c2eb5a5e7db2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="calendar"></a>Calendar
日历使用户能够通过使用可视月历显示来选择日期。  
  
 A<xref:System.Windows.Controls.Calendar>本身，或作为下拉列表的一部分，可以使用控件<xref:System.Windows.Controls.DatePicker>控件。 有关详细信息，请参阅<xref:System.Windows.Controls.DatePicker>。  
  
 下图显示了两个<xref:System.Windows.Controls.Calendar>控件，与中断日期，并选择一个，另一个没有。  
  
 ![月历控件](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP_CalendarControls")  
日历控件  
  
 下表提供了有关通常与相关联的任务的信息<xref:System.Windows.Controls.Calendar>。  
  
|任务|实现|  
|----------|--------------------|  
|指定日期，不能同时选择。|使用 <xref:System.Windows.Controls.Calendar.BlackoutDates%2A> 属性。|  
|具有<xref:System.Windows.Controls.Calendar>显示一个月、 整个年或十年。|设置<xref:System.Windows.Controls.Calendar.DisplayMode%2A>到月、 年或十年中的属性。|  
|指定用户是否可以选择一个日期、 的日期，范围或多个日期范围。|使用<xref:System.Windows.Controls.Calendar.SelectionMode%2A>。|  
|指定的日期范围的<xref:System.Windows.Controls.Calendar>显示。|使用<xref:System.Windows.Controls.Calendar.DisplayDateStart%2A>和<xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>属性。|  
|指定是否突出显示当前日期。|使用 <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> 属性。 默认情况下，<xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>是`true`。|  
|更改的大小<xref:System.Windows.Controls.Calendar>。|使用<xref:System.Windows.Controls.Viewbox>或设置<xref:System.Windows.FrameworkElement.LayoutTransform%2A>属性<xref:System.Windows.Media.ScaleTransform>。 请注意，如果你设置<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性<xref:System.Windows.Controls.Calendar>，则实际日历不会更改其大小。|  
  
 <xref:System.Windows.Controls.Calendar>控件提供使用鼠标或键盘的基本导航。 下表总结了键盘导航。  
  
|组合键|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|操作|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Month>|更改<xref:System.Windows.Controls.Calendar.SelectedDate%2A>属性如果<xref:System.Windows.Controls.Calendar.SelectionMode%2A>属性未设置为<xref:System.Windows.Controls.CalendarSelectionMode.None>。|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Year>|更改的月份<xref:System.Windows.Controls.Calendar.DisplayDate%2A>属性。 请注意，<xref:System.Windows.Controls.Calendar.SelectedDate%2A>不会更改。|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Decade>|更改的年份，该值<xref:System.Windows.Controls.Calendar.DisplayDate%2A>。 请注意，<xref:System.Windows.Controls.Calendar.SelectedDate%2A>不会更改。|  
|SHIFT + 箭头|<xref:System.Windows.Controls.CalendarMode.Month>|如果<xref:System.Windows.Controls.Calendar.SelectionMode%2A>未设置为<xref:System.Windows.Controls.CalendarSelectionMode.SingleDate>或<xref:System.Windows.Controls.CalendarSelectionMode.None>，扩展的所选日期范围。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Month>|更改<xref:System.Windows.Controls.Calendar.SelectedDate%2A>到当前月份的第一天。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Year>|更改的月份<xref:System.Windows.Controls.Calendar.DisplayDate%2A>年的第一个月。 <xref:System.Windows.Controls.Calendar.SelectedDate%2A>不会更改。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Decade>|更改的年份，该值<xref:System.Windows.Controls.Calendar.DisplayDate%2A>在十年的第一年。 <xref:System.Windows.Controls.Calendar.SelectedDate%2A>不会更改。|  
|End|<xref:System.Windows.Controls.CalendarMode.Month>|更改<xref:System.Windows.Controls.Calendar.SelectedDate%2A>与当前月份的最后一天。|  
|End|<xref:System.Windows.Controls.CalendarMode.Year>|更改的月份<xref:System.Windows.Controls.Calendar.DisplayDate%2A>年份的最后一个月。 <xref:System.Windows.Controls.Calendar.SelectedDate%2A>不会更改。|  
|End|<xref:System.Windows.Controls.CalendarMode.Decade>|更改的年份，该值<xref:System.Windows.Controls.Calendar.DisplayDate%2A>十年中的最后一年。 <xref:System.Windows.Controls.Calendar.SelectedDate%2A>不会更改。|  
|Ctrl+向上键|任意|切换到下一个更大<xref:System.Windows.Controls.Calendar.DisplayMode%2A>。 如果<xref:System.Windows.Controls.Calendar.DisplayMode%2A>已<xref:System.Windows.Controls.CalendarMode.Decade>，任何操作。|  
|Ctrl+向下键|任意|切换到下一个较小<xref:System.Windows.Controls.Calendar.DisplayMode%2A>。 如果<xref:System.Windows.Controls.Calendar.DisplayMode%2A>已<xref:System.Windows.Controls.CalendarMode.Month>，任何操作。|  
|空格键或 enter 键|<xref:System.Windows.Controls.CalendarMode.Year> 或 <xref:System.Windows.Controls.CalendarMode.Decade>|交换机<xref:System.Windows.Controls.Calendar.DisplayMode%2A>到<xref:System.Windows.Controls.CalendarMode.Month>或<xref:System.Windows.Controls.CalendarMode.Year>由已设定焦点的项表示。|  
  
## <a name="see-also"></a>请参阅  
 [控件](../../../../docs/framework/wpf/controls/index.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)
