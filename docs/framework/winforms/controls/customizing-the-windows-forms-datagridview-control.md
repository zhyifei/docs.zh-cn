---
title: 自定义 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744024"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="32cfa-102">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="32cfa-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="32cfa-103">`DataGridView` 控件提供了多个属性，这些属性可用于调整其单元格、行和列的外观和基本行为（外观和感觉）。</span><span class="sxs-lookup"><span data-stu-id="32cfa-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="32cfa-104">但是，如果您有超出 <xref:System.Windows.Forms.DataGridViewCellStyle> 类的功能的特殊需求，则还可以通过创建自定义单元、列和行来实现控件的所有者绘图或扩展其功能。</span><span class="sxs-lookup"><span data-stu-id="32cfa-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="32cfa-105">若要自行绘制单元格和行，可以处理各种 `DataGridView` 绘制事件。</span><span class="sxs-lookup"><span data-stu-id="32cfa-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="32cfa-106">若要修改现有功能或提供新功能，你可以创建自己的派生自现有 `DataGridViewCell`、`DataGridViewColumn`和 `DataGridViewRow` 类型的类型。</span><span class="sxs-lookup"><span data-stu-id="32cfa-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="32cfa-107">还可以通过创建在单元格处于编辑模式时显示所选控件的派生类型，来提供新的编辑功能。</span><span class="sxs-lookup"><span data-stu-id="32cfa-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32cfa-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="32cfa-108">In This Section</span></span>  
 [<span data-ttu-id="32cfa-109">如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观</span><span class="sxs-lookup"><span data-stu-id="32cfa-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="32cfa-110">描述如何处理 <xref:System.Windows.Forms.DataGridView.CellPainting> 事件以便手动绘制单元格。</span><span class="sxs-lookup"><span data-stu-id="32cfa-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="32cfa-111">如何：自定义 Windows 窗体 DataGridView 控件中行的外观</span><span class="sxs-lookup"><span data-stu-id="32cfa-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="32cfa-112">描述如何处理 <xref:System.Windows.Forms.DataGridView.RowPrePaint> 和 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 事件以便使用跨多个列的自定义、渐变背景和内容绘制行。</span><span class="sxs-lookup"><span data-stu-id="32cfa-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="32cfa-113">如何：通过扩展 Windows 窗体 DataGridView 控件中单元格和列的行为和外观进行自定义</span><span class="sxs-lookup"><span data-stu-id="32cfa-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="32cfa-114">介绍如何创建从 `DataGridViewCell` 和 `DataGridViewColumn` 派生的自定义类型，以便在鼠标指针停留在单元格时突出显示单元格。</span><span class="sxs-lookup"><span data-stu-id="32cfa-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="32cfa-115">如何：在 Windows 窗体 DataGridView 控件的按钮列中禁用按钮</span><span class="sxs-lookup"><span data-stu-id="32cfa-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="32cfa-116">介绍如何创建从 <xref:System.Windows.Forms.DataGridViewButtonCell> 和 <xref:System.Windows.Forms.DataGridViewButtonColumn> 派生的自定义类型，以便在按钮列中显示禁用的按钮。</span><span class="sxs-lookup"><span data-stu-id="32cfa-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="32cfa-117">如何：在 Windows 窗体 DataGridView 单元格中托管控件</span><span class="sxs-lookup"><span data-stu-id="32cfa-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="32cfa-118">描述如何实现 `IDataGridViewEditingControl` 接口，并创建从 `DataGridViewCell` 和 `DataGridViewColumn` 派生的自定义类型，以便在单元格处于编辑模式时显示 <xref:System.Windows.Forms.DateTimePicker> 控件。</span><span class="sxs-lookup"><span data-stu-id="32cfa-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="32cfa-119">引用</span><span class="sxs-lookup"><span data-stu-id="32cfa-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="32cfa-120">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="32cfa-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="32cfa-121">提供 <xref:System.Windows.Forms.DataGridViewCell> 类的参考文档。</span><span class="sxs-lookup"><span data-stu-id="32cfa-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="32cfa-122">提供 <xref:System.Windows.Forms.DataGridViewRow> 类的参考文档。</span><span class="sxs-lookup"><span data-stu-id="32cfa-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="32cfa-123">提供 <xref:System.Windows.Forms.DataGridViewColumn> 类的参考文档。</span><span class="sxs-lookup"><span data-stu-id="32cfa-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="32cfa-124">提供 <xref:System.Windows.Forms.IDataGridViewEditingControl> 接口的参考文档。</span><span class="sxs-lookup"><span data-stu-id="32cfa-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="32cfa-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="32cfa-125">Related Sections</span></span>  
 [<span data-ttu-id="32cfa-126">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="32cfa-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="32cfa-127">提供一些主题，描述如何修改该控件的基本外观和单元数据的显示格式。</span><span class="sxs-lookup"><span data-stu-id="32cfa-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32cfa-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32cfa-128">See also</span></span>

- [<span data-ttu-id="32cfa-129">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="32cfa-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="32cfa-130">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="32cfa-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
