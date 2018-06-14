---
title: MonthCalendar 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: 7ed917afe2640fe2ffef4904a3795c5f0e84ded9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537403"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>MonthCalendar 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.MonthCalendar>控件显示直观的图形界面，供用户查看并设置日期信息。 该控件将显示一个日历： 包含排列在列下方的日期突出显示所选的范围内一周中的天的月份的编号的日期的网格。 你可以通过单击箭头按钮在月标题的任意一侧选择不同的月份。 与类似<xref:System.Windows.Forms.DateTimePicker>控件，您可以选择与此控件的多个日期。 有关详细信息<xref:System.Windows.Forms.DateTimePicker>控制，请参阅[DateTimePicker 控件](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)。  
  
## <a name="configuring-the-monthcalendar-control"></a>配置 MonthCalendar 控件  
 <xref:System.Windows.Forms.MonthCalendar>控件的外观会高度可配置。 默认情况下，今天的日期显示为圆形，并且还显示在网格底部。 你可以通过设置来更改此功能<xref:System.Windows.Forms.MonthCalendar.ShowToday%2A>和<xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A>属性设置为`false`。 你还可以将周数通过设置添加到日历<xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A>属性`true`。 通过设置<xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>属性，可以有多个显示水平和垂直月份。 默认情况下，星期日显示为每周的第一天，但可以使用指定任何一天<xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A>属性。  
  
 你还可以设置要在中显示的特定日期上一次性地，每年或每月，以粗体显示通过添加<xref:System.DateTime>对象添加到<xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>， <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>，和<xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>属性。 有关详细信息，请参阅[如何： 显示特定日期中使用 Windows 窗体 MonthCalendar 控件加粗](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)。  
  
 键属性的<xref:System.Windows.Forms.MonthCalendar>控件是<xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>，选择控件中的日期范围。 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>值不能超过最大天数，可以选择，在中设置<xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A>属性。 用户可以选择的最早时间和最新日期由<xref:System.Windows.Forms.MonthCalendar.MaxDate%2A>和<xref:System.Windows.Forms.MonthCalendar.MinDate%2A>属性。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.MonthCalendar>  
 [MonthCalendar 控件](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
