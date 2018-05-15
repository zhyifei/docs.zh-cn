---
title: Windows 窗体 DataGridView 控件中的基本列、行和单元格功能
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 3d6a44dce7dfd59d484d1a3495982a0d7d1f3e46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5c998-102">Windows 窗体 DataGridView 控件中的基本列、行和单元格功能</span><span class="sxs-lookup"><span data-stu-id="5c998-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5c998-103">许多基本行为`DataGridView`单元格、 行和列可以修改通过设置单个属性。</span><span class="sxs-lookup"><span data-stu-id="5c998-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="5c998-104">本部分中的主题介绍几个最常使用的这些功能。</span><span class="sxs-lookup"><span data-stu-id="5c998-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c998-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="5c998-105">In This Section</span></span>  
 [<span data-ttu-id="5c998-106">如何：在 Windows 窗体 DataGridView 控件中隐藏列</span><span class="sxs-lookup"><span data-stu-id="5c998-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5c998-107">描述如何禁止出现在控件中的特定列。</span><span class="sxs-lookup"><span data-stu-id="5c998-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="5c998-108">如何：在 Windows 窗体 DataGridView 控件中隐藏列标题</span><span class="sxs-lookup"><span data-stu-id="5c998-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5c998-109">描述如何防止出现在控件中列标题。</span><span class="sxs-lookup"><span data-stu-id="5c998-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="5c998-110">如何：在 Windows 窗体 DataGridView 控件中启用列重新排序</span><span class="sxs-lookup"><span data-stu-id="5c998-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5c998-111">描述如何使用户能够重新排列控件中的列。</span><span class="sxs-lookup"><span data-stu-id="5c998-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="5c998-112">如何：在 Windows 窗体 DataGridView 控件中冻结列</span><span class="sxs-lookup"><span data-stu-id="5c998-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5c998-113">描述如何防止一个或多个相邻的列滚动。</span><span class="sxs-lookup"><span data-stu-id="5c998-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="5c998-114">如何：在 Windows 窗体 DataGridView 控件中将列设为只读</span><span class="sxs-lookup"><span data-stu-id="5c998-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5c998-115">描述如何阻止用户编辑控件中的特定列。</span><span class="sxs-lookup"><span data-stu-id="5c998-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="5c998-116">如何：防止在 Windows 窗体 DataGridView 控件中添加和删除行</span><span class="sxs-lookup"><span data-stu-id="5c998-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="5c998-117">描述如何删除底部的控件，以防止用户添加行的新记录所在行。</span><span class="sxs-lookup"><span data-stu-id="5c998-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="5c998-118">此外描述如何阻止用户删除行。</span><span class="sxs-lookup"><span data-stu-id="5c998-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="5c998-119">如何：在 Windows 窗体 DataGridView 控件中获取和设置当前单元格</span><span class="sxs-lookup"><span data-stu-id="5c998-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="5c998-120">介绍如何访问当前在控件中具有焦点的单元格。</span><span class="sxs-lookup"><span data-stu-id="5c998-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="5c998-121">如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像</span><span class="sxs-lookup"><span data-stu-id="5c998-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5c998-122">描述如何创建在每个单元格显示一个图标的图像列。</span><span class="sxs-lookup"><span data-stu-id="5c998-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5c998-123">参考</span><span class="sxs-lookup"><span data-stu-id="5c998-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="5c998-124">提供控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="5c998-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5c998-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="5c998-125">Related Sections</span></span>  
 [<span data-ttu-id="5c998-126">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="5c998-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="5c998-127">提供一些主题，描述如何修改该控件的基本外观和单元数据的显示格式。</span><span class="sxs-lookup"><span data-stu-id="5c998-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="5c998-128">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="5c998-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="5c998-129">提供一些主题，介绍如何使用单元格、行和列对象进行编程。</span><span class="sxs-lookup"><span data-stu-id="5c998-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c998-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c998-130">See Also</span></span>  
 [<span data-ttu-id="5c998-131">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="5c998-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="5c998-132">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="5c998-132">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
