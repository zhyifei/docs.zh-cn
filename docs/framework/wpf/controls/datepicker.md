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
ms.workload: dotnet
ms.openlocfilehash: bd2a1755ae076369661b2c9a7a2b744961cdb129
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="datepicker"></a>DatePicker
<xref:System.Windows.Controls.DatePicker>控件允许用户通过中键入文本字段或使用下拉列表选择一个日期<xref:System.Windows.Controls.Calendar>控件。  
  
 下图显示<xref:System.Windows.Controls.DatePicker>。  
  
 ![DatePicker 控件](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")  
DatePicker 控件  
  
 许多<xref:System.Windows.Controls.DatePicker>控件的属性是用于管理其内置<xref:System.Windows.Controls.Calendar>，和相同函数中的等效属性<xref:System.Windows.Controls.Calendar>。 具体而言， <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>， <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>，和<xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType>属性完全相同函数其<xref:System.Windows.Controls.Calendar>对应项。 有关详细信息，请参阅<xref:System.Windows.Controls.Calendar>。  
  
 用户可以直接在文本字段，该设置字段中键入日期<xref:System.Windows.Controls.DatePicker.Text%2A>属性。 如果<xref:System.Windows.Controls.DatePicker>无法将输入的字符串转换为有效日期，<xref:System.Windows.Controls.DatePicker.DateValidationError>将引发事件。 默认情况下，这会导致异常，但的事件处理程序<xref:System.Windows.Controls.DatePicker.DateValidationError>可以设置<xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A>属性`false`和阻止引发异常。  
  
## <a name="see-also"></a>请参阅  
 [控件](../../../../docs/framework/wpf/controls/index.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)
