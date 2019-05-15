---
title: 如何：在 Windows 窗体 DataGridView 单元格中托管控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 20b9f33b31df9145205a13b8649153e51d840a6c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592440"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="f210b-102">如何：在 Windows 窗体 DataGridView 单元格中托管控件</span><span class="sxs-lookup"><span data-stu-id="f210b-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="f210b-103"><xref:System.Windows.Forms.DataGridView> 控件提供了几种列类型，使用户能够以多种方式输入和编辑值。</span><span class="sxs-lookup"><span data-stu-id="f210b-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="f210b-104">但是如果这些列类型无法满足数据录入的需求，可以自主创建带有承载所选控件的单元格的列类型。</span><span class="sxs-lookup"><span data-stu-id="f210b-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="f210b-105">为此，必须定义派生自 <xref:System.Windows.Forms.DataGridViewColumn> 和 <xref:System.Windows.Forms.DataGridViewCell> 的类。</span><span class="sxs-lookup"><span data-stu-id="f210b-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="f210b-106">还必须定义派生自 <xref:System.Windows.Forms.Control> 的类并实现 <xref:System.Windows.Forms.IDataGridViewEditingControl> 接口。</span><span class="sxs-lookup"><span data-stu-id="f210b-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="f210b-107">下面的代码示例演示如何创建日历列。</span><span class="sxs-lookup"><span data-stu-id="f210b-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="f210b-108">此列的单元格将显示普通的文本框单元格中的日期，但当用户编辑单元格时，将出现 <xref:System.Windows.Forms.DateTimePicker> 控件。</span><span class="sxs-lookup"><span data-stu-id="f210b-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="f210b-109">为了避免再次实现文本框显示功能，`CalendarCell` 类会从 <xref:System.Windows.Forms.DataGridViewTextBoxCell> 类派生，而不是直接继承 <xref:System.Windows.Forms.DataGridViewCell> 类。</span><span class="sxs-lookup"><span data-stu-id="f210b-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f210b-110">当从 <xref:System.Windows.Forms.DataGridViewCell> 或 <xref:System.Windows.Forms.DataGridViewColumn> 进行派生并将新属性添加到派生的类时，请确保重写 `Clone` 方法以在克隆操作过程中复制新属性。</span><span class="sxs-lookup"><span data-stu-id="f210b-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="f210b-111">还应调用基类的 `Clone` 方法，以便将基类的属性复制到新的单元格或列。</span><span class="sxs-lookup"><span data-stu-id="f210b-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f210b-112">示例</span><span class="sxs-lookup"><span data-stu-id="f210b-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f210b-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="f210b-113">Compiling the Code</span></span>  
 <span data-ttu-id="f210b-114">以下示例需要：</span><span class="sxs-lookup"><span data-stu-id="f210b-114">The following example requires:</span></span>  
  
- <span data-ttu-id="f210b-115">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f210b-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f210b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f210b-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [<span data-ttu-id="f210b-117">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="f210b-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f210b-118">DataGridView 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="f210b-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="f210b-119">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="f210b-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
