---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 3e66b2306c11c54db14eb05cc6860257635cc653
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460354"
---
# <a name="datepicker"></a><span data-ttu-id="57a69-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="57a69-102">DatePicker</span></span>
<span data-ttu-id="57a69-103"><xref:System.Windows.Controls.DatePicker> 控件允许用户通过在文本字段中键入日期或使用下拉 <xref:System.Windows.Controls.Calendar> 控件来选择日期。</span><span class="sxs-lookup"><span data-stu-id="57a69-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="57a69-104">下图显示了一个 <xref:System.Windows.Controls.DatePicker>。</span><span class="sxs-lookup"><span data-stu-id="57a69-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="57a69-105">![DatePicker 控件](./media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="57a69-105">![DatePicker control](./media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="57a69-106">DatePicker 控件</span><span class="sxs-lookup"><span data-stu-id="57a69-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="57a69-107">许多 <xref:System.Windows.Controls.DatePicker> 控件的属性用于管理它的内置 <xref:System.Windows.Controls.Calendar>，并与 <xref:System.Windows.Controls.Calendar>中的等效属性相同。</span><span class="sxs-lookup"><span data-stu-id="57a69-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="57a69-108">特别是，<xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>和 <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> 属性的功能与它们的 <xref:System.Windows.Controls.Calendar> 对应项的功能相同。</span><span class="sxs-lookup"><span data-stu-id="57a69-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="57a69-109">有关更多信息，请参见<xref:System.Windows.Controls.Calendar>。</span><span class="sxs-lookup"><span data-stu-id="57a69-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="57a69-110">用户可以直接在文本字段中键入日期，这将设置 "<xref:System.Windows.Controls.DatePicker.Text%2A>" 属性。</span><span class="sxs-lookup"><span data-stu-id="57a69-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="57a69-111">如果 <xref:System.Windows.Controls.DatePicker> 不能将输入的字符串转换为有效日期，将引发 <xref:System.Windows.Controls.DatePicker.DateValidationError> 事件。</span><span class="sxs-lookup"><span data-stu-id="57a69-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="57a69-112">默认情况下，这会引发异常，但 <xref:System.Windows.Controls.DatePicker.DateValidationError> 的事件处理程序可以将 <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> 属性设置为 `false` 并防止引发异常。</span><span class="sxs-lookup"><span data-stu-id="57a69-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a69-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="57a69-113">See also</span></span>

- [<span data-ttu-id="57a69-114">控件</span><span class="sxs-lookup"><span data-stu-id="57a69-114">Controls</span></span>](index.md)
- [<span data-ttu-id="57a69-115">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="57a69-115">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
