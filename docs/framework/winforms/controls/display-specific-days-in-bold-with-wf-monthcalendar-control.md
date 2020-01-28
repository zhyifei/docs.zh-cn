---
title: 用 MonthCalendar 控件以粗体显示特定日期
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: 377eb76f562fff20aae2136ddb7130516d2d76f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745879"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="db49d-102">방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시</span><span class="sxs-lookup"><span data-stu-id="db49d-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="db49d-103">Windows 窗体 <xref:System.Windows.Forms.MonthCalendar> 控件可以将以粗体显示的日期显示为 "单数" 或 "重复"。</span><span class="sxs-lookup"><span data-stu-id="db49d-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="db49d-104">您可以这样做，以突出特殊日期，如假日和周末。</span><span class="sxs-lookup"><span data-stu-id="db49d-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="db49d-105">这三个属性控制此功能。</span><span class="sxs-lookup"><span data-stu-id="db49d-105">Three properties control this feature.</span></span> <span data-ttu-id="db49d-106"><xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> 属性包含一个日期。</span><span class="sxs-lookup"><span data-stu-id="db49d-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="db49d-107"><xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> 属性包含每年以粗体显示的日期。</span><span class="sxs-lookup"><span data-stu-id="db49d-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="db49d-108"><xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 属性包含每月以粗体显示的日期。</span><span class="sxs-lookup"><span data-stu-id="db49d-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="db49d-109">其中每个属性都包含一个 <xref:System.DateTime> 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="db49d-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="db49d-110">若要在这些列表之一中添加或删除日期，必须添加或删除 <xref:System.DateTime> 对象。</span><span class="sxs-lookup"><span data-stu-id="db49d-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="db49d-111">使日期显示为粗体</span><span class="sxs-lookup"><span data-stu-id="db49d-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="db49d-112">创建 <xref:System.DateTime> 对象。</span><span class="sxs-lookup"><span data-stu-id="db49d-112">Create the <xref:System.DateTime> objects.</span></span>  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2. <span data-ttu-id="db49d-113">通过调用 <xref:System.Windows.Forms.MonthCalendar> 控件的 <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>、<xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>或 <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> 方法，使单个日期为粗体。</span><span class="sxs-lookup"><span data-stu-id="db49d-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="db49d-114">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="db49d-114">–or–</span></span>  
  
     <span data-ttu-id="db49d-115">通过创建 <xref:System.DateTime> 对象的数组，并将其分配给其中一个属性，使一组日期同时为粗体。</span><span class="sxs-lookup"><span data-stu-id="db49d-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="db49d-116">使日期显示为常规字体</span><span class="sxs-lookup"><span data-stu-id="db49d-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="db49d-117">通过调用 <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>、<xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>或 <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> 方法，使单个以粗体显示的日期显示为常规字体。</span><span class="sxs-lookup"><span data-stu-id="db49d-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="db49d-118">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="db49d-118">–or–</span></span>  
  
     <span data-ttu-id="db49d-119">通过调用 <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>、<xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>或 <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> 方法，从三个列表之一删除所有粗体日期。</span><span class="sxs-lookup"><span data-stu-id="db49d-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="db49d-120">通过调用 <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> 方法来更新字体的外观。</span><span class="sxs-lookup"><span data-stu-id="db49d-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="db49d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db49d-121">See also</span></span>

- [<span data-ttu-id="db49d-122">MonthCalendar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="db49d-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="db49d-123">방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택</span><span class="sxs-lookup"><span data-stu-id="db49d-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="db49d-124">방법: Windows Forms MonthCalendar 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="db49d-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="db49d-125">방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시</span><span class="sxs-lookup"><span data-stu-id="db49d-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
