---
title: 如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 6d7d867b7c9e83b68589e046565bfb0199692f5f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658504"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="3d97d-102">如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式</span><span class="sxs-lookup"><span data-stu-id="3d97d-102">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="3d97d-103">使用<xref:System.Windows.Forms.DataGridView>控件, 可以为整个控件指定默认的单元格样式和单元数据格式, 对于行标题和列标题, 还可以指定用于交替行的默认单元格样式和单元数据格式。</span><span class="sxs-lookup"><span data-stu-id="3d97d-103">The <xref:System.Windows.Forms.DataGridView> control lets you specify default cell styles and cell data formats for the entire control, for specific columns, for row and column headers, and for alternating rows to create a ledger effect.</span></span> <span data-ttu-id="3d97d-104">为列和交替行设置的默认样式会重写为整个控件设置的默认样式。</span><span class="sxs-lookup"><span data-stu-id="3d97d-104">Default styles set for the entire control are overridden by default styles set for columns and alternating rows.</span></span> <span data-ttu-id="3d97d-105">此外, 在代码中为单个行和单元格设置的样式会重写默认样式。</span><span class="sxs-lookup"><span data-stu-id="3d97d-105">Additionally, styles that you set in code for individual rows and cells override the default styles.</span></span>

<span data-ttu-id="3d97d-106">有关单元格样式的详细信息, 请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="3d97d-106">For more information about cell styles, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="3d97d-107">若要为交替行设置样式, [请参阅如何:使用设计器](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)为 Windows 窗体 DataGridView 控件设置交替行样式。</span><span class="sxs-lookup"><span data-stu-id="3d97d-107">To set styles for alternating rows, see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>

<span data-ttu-id="3d97d-108">你还可以使用<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>属性设置样式, 以影响将添加到控件中的所有行。</span><span class="sxs-lookup"><span data-stu-id="3d97d-108">You can also set styles using the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property to affect all rows that will be added to the control.</span></span> <span data-ttu-id="3d97d-109">有关行模板的详细信息, 请参阅[如何:使用行模板自定义 Windows 窗体 DataGridView 控件](use-the-row-template-to-customize-rows-in-the-datagrid.md)中的行。</span><span class="sxs-lookup"><span data-stu-id="3d97d-109">For more information about the row template, see [How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control](use-the-row-template-to-customize-rows-in-the-datagrid.md).</span></span>

<span data-ttu-id="3d97d-110">下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.DataGridView>包含控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="3d97d-110">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3d97d-111">有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="3d97d-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a><span data-ttu-id="3d97d-112">设置控件中所有单元格的默认样式</span><span class="sxs-lookup"><span data-stu-id="3d97d-112">To set default styles for all cells in the control</span></span>

