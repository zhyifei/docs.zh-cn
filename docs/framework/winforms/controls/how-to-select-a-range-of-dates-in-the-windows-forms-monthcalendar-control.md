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
ms.openlocfilehash: 4c7100f77c313d219cfd4cceff5ae3015eae4c18
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558444"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="cdd32-102">如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围</span><span class="sxs-lookup"><span data-stu-id="cdd32-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="cdd32-103">Windows 窗体的一个重要功能<xref:System.Windows.Forms.MonthCalendar>控件是用户可以选择日期范围内的。</span><span class="sxs-lookup"><span data-stu-id="cdd32-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="cdd32-104">此功能是对的日期选择功能的改进<xref:System.Windows.Forms.DateTimePicker>控件，仅使用户能够选择单个日期/时间值。</span><span class="sxs-lookup"><span data-stu-id="cdd32-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="cdd32-105">可以设置的日期范围或获取由用户设置使用的属性的选择范围<xref:System.Windows.Forms.MonthCalendar>控件。</span><span class="sxs-lookup"><span data-stu-id="cdd32-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="cdd32-106">下面的代码示例演示如何设置选择范围。</span><span class="sxs-lookup"><span data-stu-id="cdd32-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="cdd32-107">若要选择的日期范围</span><span class="sxs-lookup"><span data-stu-id="cdd32-107">To select a range of dates</span></span>  
  
1.  <span data-ttu-id="cdd32-108">创建<xref:System.DateTime>对象表示范围中的第一个和最后一个日期。</span><span class="sxs-lookup"><span data-stu-id="cdd32-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
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
  
2.  <span data-ttu-id="cdd32-109">设置 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="cdd32-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
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
  
     <span data-ttu-id="cdd32-110">- 或 -</span><span class="sxs-lookup"><span data-stu-id="cdd32-110">–or–</span></span>  
  
     <span data-ttu-id="cdd32-111">设置 <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> 和 <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="cdd32-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cdd32-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdd32-112">See also</span></span>
- [<span data-ttu-id="cdd32-113">MonthCalendar 控件</span><span class="sxs-lookup"><span data-stu-id="cdd32-113">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="cdd32-114">如何：更改 Windows 窗体 MonthCalendar 控件的外观</span><span class="sxs-lookup"><span data-stu-id="cdd32-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="cdd32-115">如何：特定以粗体的显示日期与 Windows 窗体 MonthCalendar 控件</span><span class="sxs-lookup"><span data-stu-id="cdd32-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="cdd32-116">如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份</span><span class="sxs-lookup"><span data-stu-id="cdd32-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
