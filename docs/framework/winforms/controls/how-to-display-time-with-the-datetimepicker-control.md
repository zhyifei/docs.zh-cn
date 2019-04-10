---
title: 如何：使用 DateTimePicker 控件显示时间
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: 7906811d5a324ba3f2bd73cc057298e007ac311b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329851"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="d0d1d-102">如何：使用 DateTimePicker 控件显示时间</span><span class="sxs-lookup"><span data-stu-id="d0d1d-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="d0d1d-103">如果希望应用程序能够使用户选择日期和时间，并以指定的格式显示该日期和时间，请使用 <xref:System.Windows.Forms.DateTimePicker> 控件。</span><span class="sxs-lookup"><span data-stu-id="d0d1d-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="d0d1d-104">以下的过程说明如何使用 <xref:System.Windows.Forms.DateTimePicker> 控件来显示时间。</span><span class="sxs-lookup"><span data-stu-id="d0d1d-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="d0d1d-105">使用 DateTimePicker 控件来显示时间</span><span class="sxs-lookup"><span data-stu-id="d0d1d-105">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="d0d1d-106">设置<xref:System.Windows.Forms.DateTimePicker.Format%2A>属性</span><span class="sxs-lookup"><span data-stu-id="d0d1d-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to</span></span> <xref:System.Windows.Forms.DateTimePickerFormat.Time>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="d0d1d-107">将 <xref:System.Windows.Forms.DateTimePicker> 的 <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="d0d1d-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="d0d1d-108">示例</span><span class="sxs-lookup"><span data-stu-id="d0d1d-108">Example</span></span>  
 <span data-ttu-id="d0d1d-109">以下代码示例演示如何创建 <xref:System.Windows.Forms.DateTimePicker>，使用户可以仅选择时间。</span><span class="sxs-lookup"><span data-stu-id="d0d1d-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0d1d-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="d0d1d-110">Compiling the Code</span></span>  
 <span data-ttu-id="d0d1d-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d0d1d-111">This example requires:</span></span>  
  
-   <span data-ttu-id="d0d1d-112">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d0d1d-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d0d1d-113">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="d0d1d-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d0d1d-114">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="d0d1d-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d1d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0d1d-115">See also</span></span>

- [<span data-ttu-id="d0d1d-116">DateTimePicker 控件</span><span class="sxs-lookup"><span data-stu-id="d0d1d-116">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