1. <span data-ttu-id="3d97d-113">在设计器中选择控件。<xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="3d97d-113">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="3d97d-114">在 "**属性**" 窗口![中, 单击<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>、 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>或<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性旁边的省略号按钮 (Visual Studio](./media/visual-studio-ellipsis-button.png)的属性窗口中的省略号按钮 (...)。</span><span class="sxs-lookup"><span data-stu-id="3d97d-114">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property.</span></span> <span data-ttu-id="3d97d-115">此时将显示 " **CellStyle 生成器**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="3d97d-115">The **CellStyle Builder** dialog box appears.</span></span>

3. <span data-ttu-id="3d97d-116">通过设置属性来定义样式, 并使用**预览**窗格来确认你的选择。</span><span class="sxs-lookup"><span data-stu-id="3d97d-116">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

> [!NOTE]
> <span data-ttu-id="3d97d-117">如果启用了视觉样式, 则行标题和列标题 (除外<xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) 将按当前主题自动样式, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>并覆盖和<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性值。</span><span class="sxs-lookup"><span data-stu-id="3d97d-117">If visual styles are enabled, the row and column headers (except for the <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) are automatically styled by the current theme, overriding the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property values.</span></span>
>
> <span data-ttu-id="3d97d-118">您可以使用设计器为多个<xref:System.Windows.Forms.DataGridView>选定的控件设置单元格样式, 但前提是它们对于要修改的单元格样式属性具有相同的值。</span><span class="sxs-lookup"><span data-stu-id="3d97d-118">You can set cell styles for multiple selected <xref:System.Windows.Forms.DataGridView> controls using the designer, but only if they have identical values for the cell style property you want to modify.</span></span> <span data-ttu-id="3d97d-119">如果该属性的任何单元格样式不同, 则 " **CellStyle 生成器**" 对话框的 "**属性**" 窗口将为空白。</span><span class="sxs-lookup"><span data-stu-id="3d97d-119">If any cell styles differ for that property, the **Properties** windows of the **CellStyle Builder** dialog box will be blank.</span></span>

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a><span data-ttu-id="3d97d-120">设置单个列中单元格的默认样式</span><span class="sxs-lookup"><span data-stu-id="3d97d-120">To set default styles for cells in individual columns</span></span>

1. <span data-ttu-id="3d97d-121">在设计器中<xref:System.Windows.Forms.DataGridView>右键单击控件, 然后选择 "**编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="3d97d-121">Right-click the <xref:System.Windows.Forms.DataGridView> control in the designer and choose **Edit Columns**.</span></span>

2. <span data-ttu-id="3d97d-122">从 "**选定的列**" 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="3d97d-122">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="3d97d-123">在 "**列属性**" 网格中, 单击![ <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>属性旁边的省略号按钮 (Visual Studio](./media/visual-studio-ellipsis-button.png)的属性窗口中的省略号按钮 (...)。</span><span class="sxs-lookup"><span data-stu-id="3d97d-123">In the **Column Properties** grid, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="3d97d-124">此时将显示 " **CellStyle 生成器**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="3d97d-124">The **CellStyle Builder** dialog box appears.</span></span>

4. <span data-ttu-id="3d97d-125">通过设置属性来定义样式, 并使用**预览**窗格来确认你的选择。</span><span class="sxs-lookup"><span data-stu-id="3d97d-125">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

### <a name="to-format-data-in-cells"></a><span data-ttu-id="3d97d-126">设置单元格中数据的格式</span><span class="sxs-lookup"><span data-stu-id="3d97d-126">To format data in cells</span></span>

1. <span data-ttu-id="3d97d-127">使用上述过程之一来显示与默认单元格样式属性相关的 " **CellStyle Builder** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="3d97d-127">Use one of the preceding procedures to display a **CellStyle Builder** dialog box related to a default cell style property.</span></span>

2. <span data-ttu-id="3d97d-128">在 " **CellStyle 生成器**" 对话框中, 单击![ <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>属性旁边的省略号按钮 (Visual Studio](./media/visual-studio-ellipsis-button.png)的属性窗口中的省略号按钮 (...)。</span><span class="sxs-lookup"><span data-stu-id="3d97d-128">In the **CellStyle Builder** dialog box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property.</span></span> <span data-ttu-id="3d97d-129">此时将显示 "**格式字符串**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="3d97d-129">The **Format String** dialog box appears.</span></span>

3. <span data-ttu-id="3d97d-130">选择格式类型, 然后修改类型的详细信息 (例如要显示的小数位数), 并使用**示例**框确认所做的选择。</span><span class="sxs-lookup"><span data-stu-id="3d97d-130">Select a format type, then modify the details of the type (such as the number of decimal places to display), using the **Sample** box to confirm your choices.</span></span>

4. <span data-ttu-id="3d97d-131">如果要将该<xref:System.Windows.Forms.DataGridView>控件绑定到可能包含 null 值的数据源, 请在 " **null 值**" 文本框中填充。</span><span class="sxs-lookup"><span data-stu-id="3d97d-131">If you are binding the <xref:System.Windows.Forms.DataGridView> control to a data source that is likely to contain null values, fill in the **Null Value** text box.</span></span> <span data-ttu-id="3d97d-132">当单元格值等于空引用 (`Nothing`在 Visual Basic 中) 或<xref:System.DBNull.Value?displayProperty=nameWithType>时, 将显示此值。</span><span class="sxs-lookup"><span data-stu-id="3d97d-132">This value is displayed when the cell value is equal to a null reference (`Nothing` in Visual Basic) or <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d97d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d97d-133">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3d97d-134">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="3d97d-134">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3d97d-135">如何：使用设计器为 Windows 窗体 DataGridView 控件设置交替行样式</span><span class="sxs-lookup"><span data-stu-id="3d97d-135">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="3d97d-136">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="3d97d-136">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="3d97d-137">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="3d97d-137">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
