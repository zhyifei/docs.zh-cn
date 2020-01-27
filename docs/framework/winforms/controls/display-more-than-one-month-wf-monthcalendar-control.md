---
title: 在 MonthCalendar 控件中显示多个月
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], formatting display
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], multiple months
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
ms.openlocfilehash: 5d3925bc19ddcd67742f0ab8b5b2e45530820f38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745898"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시
Windows 窗体 <xref:System.Windows.Forms.MonthCalendar> 控件一次最多可以显示12个月。 默认情况下，该控件只显示一个月，但您可以指定显示的月份数以及它们在控件中的排列方式。 更改日历维度时，控件的大小会调整，因此请确保窗体上有足够的空间用于新维度。  
  
### <a name="to-display-multiple-months"></a>显示多个月  
  
- 将 <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 属性设置为水平和垂直显示的月份数。  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>另请参阅

- [MonthCalendar 컨트롤](monthcalendar-control-windows-forms.md)
- [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [방법: Windows Forms MonthCalendar 컨트롤의 모양 변경](how-to-change-monthcalendar-control-appearance.md)
