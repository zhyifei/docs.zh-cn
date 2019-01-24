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
ms.openlocfilehash: 164369ab1a94249470b57e546db64be8e17b99bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582023"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="5375c-102">如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份</span><span class="sxs-lookup"><span data-stu-id="5375c-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="5375c-103">Windows 窗体<xref:System.Windows.Forms.MonthCalendar>控件可以显示一次最多 12 个月。</span><span class="sxs-lookup"><span data-stu-id="5375c-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="5375c-104">默认情况下，该控件将显示仅一个月，但可以指定显示多少个月，它们在控件内的排列方式。</span><span class="sxs-lookup"><span data-stu-id="5375c-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="5375c-105">更改日历维度时，控件的大小调整，因此请确保新维度的窗体上没有足够的空间。</span><span class="sxs-lookup"><span data-stu-id="5375c-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="5375c-106">若要显示多个月份</span><span class="sxs-lookup"><span data-stu-id="5375c-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="5375c-107">设置<xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>属性设置为要显示水平和垂直的月数。</span><span class="sxs-lookup"><span data-stu-id="5375c-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5375c-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="5375c-108">See also</span></span>
- [<span data-ttu-id="5375c-109">MonthCalendar 控件</span><span class="sxs-lookup"><span data-stu-id="5375c-109">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="5375c-110">如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围</span><span class="sxs-lookup"><span data-stu-id="5375c-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="5375c-111">如何：更改 Windows 窗体 MonthCalendar 控件的外观</span><span class="sxs-lookup"><span data-stu-id="5375c-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
