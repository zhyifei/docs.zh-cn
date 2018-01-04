---
title: "如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示特定日期"
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
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 141d943c4f4dfc3976e66e13e7c0975aba3f1687
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="999b9-102">如何：使用 Windows 窗体 MonthCalendar 控件以粗体显示特定日期</span><span class="sxs-lookup"><span data-stu-id="999b9-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="999b9-103">Windows 窗体<xref:System.Windows.Forms.MonthCalendar>控件可以显示天粗体类型为单数日期或在重复的基础上。</span><span class="sxs-lookup"><span data-stu-id="999b9-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="999b9-104">你可以这样做来绘制成特殊的日期，例如节假日和周末的关注。</span><span class="sxs-lookup"><span data-stu-id="999b9-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="999b9-105">三个属性控制此功能。</span><span class="sxs-lookup"><span data-stu-id="999b9-105">Three properties control this feature.</span></span> <span data-ttu-id="999b9-106"><xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>属性包含一个日期。</span><span class="sxs-lookup"><span data-stu-id="999b9-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="999b9-107"><xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>属性包含每年以粗体显示的日期。</span><span class="sxs-lookup"><span data-stu-id="999b9-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="999b9-108"><xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>属性包含以粗体显示每个月的日期。</span><span class="sxs-lookup"><span data-stu-id="999b9-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="999b9-109">上述每个属性包含的数组<xref:System.DateTime>对象。</span><span class="sxs-lookup"><span data-stu-id="999b9-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="999b9-110">若要添加或移除其中一个列表的日期，必须将其添加或删除<xref:System.DateTime>对象。</span><span class="sxs-lookup"><span data-stu-id="999b9-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="999b9-111">若要使以粗体显示日期</span><span class="sxs-lookup"><span data-stu-id="999b9-111">To make a date appear in bold type</span></span>  
  
1.  <span data-ttu-id="999b9-112">创建<xref:System.DateTime>对象。</span><span class="sxs-lookup"><span data-stu-id="999b9-112">Create the <xref:System.DateTime> objects.</span></span>  
  
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
  
2.  <span data-ttu-id="999b9-113">使单个日期加粗通过调用<xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>， <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>，或<xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A>方法<xref:System.Windows.Forms.MonthCalendar>控件。</span><span class="sxs-lookup"><span data-stu-id="999b9-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
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
  
     <span data-ttu-id="999b9-114">- 或 -</span><span class="sxs-lookup"><span data-stu-id="999b9-114">–or–</span></span>  
  
     <span data-ttu-id="999b9-115">使的一组日期以粗体显示在一次创建数组<xref:System.DateTime>对象并将其分配到属性之一。</span><span class="sxs-lookup"><span data-stu-id="999b9-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="999b9-116">若要使日期中的正则字体显示</span><span class="sxs-lookup"><span data-stu-id="999b9-116">To make a date appear in the regular font</span></span>  
  
1.  <span data-ttu-id="999b9-117">使单个粗体日期中的正则字体显示通过调用<xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>， <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>，或<xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="999b9-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="999b9-118">- 或 -</span><span class="sxs-lookup"><span data-stu-id="999b9-118">–or–</span></span>  
  
     <span data-ttu-id="999b9-119">通过调用从一个三个列表中删除所有的粗体日期<xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>， <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>，或<xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="999b9-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  <span data-ttu-id="999b9-120">通过调用更新的字体的外观<xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="999b9-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="999b9-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="999b9-121">See Also</span></span>  
 [<span data-ttu-id="999b9-122">MonthCalendar 控件</span><span class="sxs-lookup"><span data-stu-id="999b9-122">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="999b9-123">如何：在 Windows 窗体 MonthCalendar 控件中选择日期范围</span><span class="sxs-lookup"><span data-stu-id="999b9-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="999b9-124">如何：更改 Windows 窗体 MonthCalendar 控件的外观</span><span class="sxs-lookup"><span data-stu-id="999b9-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 [<span data-ttu-id="999b9-125">如何：在 Windows 窗体 MonthCalendar 控件中显示多个月份</span><span class="sxs-lookup"><span data-stu-id="999b9-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
