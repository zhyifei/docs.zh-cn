---
title: 调整 Windows 窗体 DataGridView 控件中列和行的大小
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 1e501d124ccec749537d319b992c5caf00b025f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536950"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="bd033-102">调整 Windows 窗体 DataGridView 控件中列和行的大小</span><span class="sxs-lookup"><span data-stu-id="bd033-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bd033-103">`DataGridView`控件提供许多选项用于自定义其列和行的大小调整行为。</span><span class="sxs-lookup"><span data-stu-id="bd033-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="bd033-104">通常情况下，`DataGridView`单元格，不要调整大小基于其内容。</span><span class="sxs-lookup"><span data-stu-id="bd033-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="bd033-105">相反，它们剪切任何大于单元格的显示值。</span><span class="sxs-lookup"><span data-stu-id="bd033-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="bd033-106">如果内容可以显示为一个字符串，该单元格在工具提示中显示它。</span><span class="sxs-lookup"><span data-stu-id="bd033-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="bd033-107">默认情况下，用户可以拖动行、 列和标头使用鼠标以显示详细信息的分隔线。</span><span class="sxs-lookup"><span data-stu-id="bd033-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="bd033-108">用户还可以双击分隔符以自动调整大小以适应内容的关联的行、 列或标头带区。</span><span class="sxs-lookup"><span data-stu-id="bd033-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="bd033-109">`DataGridView`控件提供属性、 方法和事件，您可以自定义或禁用所有这些用户重定向的行为。</span><span class="sxs-lookup"><span data-stu-id="bd033-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="bd033-110">此外，可以以编程方式调整大小的行、 列和标头以适应其内容，或你可以将它们配置为自动调整自身大小，其内容更改时。</span><span class="sxs-lookup"><span data-stu-id="bd033-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="bd033-111">你还可以配置将自动在你指定的比例控件的可用宽度的列。</span><span class="sxs-lookup"><span data-stu-id="bd033-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd033-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="bd033-112">In This Section</span></span>  
 [<span data-ttu-id="bd033-113">Windows 窗体 DataGridView 控件中的重设大小选项</span><span class="sxs-lookup"><span data-stu-id="bd033-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bd033-114">介绍有关大小调整行、 列和标头的选项。</span><span class="sxs-lookup"><span data-stu-id="bd033-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="bd033-115">此外提供大小调整相关属性和方法，有关详细信息，并描述了常见使用方案。</span><span class="sxs-lookup"><span data-stu-id="bd033-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="bd033-116">Windows 窗体 DataGridView 控件中的列填充模式</span><span class="sxs-lookup"><span data-stu-id="bd033-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bd033-117">描述列填充模式中的详细信息，并提供可用于体验列填充模式和其他模式的演示代码。</span><span class="sxs-lookup"><span data-stu-id="bd033-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="bd033-118">如何：设置 Windows 窗体 DataGridView 控件的重设大小模式</span><span class="sxs-lookup"><span data-stu-id="bd033-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="bd033-119">描述如何为常见用途配置的大小调整模式。</span><span class="sxs-lookup"><span data-stu-id="bd033-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="bd033-120">如何：以编程方式重设单元格大小以适应 Windows 窗体 DataGridView 控件中的内容</span><span class="sxs-lookup"><span data-stu-id="bd033-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="bd033-121">提供可用于试验以编程方式调整大小的演示代码。</span><span class="sxs-lookup"><span data-stu-id="bd033-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="bd033-122">如何：在 Windows 窗体 DataGridView 控件中的内容发生变化时自动重设单元格大小</span><span class="sxs-lookup"><span data-stu-id="bd033-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="bd033-123">提供可用于试验自动调整大小模式的演示代码。</span><span class="sxs-lookup"><span data-stu-id="bd033-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bd033-124">参考</span><span class="sxs-lookup"><span data-stu-id="bd033-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="bd033-125">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="bd033-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd033-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd033-126">See Also</span></span>  
 [<span data-ttu-id="bd033-127">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="bd033-127">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
