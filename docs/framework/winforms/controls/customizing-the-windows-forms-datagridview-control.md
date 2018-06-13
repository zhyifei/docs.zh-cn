---
title: 自定义 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 92bbace4d0869aca67025f1e4ac8c451fe073219
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529839"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="2b19a-102">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="2b19a-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2b19a-103">`DataGridView`控件提供可用于调整的外观和其单元格、 行和列的基本行为 （外观和感觉） 的多个属性。</span><span class="sxs-lookup"><span data-stu-id="2b19a-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="2b19a-104">如果你有特殊需求，超出的能力<xref:System.Windows.Forms.DataGridViewCellStyle>类中，但是，你也可以实现所有者描述控件或通过创建自定义单元格、 列和行扩展其功能。</span><span class="sxs-lookup"><span data-stu-id="2b19a-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="2b19a-105">若要绘制的单元格和行自己，可以处理各种`DataGridView`绘制事件。</span><span class="sxs-lookup"><span data-stu-id="2b19a-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="2b19a-106">若要修改现有功能或提供新功能，你可以创建您自己的类型派生自现有`DataGridViewCell`， `DataGridViewColumn`，和`DataGridViewRow`类型。</span><span class="sxs-lookup"><span data-stu-id="2b19a-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="2b19a-107">你还可以通过创建显示的单元格处于编辑模式的时你选择的控件的派生的类型中提供新的编辑功能。</span><span class="sxs-lookup"><span data-stu-id="2b19a-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b19a-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="2b19a-108">In This Section</span></span>  
 [<span data-ttu-id="2b19a-109">如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观</span><span class="sxs-lookup"><span data-stu-id="2b19a-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="2b19a-110">描述如何处理<xref:System.Windows.Forms.DataGridView.CellPainting>事件，以绘制单元格的手动。</span><span class="sxs-lookup"><span data-stu-id="2b19a-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="2b19a-111">如何：自定义 Windows 窗体 DataGridView 控件中行的外观</span><span class="sxs-lookup"><span data-stu-id="2b19a-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="2b19a-112">描述如何处理<xref:System.Windows.Forms.DataGridView.RowPrePaint>和<xref:System.Windows.Forms.DataGridView.RowPostPaint>事件绘制自定义的渐变背景的行和内容，以便跨多个列。</span><span class="sxs-lookup"><span data-stu-id="2b19a-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="2b19a-113">如何：通过扩展 Windows 窗体 DataGridView 控件中单元格和列的行为和外观进行自定义</span><span class="sxs-lookup"><span data-stu-id="2b19a-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="2b19a-114">描述如何创建自定义的类型派生自`DataGridViewCell`和`DataGridViewColumn`以便在鼠标指针停留在它们上时突出显示单元格。</span><span class="sxs-lookup"><span data-stu-id="2b19a-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="2b19a-115">如何：在 Windows 窗体 DataGridView 控件的按钮列中禁用按钮</span><span class="sxs-lookup"><span data-stu-id="2b19a-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="2b19a-116">描述如何创建自定义的类型派生自<xref:System.Windows.Forms.DataGridViewButtonCell>和<xref:System.Windows.Forms.DataGridViewButtonColumn>为了在按钮列中显示禁用的按钮。</span><span class="sxs-lookup"><span data-stu-id="2b19a-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="2b19a-117">如何：在 Windows 窗体 DataGridView 单元格中托管控件</span><span class="sxs-lookup"><span data-stu-id="2b19a-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="2b19a-118">描述如何实现`IDataGridViewEditingControl`接口以及如何创建自定义的类型派生自`DataGridViewCell`和`DataGridViewColumn`为了显示<xref:System.Windows.Forms.DateTimePicker>控制时的单元格处于编辑模式。</span><span class="sxs-lookup"><span data-stu-id="2b19a-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2b19a-119">参考</span><span class="sxs-lookup"><span data-stu-id="2b19a-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2b19a-120">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="2b19a-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="2b19a-121">提供的参考文档<xref:System.Windows.Forms.DataGridViewCell>类。</span><span class="sxs-lookup"><span data-stu-id="2b19a-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="2b19a-122">提供的参考文档<xref:System.Windows.Forms.DataGridViewRow>类。</span><span class="sxs-lookup"><span data-stu-id="2b19a-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="2b19a-123">提供的参考文档<xref:System.Windows.Forms.DataGridViewColumn>类。</span><span class="sxs-lookup"><span data-stu-id="2b19a-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="2b19a-124">提供的参考文档<xref:System.Windows.Forms.IDataGridViewEditingControl>接口。</span><span class="sxs-lookup"><span data-stu-id="2b19a-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2b19a-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="2b19a-125">Related Sections</span></span>  
 [<span data-ttu-id="2b19a-126">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="2b19a-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2b19a-127">提供一些主题，描述如何修改该控件的基本外观和单元数据的显示格式。</span><span class="sxs-lookup"><span data-stu-id="2b19a-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b19a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b19a-128">See Also</span></span>  
 [<span data-ttu-id="2b19a-129">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="2b19a-129">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="2b19a-130">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="2b19a-130">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
