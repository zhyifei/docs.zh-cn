---
title: 如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份
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
ms.openlocfilehash: 79100b52d8e0a5b651edb9d6555a4497287ed858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972135"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份
Windows 窗体<xref:System.Windows.Forms.MonthCalendar>控件可以显示一次最多 12 个月。 默认情况下，该控件将显示仅一个月，但可以指定显示多少个月，它们在控件内的排列方式。 更改日历维度时，控件的大小调整，因此请确保新维度的窗体上没有足够的空间。  
  
### <a name="to-display-multiple-months"></a>若要显示多个月份  
  
- 设置<xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>属性设置为要显示水平和垂直的月数。  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>请参阅

- [MonthCalendar 控件](monthcalendar-control-windows-forms.md)
- [如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [如何：更改 Windows 窗体 MonthCalendar 控件的外观](how-to-change-monthcalendar-control-appearance.md)
