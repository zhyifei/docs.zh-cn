---
title: 调整 Windows 窗体 DataGridView 控件中列和行的大小
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: e1fa2d57cfb2cd374d691fe03a0e0bdbd3ad7141
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138107"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4de77-102">调整 Windows 窗体 DataGridView 控件中列和行的大小</span><span class="sxs-lookup"><span data-stu-id="4de77-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4de77-103">`DataGridView`控件提供了许多选项用于自定义其列和行的大小调整行为。</span><span class="sxs-lookup"><span data-stu-id="4de77-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="4de77-104">通常情况下，`DataGridView`单元格不调整大小基于其内容。</span><span class="sxs-lookup"><span data-stu-id="4de77-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="4de77-105">相反，它们会剪辑任何大于该单元格的显示值。</span><span class="sxs-lookup"><span data-stu-id="4de77-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="4de77-106">如果内容可以显示为一个字符串，该单元格工具提示中显示它。</span><span class="sxs-lookup"><span data-stu-id="4de77-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="4de77-107">默认情况下，用户可以拖动行、 列和标头上，以显示详细信息的分隔线。</span><span class="sxs-lookup"><span data-stu-id="4de77-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="4de77-108">用户也可双击分隔条可以自动调整大小以适应内容的相关联的行、 列或标头带区。</span><span class="sxs-lookup"><span data-stu-id="4de77-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="4de77-109">`DataGridView`控件提供属性、 方法和事件，使你能够自定义或禁用所有用户定向行为。</span><span class="sxs-lookup"><span data-stu-id="4de77-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="4de77-110">此外，可以以编程方式调整大小的行、 列和标头以适应其内容，也可以配置它们时更改其内容自动调整自身大小。</span><span class="sxs-lookup"><span data-stu-id="4de77-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="4de77-111">此外可以配置要自动将你指定的比例中的控件的可用宽度的列。</span><span class="sxs-lookup"><span data-stu-id="4de77-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4de77-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="4de77-112">In This Section</span></span>  
 [<span data-ttu-id="4de77-113">Windows 窗体 DataGridView 控件中的大小调整选项</span><span class="sxs-lookup"><span data-stu-id="4de77-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4de77-114">介绍了用于调整行、 列和标头。</span><span class="sxs-lookup"><span data-stu-id="4de77-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="4de77-115">此外提供了详细信息与大小相关的属性和方法，并描述了常见使用方案。</span><span class="sxs-lookup"><span data-stu-id="4de77-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="4de77-116">Windows 窗体 DataGridView 控件中的列填充模式</span><span class="sxs-lookup"><span data-stu-id="4de77-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4de77-117">描述列填充模式中详细信息，并提供可用来试用列填充模式和其他模式的演示代码。</span><span class="sxs-lookup"><span data-stu-id="4de77-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="4de77-118">如何：设置 Windows 窗体 DataGridView 控件的大小调整模式</span><span class="sxs-lookup"><span data-stu-id="4de77-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4de77-119">介绍如何为常见用途配置的大小调整模式。</span><span class="sxs-lookup"><span data-stu-id="4de77-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="4de77-120">如何：以编程方式调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容</span><span class="sxs-lookup"><span data-stu-id="4de77-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="4de77-121">提供可用于试验以编程方式调整大小的演示代码。</span><span class="sxs-lookup"><span data-stu-id="4de77-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="4de77-122">如何：自动调整单元格的大小来适应 Windows 窗体 DataGridView 控件中的内容变化</span><span class="sxs-lookup"><span data-stu-id="4de77-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="4de77-123">提供可用于试验自动调整大小模式的演示代码。</span><span class="sxs-lookup"><span data-stu-id="4de77-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4de77-124">参考</span><span class="sxs-lookup"><span data-stu-id="4de77-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="4de77-125">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="4de77-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de77-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="4de77-126">See also</span></span>

- [<span data-ttu-id="4de77-127">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="4de77-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
