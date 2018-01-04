---
title: "如何：在 Windows 窗体 DataGridView 单元格中承载控件"
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
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dbd315b5980c0aed222c9576632064ea9f7b2ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="c25e2-102">如何：在 Windows 窗体 DataGridView 单元格中承载控件</span><span class="sxs-lookup"><span data-stu-id="c25e2-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="c25e2-103"><xref:System.Windows.Forms.DataGridView> 控件提供了几种列类型，使用户能够以多种方式输入和编辑值。</span><span class="sxs-lookup"><span data-stu-id="c25e2-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="c25e2-104">但是如果这些列类型无法满足数据录入的需求，可以自主创建带有承载所选控件的单元格的列类型。</span><span class="sxs-lookup"><span data-stu-id="c25e2-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="c25e2-105">为此，必须定义派生自 <xref:System.Windows.Forms.DataGridViewColumn> 和 <xref:System.Windows.Forms.DataGridViewCell> 的类。</span><span class="sxs-lookup"><span data-stu-id="c25e2-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="c25e2-106">还必须定义派生自 <xref:System.Windows.Forms.Control> 的类并实现 <xref:System.Windows.Forms.IDataGridViewEditingControl> 接口。</span><span class="sxs-lookup"><span data-stu-id="c25e2-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="c25e2-107">下面的代码示例演示如何创建日历列。</span><span class="sxs-lookup"><span data-stu-id="c25e2-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="c25e2-108">此列的单元格将显示普通的文本框单元格中的日期，但当用户编辑单元格时，将出现 <xref:System.Windows.Forms.DateTimePicker> 控件。</span><span class="sxs-lookup"><span data-stu-id="c25e2-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="c25e2-109">为了避免再次实现文本框显示功能，`CalendarCell` 类会从 <xref:System.Windows.Forms.DataGridViewTextBoxCell> 类派生，而不是直接继承 <xref:System.Windows.Forms.DataGridViewCell> 类。</span><span class="sxs-lookup"><span data-stu-id="c25e2-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c25e2-110">当从 <xref:System.Windows.Forms.DataGridViewCell> 或 <xref:System.Windows.Forms.DataGridViewColumn> 进行派生并将新属性添加到派生的类时，请确保重写 `Clone` 方法以在克隆操作过程中复制新属性。</span><span class="sxs-lookup"><span data-stu-id="c25e2-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="c25e2-111">还应调用基类的 `Clone` 方法，以便将基类的属性复制到新的单元格或列。</span><span class="sxs-lookup"><span data-stu-id="c25e2-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c25e2-112">示例</span><span class="sxs-lookup"><span data-stu-id="c25e2-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c25e2-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="c25e2-113">Compiling the Code</span></span>  
 <span data-ttu-id="c25e2-114">以下示例需要：</span><span class="sxs-lookup"><span data-stu-id="c25e2-114">The following example requires:</span></span>  
  
-   <span data-ttu-id="c25e2-115">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="c25e2-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c25e2-116">有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="c25e2-116">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c25e2-117">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="c25e2-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="c25e2-118">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="c25e2-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c25e2-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c25e2-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <xref:System.Windows.Forms.DateTimePicker>  
 [<span data-ttu-id="c25e2-120">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="c25e2-120">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="c25e2-121">DataGridView 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="c25e2-121">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [<span data-ttu-id="c25e2-122">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="c25e2-122">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
