---
title: Windows 窗体 DataGridView 控件中的基本格式设置和样式设置
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: 3d185b93f1e040ae320afbfd3e2b010bbf9ca624
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707074"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e5034-102">Windows 窗体 DataGridView 控件中的基本格式设置和样式设置</span><span class="sxs-lookup"><span data-stu-id="e5034-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e5034-103">`DataGridView`控件，可以轻松定义单元格的基本外观和单元格的值的显示格式。</span><span class="sxs-lookup"><span data-stu-id="e5034-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="e5034-104">您可以定义外观和设置的属性的各个单元格、 行和特定列中的单元格或控件中的所有单元格格式设置样式`DataGridViewCellStyle`访问通过各种对象`DataGridView`控件属性。</span><span class="sxs-lookup"><span data-stu-id="e5034-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="e5034-105">此外，你可以修改基于动态因素，例如单元格的值通过处理这些样式`CellFormatting`事件。</span><span class="sxs-lookup"><span data-stu-id="e5034-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5034-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e5034-106">In This Section</span></span>  
 [<span data-ttu-id="e5034-107">如何：更改边框和网格线在 Windows 窗体 DataGridView 控件中的样式</span><span class="sxs-lookup"><span data-stu-id="e5034-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="e5034-108">介绍如何设置`DataGridView`属性用于定义控件边框和单元格之间的边界行的外观。</span><span class="sxs-lookup"><span data-stu-id="e5034-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="e5034-109">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="e5034-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5034-110">介绍`DataGridViewCellStyle`类和该类型的属性是如何交互以定义单元格控件中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="e5034-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="e5034-111">如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式</span><span class="sxs-lookup"><span data-stu-id="e5034-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5034-112">介绍如何使用`DataGridViewCellStyle`属性以定义单元格的默认外观和整个控件中特定行和列。</span><span class="sxs-lookup"><span data-stu-id="e5034-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="e5034-113">如何：Windows 中的数据格式窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="e5034-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5034-114">介绍了如何设置使用的单元格显示值`DataGridViewCellStyle`属性。</span><span class="sxs-lookup"><span data-stu-id="e5034-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="e5034-115">如何：在 Windows 窗体 DataGridView 控件中设置字体和颜色样式</span><span class="sxs-lookup"><span data-stu-id="e5034-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5034-116">介绍如何使用`DefaultCellStyle`要设置基本属性在控件中显示的所有单元格的特征。</span><span class="sxs-lookup"><span data-stu-id="e5034-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="e5034-117">如何：设置 Windows 窗体 DataGridView 控件的交替行样式</span><span class="sxs-lookup"><span data-stu-id="e5034-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5034-118">介绍如何使用以不同方式显示的交替行在控件中创建一个类似分类帐的效果。</span><span class="sxs-lookup"><span data-stu-id="e5034-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="e5034-119">如何：使用行模板自定义 Windows 窗体 DataGridView 控件中的行</span><span class="sxs-lookup"><span data-stu-id="e5034-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="e5034-120">介绍如何使用`RowTemplate`属性来设置将用于在控件中的所有行的行属性。</span><span class="sxs-lookup"><span data-stu-id="e5034-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e5034-121">参考</span><span class="sxs-lookup"><span data-stu-id="e5034-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="e5034-122">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="e5034-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="e5034-123">为提供参考文档<xref:System.Windows.Forms.DataGridViewCellStyle>类。</span><span class="sxs-lookup"><span data-stu-id="e5034-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="e5034-124">为提供参考文档<xref:System.Windows.Forms.DataGridView.CellFormatting>事件。</span><span class="sxs-lookup"><span data-stu-id="e5034-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="e5034-125">为提供参考文档<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e5034-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e5034-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="e5034-126">Related Sections</span></span>  
 [<span data-ttu-id="e5034-127">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="e5034-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e5034-128">提供一些主题，介绍自定义绘制 <xref:System.Windows.Forms.DataGridView> 单元格和行，以及创建派生的单元、列和行类型。</span><span class="sxs-lookup"><span data-stu-id="e5034-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="e5034-129">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="e5034-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="e5034-130">提供一些主题，介绍通常使用单元格、 行和列属性。</span><span class="sxs-lookup"><span data-stu-id="e5034-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5034-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5034-131">See also</span></span>
- [<span data-ttu-id="e5034-132">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="e5034-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
