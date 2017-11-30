---
title: "如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期"
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
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b92fec7565aad2a881f714f9232eae10bf7633c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="e2b47-102">如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期</span><span class="sxs-lookup"><span data-stu-id="e2b47-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="e2b47-103">Windows 窗体<xref:System.Windows.Forms.DateTimePicker>控件使您可以灵活地设置日期和时间控件中的显示格式。</span><span class="sxs-lookup"><span data-stu-id="e2b47-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="e2b47-104"><xref:System.Windows.Forms.DateTimePicker.Format%2A>属性允许你选择从预定义的格式，列入<xref:System.Windows.Forms.DateTimePickerFormat>。</span><span class="sxs-lookup"><span data-stu-id="e2b47-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="e2b47-105">如果这些都足以满足你的用途，则可以创建使用格式字符中列出你自己的格式样式<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>。</span><span class="sxs-lookup"><span data-stu-id="e2b47-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="e2b47-106">若要显示自定义格式</span><span class="sxs-lookup"><span data-stu-id="e2b47-106">To display a custom format</span></span>  
  
1.  <span data-ttu-id="e2b47-107">将 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 属性设置为 `DateTimePickerFormat.Custom`。</span><span class="sxs-lookup"><span data-stu-id="e2b47-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2.  <span data-ttu-id="e2b47-108">设置<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>到一个格式字符串的属性。</span><span class="sxs-lookup"><span data-stu-id="e2b47-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="e2b47-109">将文本添加到的格式化值</span><span class="sxs-lookup"><span data-stu-id="e2b47-109">To add text to the formatted value</span></span>  
  
1.  <span data-ttu-id="e2b47-110">使用单引号括起来的格式字符，如"M"） 或分隔符 （如不是任何字符":"。</span><span class="sxs-lookup"><span data-stu-id="e2b47-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="e2b47-111">例如，下面的格式字符串显示当前日期，以格式"现在是： 05:30:31 2012 年 3 月 2 日，星期五"英语 （美国） 区域性。</span><span class="sxs-lookup"><span data-stu-id="e2b47-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     <span data-ttu-id="e2b47-112">根据区域性设置中，任何未括在单引号字符可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="e2b47-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="e2b47-113">例如，上面的格式字符串显示当前日期，以格式"现在是： 05:30:31 2012 年 3 月 2 日，星期五"英语 （美国） 区域性。</span><span class="sxs-lookup"><span data-stu-id="e2b47-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="e2b47-114">请注意，将第一个冒号括在单引号中，因为它不应为分隔字符，因为它处于"hh: mm:"。</span><span class="sxs-lookup"><span data-stu-id="e2b47-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="e2b47-115">在另一个区域性格式可能显示为"现在是： 05.30.31 2012 年 3 月 2 日，星期五"。</span><span class="sxs-lookup"><span data-stu-id="e2b47-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b47-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2b47-116">See Also</span></span>  
 [<span data-ttu-id="e2b47-117">DateTimePicker 控件</span><span class="sxs-lookup"><span data-stu-id="e2b47-117">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [<span data-ttu-id="e2b47-118">如何：使用 Windows 窗体 DateTimePicker 控件设置和返回日期</span><span class="sxs-lookup"><span data-stu-id="e2b47-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
