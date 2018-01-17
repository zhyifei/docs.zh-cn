---
title: "如何： 更改 Windows 窗体 MonthCalendar 控件 &#39; s 外观"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9c401532fa7a5f09462cf12084f32bca3f721cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a>如何： 更改 Windows 窗体 MonthCalendar 控件 &#39; s 外观
Windows 窗体<xref:System.Windows.Forms.MonthCalendar>控件允许你自定义在许多方面的日历的外观。 例如，你可以设置配色方案，并选择以显示或隐藏周数和当前日期。  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>若要更改月历的配色方案  
  
-   设置属性，如<xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>，<xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>和<xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>。 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>属性还为每周天数中确定的字体颜色。 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>属性确定的日期之前和之后显示的月份的颜色。  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    >  启动与 Windows Vista 和具体取决于主题，设置某些属性可能不更改的外观的日历。 例如，如果 Windows 设置为使用 Aero 主题，设置<xref:System.Windows.Forms.MonthCalendar.BackColor%2A>， <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>， <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>，或<xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>属性不起作用。 这是因为日历的更新的版本呈现在运行时派生自当前的操作系统主题的外观。 如果你想要使用这些属性和启用日历的早期版本，你可以为你的应用程序禁用视觉样式。 禁用视觉样式可能会影响的外观和应用程序中其他控件的行为。 若要禁用在 Visual Basic 中的视觉样式，打开项目设计器，并取消选中**启用 XP 视觉样式**复选框。 若要禁用在 C# 中的视觉样式，打开 Program.cs，并注释掉`Application.EnableVisualStyles();`。 关于视觉样式的详细信息，请参阅[如何： 启用 Windows XP 视觉样式](http://msdn.microsoft.com/en-us/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f)。  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>若要在控件底部显示当前日期  
  
-   将 <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 属性设置为 `true`。 下面的示例显示和省略窗体时在双击今天的日期之间切换。  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)][!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>若要显示周数  
  
-   将 <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 属性设置为 `true`。 在代码中或在属性窗口中，你可以设置此属性。  
  
     在一周的第一天左侧一个单独的列中显示周数。  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>请参阅  
 [MonthCalendar 控件](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示具体日期](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
