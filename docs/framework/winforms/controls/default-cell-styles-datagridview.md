---
title: "如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 28f81efa3d9f63127ad9748aaba9ce3483246a69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="00ea4-102">如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式</span><span class="sxs-lookup"><span data-stu-id="00ea4-102">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="00ea4-103"><xref:System.Windows.Forms.DataGridView>控制可用于指定默认单元格样式和单元格为整个控件、 特定列的、 行和列标题和为交替行创建帐目型效果的数据格式。</span><span class="sxs-lookup"><span data-stu-id="00ea4-103">The <xref:System.Windows.Forms.DataGridView> control lets you specify default cell styles and cell data formats for the entire control, for specific columns, for row and column headers, and for alternating rows to create a ledger effect.</span></span> <span data-ttu-id="00ea4-104">设置整个控件的默认样式中被重写默认列和交替行样式设置中。</span><span class="sxs-lookup"><span data-stu-id="00ea4-104">Default styles set for the entire control are overridden by default styles set for columns and alternating rows.</span></span> <span data-ttu-id="00ea4-105">此外，在单独的行和单元格的代码中设置的样式重写默认样式。</span><span class="sxs-lookup"><span data-stu-id="00ea4-105">Additionally, styles that you set in code for individual rows and cells override the default styles.</span></span>  
  
 <span data-ttu-id="00ea4-106">单元格样式有关的详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea4-106">For more information about cell styles, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="00ea4-107">若要设置交替行样式，请参阅[如何： 设置 Windows 窗体 DataGridView 控件使用设计器交替行样式](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea4-107">To set styles for alternating rows, see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="00ea4-108">你还可以设置使用的样式<xref:System.Windows.Forms.DataGridView.RowTemplate%2A>属性以影响将添加到控件的所有行。</span><span class="sxs-lookup"><span data-stu-id="00ea4-108">You can also set styles using the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property to affect all rows that will be added to the control.</span></span> <span data-ttu-id="00ea4-109">有关行模板的详细信息，请参阅[如何： 在 Windows 窗体 DataGridView 控件中使用行模板自定义行](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea4-109">For more information about the row template, see [How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).</span></span>  
  
 <span data-ttu-id="00ea4-110">下面的过程要求**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="00ea4-110">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="00ea4-111">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="00ea4-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00ea4-112">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="00ea4-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="00ea4-113">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="00ea4-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="00ea4-114">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="00ea4-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a><span data-ttu-id="00ea4-115">若要设置控件中的所有单元格的默认样式</span><span class="sxs-lookup"><span data-stu-id="00ea4-115">To set default styles for all cells in the control</span></span>  
  
1.  <span data-ttu-id="00ea4-116">选择<xref:System.Windows.Forms.DataGridView>设计器中的控件。</span><span class="sxs-lookup"><span data-stu-id="00ea4-116">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>  
  
2.  <span data-ttu-id="00ea4-117">在**属性**窗口中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>， <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>，或<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="00ea4-117">In the **Properties** window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property.</span></span> <span data-ttu-id="00ea4-118">**CellStyle 生成器**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="00ea4-118">The **CellStyle Builder** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="00ea4-119">通过设置属性，请使用定义样式**预览**窗格中，以确认你的选择。</span><span class="sxs-lookup"><span data-stu-id="00ea4-119">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00ea4-120">如果启用了可视样式，行和列标题 (除<xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) 样式将自动由当前的主题中，重写<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>和<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性值。</span><span class="sxs-lookup"><span data-stu-id="00ea4-120">If visual styles are enabled, the row and column headers (except for the <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) are automatically styled by the current theme, overriding the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property values.</span></span>  
>   
>  <span data-ttu-id="00ea4-121">你可以设置为多个选定的单元格样式<xref:System.Windows.Forms.DataGridView>控制使用设计器中的，但仅，如果它们具有你想要修改的单元格样式属性的相同值。</span><span class="sxs-lookup"><span data-stu-id="00ea4-121">You can set cell styles for multiple selected <xref:System.Windows.Forms.DataGridView> controls using the designer, but only if they have identical values for the cell style property you want to modify.</span></span> <span data-ttu-id="00ea4-122">如果任何单元格样式不同于该属性，**属性**的 windows **CellStyle 生成器**对话框中将为空。</span><span class="sxs-lookup"><span data-stu-id="00ea4-122">If any cell styles differ for that property, the **Properties** windows of the **CellStyle Builder** dialog box will be blank.</span></span>  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a><span data-ttu-id="00ea4-123">在单个列中设置单元格的默认样式</span><span class="sxs-lookup"><span data-stu-id="00ea4-123">To set default styles for cells in individual columns</span></span>  
  
1.  <span data-ttu-id="00ea4-124">右键单击<xref:System.Windows.Forms.DataGridView>控制在设计器并选择**编辑列**。</span><span class="sxs-lookup"><span data-stu-id="00ea4-124">Right-click the <xref:System.Windows.Forms.DataGridView> control in the designer and choose **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="00ea4-125">选择从列**选定的列**列表。</span><span class="sxs-lookup"><span data-stu-id="00ea4-125">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="00ea4-126">在**列属性**网格中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="00ea4-126">In the **Column Properties** grid, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="00ea4-127">**CellStyle 生成器**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="00ea4-127">The **CellStyle Builder** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="00ea4-128">通过设置属性，请使用定义样式**预览**窗格中，以确认你的选择。</span><span class="sxs-lookup"><span data-stu-id="00ea4-128">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>  
  
### <a name="to-format-data-in-cells"></a><span data-ttu-id="00ea4-129">若要设置单元格中的数据的格式</span><span class="sxs-lookup"><span data-stu-id="00ea4-129">To format data in cells</span></span>  
  
1.  <span data-ttu-id="00ea4-130">使用前面的过程之一来显示**CellStyle 生成器**对话框相关的默认单元格样式属性。</span><span class="sxs-lookup"><span data-stu-id="00ea4-130">Use one of the preceding procedures to display a **CellStyle Builder** dialog box related to a default cell style property.</span></span>  
  
2.  <span data-ttu-id="00ea4-131">在**CellStyle 生成器**对话框框中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="00ea4-131">In the **CellStyle Builder** dialog box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property.</span></span> <span data-ttu-id="00ea4-132">**格式字符串**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="00ea4-132">The **Format String** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="00ea4-133">选择一个格式类型，然后修改的类型 （例如要显示的小数位数） 的详细信息使用**示例**框以确认你的选择。</span><span class="sxs-lookup"><span data-stu-id="00ea4-133">Select a format type, then modify the details of the type (such as the number of decimal places to display), using the **Sample** box to confirm your choices.</span></span>  
  
4.  <span data-ttu-id="00ea4-134">如果你正在绑定<xref:System.Windows.Forms.DataGridView>控件添加到数据源都可能包含 null 值、 填写**Null 值**文本框。</span><span class="sxs-lookup"><span data-stu-id="00ea4-134">If you are binding the <xref:System.Windows.Forms.DataGridView> control to a data source that is likely to contain null values, fill in the **Null Value** text box.</span></span> <span data-ttu-id="00ea4-135">此值将显示当单元格的值等于空引用 (`Nothing`在 Visual Basic 中) 或<xref:System.DBNull.Value?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="00ea4-135">This value is displayed when the cell value is equal to a null reference (`Nothing` in Visual Basic) or <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ea4-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00ea4-136">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="00ea4-137">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="00ea4-137">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="00ea4-138">如何：使用设计器设置 Windows 窗体 DataGridView 控件的交替行样式</span><span class="sxs-lookup"><span data-stu-id="00ea4-138">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="00ea4-139">如何： 创建 Windows 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="00ea4-139">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="00ea4-140">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="00ea4-140">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
