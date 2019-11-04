---
title: Calendar
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: e99a716e7ca8f7b2c9ed11543f37e0b8cb7422a6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460812"
---
# <a name="calendar"></a>Calendar
使用日历，用户可以使用可视日历显示来选择日期。  
  
 <xref:System.Windows.Controls.Calendar> 控件可单独使用，也可作为 <xref:System.Windows.Controls.DatePicker> 控件的下拉部分使用。 有关更多信息，请参见<xref:System.Windows.Controls.DatePicker>。  
  
 下图显示了两个 <xref:System.Windows.Controls.Calendar> 控件，一个具有选择和中断日期，另一个不包含。  
  
 ![日历控件](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
日历控件  
  
 下表提供了有关通常与 <xref:System.Windows.Controls.Calendar>相关联的任务的信息。  
  
|任务|实现|  
|----------|--------------------|  
|指定不能选择的日期。|使用 <xref:System.Windows.Controls.Calendar.BlackoutDates%2A> 属性。|  
|让 <xref:System.Windows.Controls.Calendar> 显示月、整年或十年。|将 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 属性设置为月份、年份或十年。|  
|指定用户是否可以选择日期、日期范围或多个日期范围。|使用 <xref:System.Windows.Controls.Calendar.SelectionMode%2A>。|  
|指定 <xref:System.Windows.Controls.Calendar> 显示的日期范围。|使用 "<xref:System.Windows.Controls.Calendar.DisplayDateStart%2A>" 和 "<xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A>" 属性。|  
|指定是否突出显示当前日期。|使用 <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> 属性。 默认情况下，<xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> `true`。|  
|更改 <xref:System.Windows.Controls.Calendar>的大小。|使用 <xref:System.Windows.Controls.Viewbox> 或将 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 属性设置为 <xref:System.Windows.Media.ScaleTransform>。 请注意，如果您设置了 <xref:System.Windows.Controls.Calendar>的 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 属性，则实际日历不会更改其大小。|  
  
 <xref:System.Windows.Controls.Calendar> 控件使用鼠标或键盘提供基本导航。 下表总结了键盘导航。  
  
|组合键|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|操作|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Month>|如果 <xref:System.Windows.Controls.Calendar.SelectionMode%2A> 属性未设置为 <xref:System.Windows.Controls.CalendarSelectionMode.None>，则更改 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 属性。|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Year>|更改 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 属性的月份。 请注意，<xref:System.Windows.Controls.Calendar.SelectedDate%2A> 不会发生更改。|  
|箭头|<xref:System.Windows.Controls.CalendarMode.Decade>|更改 <xref:System.Windows.Controls.Calendar.DisplayDate%2A>的年份。 请注意，<xref:System.Windows.Controls.Calendar.SelectedDate%2A> 不会发生更改。|  
|SHIFT + 箭头|<xref:System.Windows.Controls.CalendarMode.Month>|如果 <xref:System.Windows.Controls.Calendar.SelectionMode%2A> 未设置为 <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> 或 <xref:System.Windows.Controls.CalendarSelectionMode.None>，将扩展选定日期的范围。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Month>|将 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 更改为当月的第一天。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Year>|将 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 的月份更改为一年中的第一个月。 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 不会更改。|  
|Home|<xref:System.Windows.Controls.CalendarMode.Decade>|将 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 的年份更改为十年的第一年。 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 不会更改。|  
|End|<xref:System.Windows.Controls.CalendarMode.Month>|将 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 更改为当月的最后一天。|  
|End|<xref:System.Windows.Controls.CalendarMode.Year>|将 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 中的月份更改为一年中的最后一个月。 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 不会更改。|  
|End|<xref:System.Windows.Controls.CalendarMode.Decade>|将 <xref:System.Windows.Controls.Calendar.DisplayDate%2A> 的年份更改为十年的最后一年。 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 不会更改。|  
|Ctrl+向上键|任意|切换到下一个更大的 <xref:System.Windows.Controls.Calendar.DisplayMode%2A>。 如果 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 已 <xref:System.Windows.Controls.CalendarMode.Decade>，则不执行任何操作。|  
|Ctrl+向下键|任意|切换到下一个较小的 <xref:System.Windows.Controls.Calendar.DisplayMode%2A>。 如果 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 已 <xref:System.Windows.Controls.CalendarMode.Month>，则不执行任何操作。|  
|空格键或 ENTER|<xref:System.Windows.Controls.CalendarMode.Year> 或 <xref:System.Windows.Controls.CalendarMode.Decade>|将 <xref:System.Windows.Controls.Calendar.DisplayMode%2A> 切换到焦点项表示的 <xref:System.Windows.Controls.CalendarMode.Month> 或 <xref:System.Windows.Controls.CalendarMode.Year>。|  
  
## <a name="see-also"></a>请参阅

- [控件](index.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
