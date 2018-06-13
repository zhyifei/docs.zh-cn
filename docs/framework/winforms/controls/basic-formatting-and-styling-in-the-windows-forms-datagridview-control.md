---
title: Windows 窗体 DataGridView 控件中的基本格式设置和样式设置
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d38620c321fb12b9f489fd086e222b7780337ab3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528790"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a879c-102">Windows 窗体 DataGridView 控件中的基本格式设置和样式设置</span><span class="sxs-lookup"><span data-stu-id="a879c-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a879c-103">`DataGridView`控件，可以轻松定义单元格的基本外观和单元格的值的显示格式。</span><span class="sxs-lookup"><span data-stu-id="a879c-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="a879c-104">你可以定义外观和格式设置样式各个单元格、 行和特定列中的单元格或控件中的所有单元格通过设置的属性`DataGridViewCellStyle`通过各种访问的对象`DataGridView`控件属性。</span><span class="sxs-lookup"><span data-stu-id="a879c-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="a879c-105">此外，你可以修改这些动态基于通过处理的单元格的值等因素的样式`CellFormatting`事件。</span><span class="sxs-lookup"><span data-stu-id="a879c-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a879c-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="a879c-106">In This Section</span></span>  
 [<span data-ttu-id="a879c-107">如何：在 Windows 窗体 DataGridView 控件中更改边框和网格线的样式</span><span class="sxs-lookup"><span data-stu-id="a879c-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="a879c-108">描述如何设置`DataGridView`定义控件边框和单元格之间的边界行的外观的属性。</span><span class="sxs-lookup"><span data-stu-id="a879c-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="a879c-109">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="a879c-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a879c-110">描述`DataGridViewCellStyle`类以及该类型的属性交互的方式来定义单元格控件中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="a879c-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="a879c-111">如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式</span><span class="sxs-lookup"><span data-stu-id="a879c-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a879c-112">介绍如何使用`DataGridViewCellStyle`属性，以在特定行和列和整个控件中定义单元格的默认外观。</span><span class="sxs-lookup"><span data-stu-id="a879c-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="a879c-113">如何：在 Windows 窗体 DataGridView 控件中设置数据格式</span><span class="sxs-lookup"><span data-stu-id="a879c-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a879c-114">描述如何设置格式使用的单元格显示值`DataGridViewCellStyle`属性。</span><span class="sxs-lookup"><span data-stu-id="a879c-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="a879c-115">如何：在 Windows 窗体 DataGridView 控件中设置字体和颜色样式</span><span class="sxs-lookup"><span data-stu-id="a879c-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a879c-116">介绍如何使用`DefaultCellStyle`属性来设置基本显示控件中的所有单元格的特征。</span><span class="sxs-lookup"><span data-stu-id="a879c-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="a879c-117">如何：设置 Windows 窗体 DataGridView 控件的交替行样式</span><span class="sxs-lookup"><span data-stu-id="a879c-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a879c-118">描述如何在使用以不同方式显示的交替行的控件中创建一个类似帐目的效果。</span><span class="sxs-lookup"><span data-stu-id="a879c-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="a879c-119">如何：使用行模板在 Windows 窗体 DataGridView 控件中自定义行</span><span class="sxs-lookup"><span data-stu-id="a879c-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="a879c-120">介绍如何使用`RowTemplate`属性来设置将用于在控件中的所有行的行属性。</span><span class="sxs-lookup"><span data-stu-id="a879c-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a879c-121">参考</span><span class="sxs-lookup"><span data-stu-id="a879c-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="a879c-122">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="a879c-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="a879c-123">提供的参考文档<xref:System.Windows.Forms.DataGridViewCellStyle>类。</span><span class="sxs-lookup"><span data-stu-id="a879c-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="a879c-124">提供的参考文档<xref:System.Windows.Forms.DataGridView.CellFormatting>事件。</span><span class="sxs-lookup"><span data-stu-id="a879c-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="a879c-125">提供的参考文档<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="a879c-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a879c-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="a879c-126">Related Sections</span></span>  
 [<span data-ttu-id="a879c-127">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="a879c-127">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="a879c-128">提供一些主题，介绍自定义绘制 <xref:System.Windows.Forms.DataGridView> 单元格和行，以及创建派生的单元、列和行类型。</span><span class="sxs-lookup"><span data-stu-id="a879c-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="a879c-129">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="a879c-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="a879c-130">提供一些主题，描述了通常使用单元格、 行和列的属性。</span><span class="sxs-lookup"><span data-stu-id="a879c-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a879c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a879c-131">See Also</span></span>  
 [<span data-ttu-id="a879c-132">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="a879c-132">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
