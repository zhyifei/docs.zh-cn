---
title: 如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: 8b6d64fcffb02c4496cff3f2821861117b0062fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围
Windows 窗体的一个重要特征<xref:System.Windows.Forms.MonthCalendar>控件是用户可以选择的日期范围。 此功能是对的日期选择功能的改进<xref:System.Windows.Forms.DateTimePicker>控件，后者只允许用户选择的单个日期/时间值。 您可以设置的日期范围或获取由用户通过使用属性的设置选择范围<xref:System.Windows.Forms.MonthCalendar>控件。 下面的代码示例演示如何设置选择范围。  
  
### <a name="to-select-a-range-of-dates"></a>若要选择的日期范围  
  
1.  创建<xref:System.DateTime>表示范围中的第一个和最后一个日期的对象。  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2.  设置 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 属性。  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     - 或 -  
  
     设置 <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> 和 <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> 属性。  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a>请参阅  
 [MonthCalendar 控件](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [如何：更改 Windows 窗体 MonthCalendar 控件的外观](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 [如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示具体日期](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
