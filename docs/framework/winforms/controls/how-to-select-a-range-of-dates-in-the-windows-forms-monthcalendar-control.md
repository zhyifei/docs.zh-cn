---
title: 在 MonthCalendar 控件中选择日期范围
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
ms.openlocfilehash: bda96af21a8f86a54d5c0fe0204546b980076d26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732895"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택
Windows 窗体 <xref:System.Windows.Forms.MonthCalendar> 控件的一项重要功能是用户可以选择日期范围。 此功能优于 <xref:System.Windows.Forms.DateTimePicker> 控件的日期选择功能，只允许用户选择单个日期/时间值。 您可以通过使用 <xref:System.Windows.Forms.MonthCalendar> 控件的属性来设置日期范围或获取由用户设置的选择范围。 下面的代码示例演示如何设置选择范围。  
  
### <a name="to-select-a-range-of-dates"></a>选择日期范围  
  
1. 创建表示范围中第一个和最后一个日期的 <xref:System.DateTime> 对象。  
  
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
  
2. <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 속성을 설정합니다.  
  
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
  
     – 또는 –  
  
     <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> 및 <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> 속성을 설정합니다.  
  
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
  
## <a name="see-also"></a>另请参阅

- [MonthCalendar 컨트롤](monthcalendar-control-windows-forms.md)
- [방법: Windows Forms MonthCalendar 컨트롤의 모양 변경](how-to-change-monthcalendar-control-appearance.md)
- [방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시](display-more-than-one-month-wf-monthcalendar-control.md)
