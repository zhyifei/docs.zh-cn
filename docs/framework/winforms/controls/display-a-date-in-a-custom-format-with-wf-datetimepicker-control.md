---
title: 如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: 2f563b5de9b80dab2af00290e8a6b3b309410a9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526004"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期
Windows 窗体<xref:System.Windows.Forms.DateTimePicker>控件使您可以灵活地设置日期和时间控件中的显示格式。 <xref:System.Windows.Forms.DateTimePicker.Format%2A>属性允许你选择从预定义的格式，列入<xref:System.Windows.Forms.DateTimePickerFormat>。 如果这些都足以满足你的用途，则可以创建使用格式字符中列出你自己的格式样式<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>。  
  
### <a name="to-display-a-custom-format"></a>若要显示自定义格式  
  
1.  将 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 属性设置为 `DateTimePickerFormat.Custom`。  
  
2.  设置<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>到一个格式字符串的属性。  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a>将文本添加到的格式化值  
  
1.  使用单引号括起来的格式字符，如"M"） 或分隔符 （如不是任何字符":"。 例如，下面的格式字符串显示当前日期，以格式"现在是： 05:30:31 2012 年 3 月 2 日，星期五"英语 （美国） 区域性。  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     根据区域性设置中，任何未括在单引号字符可能会发生更改。 例如，上面的格式字符串显示当前日期，以格式"现在是： 05:30:31 2012 年 3 月 2 日，星期五"英语 （美国） 区域性。 请注意，将第一个冒号括在单引号中，因为它不应为分隔字符，因为它处于"hh: mm:"。 在另一个区域性格式可能显示为"现在是： 05.30.31 2012 年 3 月 2 日，星期五"。  
  
## <a name="see-also"></a>请参阅  
 [DateTimePicker 控件](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [如何：使用 Windows 窗体 DateTimePicker 控件设置和返回日期](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
