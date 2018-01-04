---
title: "MonthCalendar 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a22667e4227067dfbf0baaad1838ab520e0ac7e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="monthcalendar-control-overview-windows-forms"></a><span data-ttu-id="0dad0-102">MonthCalendar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0dad0-102">MonthCalendar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="0dad0-103">Windows 窗体<xref:System.Windows.Forms.MonthCalendar>控件显示直观的图形界面，供用户查看并设置日期信息。</span><span class="sxs-lookup"><span data-stu-id="0dad0-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control presents an intuitive graphical interface for users to view and set date information.</span></span> <span data-ttu-id="0dad0-104">该控件将显示一个日历： 包含排列在列下方的日期突出显示所选的范围内一周中的天的月份的编号的日期的网格。</span><span class="sxs-lookup"><span data-stu-id="0dad0-104">The control displays a calendar: a grid containing the numbered days of the month, arranged in columns underneath the days of the week, with the selected range of dates highlighted.</span></span> <span data-ttu-id="0dad0-105">你可以通过单击箭头按钮在月标题的任意一侧选择不同的月份。</span><span class="sxs-lookup"><span data-stu-id="0dad0-105">You can select a different month by clicking the arrow buttons on either side of the month caption.</span></span> <span data-ttu-id="0dad0-106">与类似<xref:System.Windows.Forms.DateTimePicker>控件，您可以选择与此控件的多个日期。</span><span class="sxs-lookup"><span data-stu-id="0dad0-106">Unlike the similar <xref:System.Windows.Forms.DateTimePicker> control, you can select more than one date with this control.</span></span> <span data-ttu-id="0dad0-107">有关详细信息<xref:System.Windows.Forms.DateTimePicker>控制，请参阅[DateTimePicker 控件](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="0dad0-107">For more information about the <xref:System.Windows.Forms.DateTimePicker> control, see [DateTimePicker Control](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md).</span></span>  
  
## <a name="configuring-the-monthcalendar-control"></a><span data-ttu-id="0dad0-108">配置 MonthCalendar 控件</span><span class="sxs-lookup"><span data-stu-id="0dad0-108">Configuring the MonthCalendar Control</span></span>  
 <span data-ttu-id="0dad0-109"><xref:System.Windows.Forms.MonthCalendar>控件的外观会高度可配置。</span><span class="sxs-lookup"><span data-stu-id="0dad0-109">The <xref:System.Windows.Forms.MonthCalendar> control's appearance is highly configurable.</span></span> <span data-ttu-id="0dad0-110">默认情况下，今天的日期显示为圆形，并且还显示在网格底部。</span><span class="sxs-lookup"><span data-stu-id="0dad0-110">By default, today's date is displayed as circled, and is also noted at the bottom of the grid.</span></span> <span data-ttu-id="0dad0-111">你可以通过设置来更改此功能<xref:System.Windows.Forms.MonthCalendar.ShowToday%2A>和<xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="0dad0-111">You can change this feature by setting the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> and <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> properties to `false`.</span></span> <span data-ttu-id="0dad0-112">你还可以将周数通过设置添加到日历<xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="0dad0-112">You can also add week numbers to the calendar by setting the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="0dad0-113">通过设置<xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>属性，可以有多个显示水平和垂直月份。</span><span class="sxs-lookup"><span data-stu-id="0dad0-113">By setting the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property, you can have multiple months displayed horizontally and vertically.</span></span> <span data-ttu-id="0dad0-114">默认情况下，星期日显示为每周的第一天，但可以使用指定任何一天<xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0dad0-114">By default, Sunday is shown as the first day of the week, but any day can be designated using the <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> property.</span></span>  
  
 <span data-ttu-id="0dad0-115">你还可以设置要在中显示的特定日期上一次性地，每年或每月，以粗体显示通过添加<xref:System.DateTime>对象添加到<xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>， <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>，和<xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0dad0-115">You can also set certain dates to be displayed in bold on a one-time basis, annually, or monthly, by adding <xref:System.DateTime> objects to the <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>, and <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> properties.</span></span> <span data-ttu-id="0dad0-116">有关详细信息，请参阅[如何： 显示特定日期中使用 Windows 窗体 MonthCalendar 控件加粗](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0dad0-116">For more information, see [How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md).</span></span>  
  
 <span data-ttu-id="0dad0-117">键属性的<xref:System.Windows.Forms.MonthCalendar>控件是<xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>，选择控件中的日期范围。</span><span class="sxs-lookup"><span data-stu-id="0dad0-117">The key property of the <xref:System.Windows.Forms.MonthCalendar> control is <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, the range of dates selected in the control.</span></span> <span data-ttu-id="0dad0-118"><xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>值不能超过最大天数，可以选择，在中设置<xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0dad0-118">The <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> value cannot exceed the maximum number of days that can be selected, set in the <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> property.</span></span> <span data-ttu-id="0dad0-119">用户可以选择的最早时间和最新日期由<xref:System.Windows.Forms.MonthCalendar.MaxDate%2A>和<xref:System.Windows.Forms.MonthCalendar.MinDate%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0dad0-119">The earliest and latest dates the user can select are determined by the <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> and <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dad0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0dad0-120">See Also</span></span>  
 <xref:System.Windows.Forms.MonthCalendar>  
 [<span data-ttu-id="0dad0-121">MonthCalendar 控件</span><span class="sxs-lookup"><span data-stu-id="0dad0-121">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
