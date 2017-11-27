---
title: DatePicker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd5c7c796ee9d51a216368de3f3b04c10a5a3acd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="datepicker"></a><span data-ttu-id="06ec0-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="06ec0-102">DatePicker</span></span>
<span data-ttu-id="06ec0-103"><xref:System.Windows.Controls.DatePicker>控件允许用户通过中键入文本字段或使用下拉列表选择一个日期<xref:System.Windows.Controls.Calendar>控件。</span><span class="sxs-lookup"><span data-stu-id="06ec0-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="06ec0-104">下图显示<xref:System.Windows.Controls.DatePicker>。</span><span class="sxs-lookup"><span data-stu-id="06ec0-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="06ec0-105">![DatePicker 控件](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="06ec0-105">![DatePicker control](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="06ec0-106">DatePicker 控件</span><span class="sxs-lookup"><span data-stu-id="06ec0-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="06ec0-107">许多<xref:System.Windows.Controls.DatePicker>控件的属性是用于管理其内置<xref:System.Windows.Controls.Calendar>，和相同函数中的等效属性<xref:System.Windows.Controls.Calendar>。</span><span class="sxs-lookup"><span data-stu-id="06ec0-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="06ec0-108">具体而言， <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>，和<xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType>属性完全相同函数其<xref:System.Windows.Controls.Calendar>对应项。</span><span class="sxs-lookup"><span data-stu-id="06ec0-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="06ec0-109">有关详细信息，请参阅<xref:System.Windows.Controls.Calendar>。</span><span class="sxs-lookup"><span data-stu-id="06ec0-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="06ec0-110">用户可以直接在文本字段，该设置字段中键入日期<xref:System.Windows.Controls.DatePicker.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="06ec0-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="06ec0-111">如果<xref:System.Windows.Controls.DatePicker>无法将输入的字符串转换为有效日期，<xref:System.Windows.Controls.DatePicker.DateValidationError>将引发事件。</span><span class="sxs-lookup"><span data-stu-id="06ec0-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="06ec0-112">默认情况下，这会导致异常，但的事件处理程序<xref:System.Windows.Controls.DatePicker.DateValidationError>可以设置<xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A>属性`false`和阻止引发异常。</span><span class="sxs-lookup"><span data-stu-id="06ec0-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ec0-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06ec0-113">See Also</span></span>  
 [<span data-ttu-id="06ec0-114">控件</span><span class="sxs-lookup"><span data-stu-id="06ec0-114">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="06ec0-115">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="06ec0-115">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
