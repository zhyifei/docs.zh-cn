---
title: 使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], elements
- columns [Windows Forms], data grids
- cells [Windows Forms], data grids
- DataGridView control [Windows Forms], programming with grid elements
- rows [Windows Forms], data grids
ms.assetid: 0d76f7e4-4149-42c6-9118-bb37d6669dc5
ms.openlocfilehash: a32b42a63225dbd94233258a5d61c8dd4a0b728f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715403"
---
# <a name="programming-with-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="78bc0-102">使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程</span><span class="sxs-lookup"><span data-stu-id="78bc0-102">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="78bc0-103">本部分提供了演示各种涉及单元格、 行和列对象的编程任务的主题。</span><span class="sxs-lookup"><span data-stu-id="78bc0-103">This section provides topics that demonstrate various programming tasks involving cell, row, and column objects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78bc0-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="78bc0-104">In This Section</span></span>  
 [<span data-ttu-id="78bc0-105">如何：Windows 窗体 DataGridView 控件中的单个单元格添加工具提示</span><span class="sxs-lookup"><span data-stu-id="78bc0-105">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>](add-tooltips-to-individual-cells-in-a-wf-datagridview-control.md)  
 <span data-ttu-id="78bc0-106">描述如何处理<xref:System.Windows.Forms.DataGridView.CellFormatting>事件，以便为各个单元提供不同的工具提示。</span><span class="sxs-lookup"><span data-stu-id="78bc0-106">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting> event to provide different ToolTips for individual cells.</span></span>  
  
 [<span data-ttu-id="78bc0-107">如何：执行自定义操作在基于 Windows 窗体 DataGridView 控件单元格中的更改</span><span class="sxs-lookup"><span data-stu-id="78bc0-107">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>](perform-a-custom-action-based-on-changes-in-a-cell-of-a-datagrid.md)  
 <span data-ttu-id="78bc0-108">描述如何处理<xref:System.Windows.Forms.DataGridView.CellValueChanged>和<xref:System.Windows.Forms.DataGridView.CellStateChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="78bc0-108">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
 [<span data-ttu-id="78bc0-109">如何：操作 Windows 窗体 DataGridView 控件中的带区</span><span class="sxs-lookup"><span data-stu-id="78bc0-109">How to: Manipulate Bands in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-bands-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="78bc0-110">介绍如何使用类型的对象进行编程<xref:System.Windows.Forms.DataGridViewBand>，这是行和列的基类型。</span><span class="sxs-lookup"><span data-stu-id="78bc0-110">Describes how to program with objects of type <xref:System.Windows.Forms.DataGridViewBand>, which is the base type for rows and columns.</span></span>  
  
 [<span data-ttu-id="78bc0-111">如何：操作 Windows 窗体 DataGridView 控件中的行</span><span class="sxs-lookup"><span data-stu-id="78bc0-111">How to: Manipulate Rows in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="78bc0-112">介绍如何使用类型的对象进行编程`DataGridViewRow`。</span><span class="sxs-lookup"><span data-stu-id="78bc0-112">Describes how to program with objects of type `DataGridViewRow`.</span></span>  
  
 [<span data-ttu-id="78bc0-113">如何：操作 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="78bc0-113">How to: Manipulate Columns in the Windows Forms DataGridView Control</span></span>](how-to-manipulate-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="78bc0-114">介绍如何使用类型的对象进行编程`DataGridViewColumn`。</span><span class="sxs-lookup"><span data-stu-id="78bc0-114">Describes how to program with objects of type `DataGridViewColumn`.</span></span>  
  
 [<span data-ttu-id="78bc0-115">如何：使用的 Windows 窗体 DataGridView 控件中的图像列</span><span class="sxs-lookup"><span data-stu-id="78bc0-115">How to: Work with Image Columns in the Windows Forms DataGridView Control</span></span>](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="78bc0-116">介绍如何进行编程与`DataGridViewImageColumn`类。</span><span class="sxs-lookup"><span data-stu-id="78bc0-116">Describes how to program with the `DataGridViewImageColumn` class.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="78bc0-117">参考</span><span class="sxs-lookup"><span data-stu-id="78bc0-117">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="78bc0-118">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="78bc0-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="78bc0-119">为提供参考文档<xref:System.Windows.Forms.DataGridViewCell>类。</span><span class="sxs-lookup"><span data-stu-id="78bc0-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="78bc0-120">为提供参考文档<xref:System.Windows.Forms.DataGridViewRow>类。</span><span class="sxs-lookup"><span data-stu-id="78bc0-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="78bc0-121">为提供参考文档<xref:System.Windows.Forms.DataGridViewColumn>类。</span><span class="sxs-lookup"><span data-stu-id="78bc0-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="78bc0-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="78bc0-122">Related Sections</span></span>  
 [<span data-ttu-id="78bc0-123">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="78bc0-123">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="78bc0-124">提供一些主题，介绍通常使用单元格、 行和列属性。</span><span class="sxs-lookup"><span data-stu-id="78bc0-124">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78bc0-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="78bc0-125">See also</span></span>
- [<span data-ttu-id="78bc0-126">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="78bc0-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="78bc0-127">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="78bc0-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
