---
title: 如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: c201455acaa9bde521afd623424d0cfc403b1bff
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705865"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="f5b69-102">如何：使用 Windows 窗体 DateTimePicker 控件以自定义格式显示日期</span><span class="sxs-lookup"><span data-stu-id="f5b69-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="f5b69-103">Windows 窗体<xref:System.Windows.Forms.DateTimePicker>控制可以让你灵活地设置日期和时间控件中的显示格式。</span><span class="sxs-lookup"><span data-stu-id="f5b69-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="f5b69-104"><xref:System.Windows.Forms.DateTimePicker.Format%2A>属性，可选择从中列出的预定义格式<xref:System.Windows.Forms.DateTimePickerFormat>。</span><span class="sxs-lookup"><span data-stu-id="f5b69-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="f5b69-105">如果这些都不能充分满足您需求，则可以创建您自己使用中列出的格式字符的格式样式<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>。</span><span class="sxs-lookup"><span data-stu-id="f5b69-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="f5b69-106">若要显示的自定义格式</span><span class="sxs-lookup"><span data-stu-id="f5b69-106">To display a custom format</span></span>  
  
1.  <span data-ttu-id="f5b69-107">将 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 属性设置为 `DateTimePickerFormat.Custom`。</span><span class="sxs-lookup"><span data-stu-id="f5b69-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2.  <span data-ttu-id="f5b69-108">设置<xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>属性设置为格式字符串。</span><span class="sxs-lookup"><span data-stu-id="f5b69-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="f5b69-109">若要将文本添加到带格式的值</span><span class="sxs-lookup"><span data-stu-id="f5b69-109">To add text to the formatted value</span></span>  
  
1.  <span data-ttu-id="f5b69-110">使用单引号括起来不像"M"的格式字符或分隔符等任何字符":"。</span><span class="sxs-lookup"><span data-stu-id="f5b69-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="f5b69-111">例如，下面的格式字符串显示当前日期，格式以"今天是：05:30:31 星期五年 3 月 02，2012"英语 （美国） 区域性中。</span><span class="sxs-lookup"><span data-stu-id="f5b69-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="f5b69-112">具体取决于的区域性设置，可能会更改任何未括在单引号内字符。</span><span class="sxs-lookup"><span data-stu-id="f5b69-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="f5b69-113">例如，上面的格式字符串显示当前日期，格式以"今天是：05:30:31 星期五年 3 月 02，2012"英语 （美国） 区域性中。</span><span class="sxs-lookup"><span data-stu-id="f5b69-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="f5b69-114">请注意，第一个冒号括在单引号中，因为它不是因为它处于"hh: mm:"为分隔字符。</span><span class="sxs-lookup"><span data-stu-id="f5b69-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="f5b69-115">在另一个区域性格式可能显示为"现在是：05.30.31 星期五年 3 月 02，2012"。</span><span class="sxs-lookup"><span data-stu-id="f5b69-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b69-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5b69-116">See also</span></span>
- [<span data-ttu-id="f5b69-117">DateTimePicker 控件</span><span class="sxs-lookup"><span data-stu-id="f5b69-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="f5b69-118">如何：使用 Windows 窗体 DateTimePicker 控件设置和返回日期</span><span class="sxs-lookup"><span data-stu-id="f5b69-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
