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
# <a name="datepicker"></a>DatePicker
<xref:System.Windows.Controls.DatePicker> 控件允许用户通过在文本字段中键入日期或使用下拉 <xref:System.Windows.Controls.Calendar> 控件来选择日期。  
  
 下图显示了一个 <xref:System.Windows.Controls.DatePicker>。  
  
 ![DatePicker 控件](./media/ndp-datepicker.png "NDP_DatePicker")  
DatePicker 控件  
  
 许多 <xref:System.Windows.Controls.DatePicker> 控件的属性用于管理它的内置 <xref:System.Windows.Controls.Calendar>，并与 <xref:System.Windows.Controls.Calendar>中的等效属性相同。 特别是，<xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>、<xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>和 <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> 属性的功能与它们的 <xref:System.Windows.Controls.Calendar> 对应项的功能相同。 有关更多信息，请参见<xref:System.Windows.Controls.Calendar>。  
  
 用户可以直接在文本字段中键入日期，这将设置 "<xref:System.Windows.Controls.DatePicker.Text%2A>" 属性。 如果 <xref:System.Windows.Controls.DatePicker> 不能将输入的字符串转换为有效日期，将引发 <xref:System.Windows.Controls.DatePicker.DateValidationError> 事件。 默认情况下，这会引发异常，但 <xref:System.Windows.Controls.DatePicker.DateValidationError> 的事件处理程序可以将 <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> 属性设置为 `false` 并防止引发异常。  
  
## <a name="see-also"></a>请参阅

- [控件](index.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
