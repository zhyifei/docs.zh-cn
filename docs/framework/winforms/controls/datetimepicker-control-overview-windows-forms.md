---
title: "DateTimePicker 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a97eecc43614c84867e9dbdd527dbebd7dfd426e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="datetimepicker-control-overview-windows-forms"></a>DateTimePicker 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.DateTimePicker>控件允许用户从日期或时间的列表中选择单个项。 当用于表示的日期，它将显示在两个部分： 文本，并单击列表旁的向下箭头时出现的网格中所表示日期的下拉列表。 网格如下所示<xref:System.Windows.Forms.MonthCalendar>控件，可用于选择多个日期。 有关详细信息<xref:System.Windows.Forms.MonthCalendar>控制，请参阅[MonthCalendar 控件概述](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md)。  
  
## <a name="key-properties"></a>键属性  
 如果你想<xref:System.Windows.Forms.DateTimePicker>若要显示为选取或编辑而不是日期时间的控件，将设置<xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A>属性`true`和<xref:System.Windows.Forms.DateTimePicker.Format%2A>属性<xref:System.Windows.Forms.DateTimePickerFormat.Time>。 有关详细信息请参阅[如何： 使用 DateTimePicker 控件显示时间](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md)。  
  
 当<xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A>属性设置为`true`，控件中的选定日期旁边显示一个复选框。 选中复选框后，可以更新所选的日期时间值。 如果复选框为空，值显示为不可用。  
  
 控件的<xref:System.Windows.Forms.DateTimePicker.MaxDate%2A>和<xref:System.Windows.Forms.DateTimePicker.MinDate%2A>属性确定日期和时间的范围。 <xref:System.Windows.Forms.DateTimePicker.Value%2A>属性包含的当前日期和时间控件设置为。 有关详细信息，请参阅[如何： 设置和使用 Windows 窗体 DateTimePicker 控件返回日期](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)。 值可以显示在四种格式，通过设置<xref:System.Windows.Forms.DateTimePicker.Format%2A>属性： <xref:System.Windows.Forms.DateTimePickerFormat.Long>， <xref:System.Windows.Forms.DateTimePickerFormat.Short>， <xref:System.Windows.Forms.DateTimePickerFormat.Time>，或<xref:System.Windows.Forms.DateTimePickerFormat.Custom>。 如果选择自定义格式，则必须设置<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>为适当的字符串的属性。 有关详细信息，请参阅[如何： 使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)。  
  
## <a name="see-also"></a>另请参阅  
 [如何：使用 Windows 窗体 DateTimePicker 控件显示自定义格式的日期](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)  
 [如何：使用 Windows 窗体 DateTimePicker 控件设置和返回日期](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
