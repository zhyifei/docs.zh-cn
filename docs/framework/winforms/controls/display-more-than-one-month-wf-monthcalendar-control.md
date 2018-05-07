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
ms.openlocfilehash: a71f85af2d51faf37160aba7fa89a8421b4523d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份
Windows 窗体<xref:System.Windows.Forms.MonthCalendar>控件可以一次显示最多 12 个月。 默认情况下，该控件将显示仅一个月，但你可以指定多少个月的显示，并且它们在控件内的排列方式。 当你更改日历维度时，请调整控件的因此请确保在新维度的窗体上没有足够的空间。  
  
### <a name="to-display-multiple-months"></a>若要显示多个月份  
  
-   设置<xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>属性设置为要显示水平和垂直的月数。  
  
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
 [MonthCalendar 控件](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [如何：更改 Windows 窗体 MonthCalendar 控件的外观](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
