---
title: 如何： 更改 Windows 窗体 MonthCalendar 控件&#39;的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 4f91363764099cabfa1a7939ff07e627aeb6c815
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467660"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a><span data-ttu-id="3566d-102">如何： 更改 Windows 窗体 MonthCalendar 控件&#39;的外观</span><span class="sxs-lookup"><span data-stu-id="3566d-102">How to: Change the Windows Forms MonthCalendar Control&#39;s Appearance</span></span>
<span data-ttu-id="3566d-103">Windows 窗体<xref:System.Windows.Forms.MonthCalendar>让您可以自定义在很多方面的日历的外观。</span><span class="sxs-lookup"><span data-stu-id="3566d-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="3566d-104">例如，可以设置配色方案，并选择要显示或隐藏周数和当前日期。</span><span class="sxs-lookup"><span data-stu-id="3566d-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="3566d-105">若要更改月日历的配色方案</span><span class="sxs-lookup"><span data-stu-id="3566d-105">To change the month calendar's color scheme</span></span>  
  
-   <span data-ttu-id="3566d-106">设置属性，如<xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>，<xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>和<xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>。</span><span class="sxs-lookup"><span data-stu-id="3566d-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="3566d-107"><xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>属性还为每周天数中确定的字体颜色。</span><span class="sxs-lookup"><span data-stu-id="3566d-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="3566d-108"><xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>属性确定的日期之前和之后显示的月或几个月的颜色。</span><span class="sxs-lookup"><span data-stu-id="3566d-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    >  <span data-ttu-id="3566d-109">从开始使用 Windows Vista，具体取决于主题，设置某些属性可能会更改日历的外观。</span><span class="sxs-lookup"><span data-stu-id="3566d-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="3566d-110">例如，如果 Windows 设置为使用 Aero 主题，则将设置<xref:System.Windows.Forms.MonthCalendar.BackColor%2A>， <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>， <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>，或<xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>属性不起作用。</span><span class="sxs-lookup"><span data-stu-id="3566d-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="3566d-111">这是因为该日历的更新的版本呈现在运行时派生自当前操作系统主题的外观。</span><span class="sxs-lookup"><span data-stu-id="3566d-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="3566d-112">如果你想要使用这些属性，并启用日历的早期版本，则可以为应用程序禁用视觉样式。</span><span class="sxs-lookup"><span data-stu-id="3566d-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="3566d-113">禁用视觉样式，可能会影响的外观和行为的应用程序中的其他控件。</span><span class="sxs-lookup"><span data-stu-id="3566d-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="3566d-114">若要禁用在 Visual Basic 中的视觉样式，请打开项目设计器，并取消选中**启用 XP 视觉样式**复选框。</span><span class="sxs-lookup"><span data-stu-id="3566d-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="3566d-115">若要禁用视觉样式在 C# 中的，打开 Program.cs，并注释掉`Application.EnableVisualStyles();`。</span><span class="sxs-lookup"><span data-stu-id="3566d-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="3566d-116">视觉样式的详细信息，请参阅[如何： 启用 Windows XP 视觉样式](https://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f)。</span><span class="sxs-lookup"><span data-stu-id="3566d-116">For more information about visual styles, see [How to: Enable Windows XP Visual Styles](https://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="3566d-117">若要在控件的底部显示当前日期</span><span class="sxs-lookup"><span data-stu-id="3566d-117">To display the current date at the bottom of the control</span></span>  
  
-   <span data-ttu-id="3566d-118">将 <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="3566d-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="3566d-119">下面的示例显示和省略双击窗体之后今天的日期之间切换。</span><span class="sxs-lookup"><span data-stu-id="3566d-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="3566d-120">(Visual C#， [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3566d-120">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="3566d-121">若要显示周数</span><span class="sxs-lookup"><span data-stu-id="3566d-121">To display week numbers</span></span>  
  
-   <span data-ttu-id="3566d-122">将 <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="3566d-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="3566d-123">在代码中或在属性窗口中，可以设置此属性。</span><span class="sxs-lookup"><span data-stu-id="3566d-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="3566d-124">在左侧的一周的第一天到一个单独的列中显示周数。</span><span class="sxs-lookup"><span data-stu-id="3566d-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3566d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3566d-125">See Also</span></span>  
 [<span data-ttu-id="3566d-126">MonthCalendar 控件</span><span class="sxs-lookup"><span data-stu-id="3566d-126">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="3566d-127">如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围</span><span class="sxs-lookup"><span data-stu-id="3566d-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="3566d-128">如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示具体日期</span><span class="sxs-lookup"><span data-stu-id="3566d-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [<span data-ttu-id="3566d-129">如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份</span><span class="sxs-lookup"><span data-stu-id="3566d-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
