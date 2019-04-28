---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 555bf31b27ba233ffa54438077984b02b5e3084a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911973"
---
# <a name="datepicker"></a><span data-ttu-id="1e2fe-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="1e2fe-102">DatePicker</span></span>
<span data-ttu-id="1e2fe-103"><xref:System.Windows.Controls.DatePicker>控件允许用户通过下拉列表中键入文本字段，或选择日期<xref:System.Windows.Controls.Calendar>控件。</span><span class="sxs-lookup"><span data-stu-id="1e2fe-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="1e2fe-104">下图显示<xref:System.Windows.Controls.DatePicker>。</span><span class="sxs-lookup"><span data-stu-id="1e2fe-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="1e2fe-105">![DatePicker 控件](./media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="1e2fe-105">![DatePicker control](./media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="1e2fe-106">DatePicker 控件</span><span class="sxs-lookup"><span data-stu-id="1e2fe-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="1e2fe-107">许多<xref:System.Windows.Controls.DatePicker>控件的属性是用于管理其内置<xref:System.Windows.Controls.Calendar>，和函数中的等效属性与相同<xref:System.Windows.Controls.Calendar>。</span><span class="sxs-lookup"><span data-stu-id="1e2fe-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="1e2fe-108">具体而言， <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>，以及<xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType>属性函数完全相同其<xref:System.Windows.Controls.Calendar>对应项。</span><span class="sxs-lookup"><span data-stu-id="1e2fe-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="1e2fe-109">有关详细信息，请参阅 <xref:System.Windows.Controls.Calendar>。</span><span class="sxs-lookup"><span data-stu-id="1e2fe-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="1e2fe-110">用户可以直接在设置的文本字段中键入日期<xref:System.Windows.Controls.DatePicker.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1e2fe-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="1e2fe-111">如果<xref:System.Windows.Controls.DatePicker>无法将输入的字符串转换为有效的日期，<xref:System.Windows.Controls.DatePicker.DateValidationError>将引发事件。</span><span class="sxs-lookup"><span data-stu-id="1e2fe-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="1e2fe-112">默认情况下，这会导致异常，但的事件处理程序<xref:System.Windows.Controls.DatePicker.DateValidationError>可以设置<xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A>属性设置为`false`并防止引发异常。</span><span class="sxs-lookup"><span data-stu-id="1e2fe-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e2fe-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e2fe-113">See also</span></span>

- [<span data-ttu-id="1e2fe-114">控件</span><span class="sxs-lookup"><span data-stu-id="1e2fe-114">Controls</span></span>](index.md)
- [<span data-ttu-id="1e2fe-115">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="1e2fe-115">Styling and Templating</span></span>](styling-and-templating.md)
