---
title: 自定义 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 901b221f74fa76221ed3f19e9eb4c5f17c6534fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559549"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="3fd7f-102">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="3fd7f-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3fd7f-103">`DataGridView`控件提供了可用于调整的外观和其单元格、 行和列的基本行为 （外观和感受） 的多个属性。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="3fd7f-104">如果您有特殊需求，超出的能力<xref:System.Windows.Forms.DataGridViewCellStyle>类中，但是，还可以实现所有者描述控件或通过创建自定义单元格、 列和行来扩展其功能。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="3fd7f-105">若要绘制单元格和行自己，可以处理各种`DataGridView`绘制事件。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="3fd7f-106">若要修改现有功能，或提供了新功能，可以创建自己的类型派生自现有`DataGridViewCell`， `DataGridViewColumn`，和`DataGridViewRow`类型。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="3fd7f-107">此外可以通过创建显示控件的单元格处于编辑模式时所选的派生的类型提供新的编辑功能。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3fd7f-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="3fd7f-108">In This Section</span></span>  
 [<span data-ttu-id="3fd7f-109">如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观</span><span class="sxs-lookup"><span data-stu-id="3fd7f-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="3fd7f-110">描述如何处理<xref:System.Windows.Forms.DataGridView.CellPainting>手动事件，以绘制单元格。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="3fd7f-111">如何：自定义 Windows 窗体 DataGridView 控件中的行的外观</span><span class="sxs-lookup"><span data-stu-id="3fd7f-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="3fd7f-112">描述如何处理<xref:System.Windows.Forms.DataGridView.RowPrePaint>和<xref:System.Windows.Forms.DataGridView.RowPostPaint>事件以绘制自定义的渐变背景的行和内容的跨多个列。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="3fd7f-113">如何：通过扩展行为和外观自定义单元格和 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="3fd7f-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="3fd7f-114">介绍如何创建自定义的类型派生自`DataGridViewCell`和`DataGridViewColumn`以便当鼠标指针停留在其上突出显示的单元格。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="3fd7f-115">如何：禁用 Windows 窗体 DataGridView 控件中的按钮列中的按钮</span><span class="sxs-lookup"><span data-stu-id="3fd7f-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="3fd7f-116">介绍如何创建自定义的类型派生自<xref:System.Windows.Forms.DataGridViewButtonCell>和<xref:System.Windows.Forms.DataGridViewButtonColumn>为了在按钮列中显示禁用的按钮。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="3fd7f-117">如何：在 Windows 窗体 DataGridView 单元格中的宿主控件</span><span class="sxs-lookup"><span data-stu-id="3fd7f-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="3fd7f-118">介绍了如何实现`IDataGridViewEditingControl`接口，并创建自定义的类型派生自`DataGridViewCell`并`DataGridViewColumn`以便显示<xref:System.Windows.Forms.DateTimePicker>控件处于编辑模式时单元格。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3fd7f-119">参考</span><span class="sxs-lookup"><span data-stu-id="3fd7f-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="3fd7f-120">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="3fd7f-121">为提供参考文档<xref:System.Windows.Forms.DataGridViewCell>类。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="3fd7f-122">为提供参考文档<xref:System.Windows.Forms.DataGridViewRow>类。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="3fd7f-123">为提供参考文档<xref:System.Windows.Forms.DataGridViewColumn>类。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="3fd7f-124">为提供参考文档<xref:System.Windows.Forms.IDataGridViewEditingControl>接口。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3fd7f-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="3fd7f-125">Related Sections</span></span>  
 [<span data-ttu-id="3fd7f-126">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="3fd7f-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="3fd7f-127">提供一些主题，描述如何修改该控件的基本外观和单元数据的显示格式。</span><span class="sxs-lookup"><span data-stu-id="3fd7f-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd7f-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fd7f-128">See also</span></span>
- [<span data-ttu-id="3fd7f-129">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="3fd7f-129">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
- [<span data-ttu-id="3fd7f-130">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="3fd7f-130">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
