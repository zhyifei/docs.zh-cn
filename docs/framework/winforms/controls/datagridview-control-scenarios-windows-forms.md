---
title: DataGridView 控件方案（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
ms.openlocfilehash: a320b40664e4fe2254109183731db346a5d7d0b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="datagridview-control-scenarios-windows-forms"></a><span data-ttu-id="57a19-102">DataGridView 控件方案（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="57a19-102">DataGridView Control Scenarios (Windows Forms)</span></span>
<span data-ttu-id="57a19-103">与<xref:System.Windows.Forms.DataGridView>控件，您可以显示来自各种数据源的表格数据。</span><span class="sxs-lookup"><span data-stu-id="57a19-103">With the <xref:System.Windows.Forms.DataGridView> control, you can display tabular data from a variety of data sources.</span></span> <span data-ttu-id="57a19-104">有关简单用法，则可以手动填充<xref:System.Windows.Forms.DataGridView>和操作直接通过控件的数据。</span><span class="sxs-lookup"><span data-stu-id="57a19-104">For simple uses, you can manually populate a <xref:System.Windows.Forms.DataGridView> and manipulate the data directly through the control.</span></span> <span data-ttu-id="57a19-105">通常情况下，但是，你将在外部数据源中存储你的数据并将控件绑定到它通过<xref:System.Windows.Forms.BindingSource>组件。</span><span class="sxs-lookup"><span data-stu-id="57a19-105">Typically, however, you will store your data in an external data source and bind the control to it through a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="57a19-106">本主题介绍了一些常见方案涉及<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="57a19-106">This topic describes some of the common scenarios that involve the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a><span data-ttu-id="57a19-107">方案 1： 显示少量数据</span><span class="sxs-lookup"><span data-stu-id="57a19-107">Scenario 1: Displaying Small Amounts of Data</span></span>  
 <span data-ttu-id="57a19-108">无需将你的数据存储在外部数据源，使其显示在<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="57a19-108">You do not have to store your data in an external data source to display it in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="57a19-109">如果你正在使用的少量数据，你可以自行填充控件和操作通过控件的数据。</span><span class="sxs-lookup"><span data-stu-id="57a19-109">If you are working with a small amount of data, you can populate the control yourself and manipulate the data through the control.</span></span> <span data-ttu-id="57a19-110">这称为*取消绑定的模式*。</span><span class="sxs-lookup"><span data-stu-id="57a19-110">This is called *unbound mode*.</span></span> <span data-ttu-id="57a19-111">有关详细信息，请参阅[如何： 创建未绑定的 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-111">For more information, see [How to: Create an Unbound Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="57a19-112">方案关键点</span><span class="sxs-lookup"><span data-stu-id="57a19-112">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="57a19-113">在未绑定模式下，你手动填充控件。</span><span class="sxs-lookup"><span data-stu-id="57a19-113">In unbound mode, you populate the control manually.</span></span>  
  
-   <span data-ttu-id="57a19-114">未绑定的模式是特别适用于只读数据的信息量很小。</span><span class="sxs-lookup"><span data-stu-id="57a19-114">Unbound mode is particularly suited for small amounts of read-only data.</span></span>  
  
-   <span data-ttu-id="57a19-115">取消绑定的模式也适用于类似电子表格或稀疏填充表。</span><span class="sxs-lookup"><span data-stu-id="57a19-115">Unbound mode is also suited for spreadsheet-like or sparsely populated tables.</span></span>  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a><span data-ttu-id="57a19-116">方案 2： 查看和更新的外部数据源中存储的数据</span><span class="sxs-lookup"><span data-stu-id="57a19-116">Scenario 2: Viewing and Updating Data Stored in an External Data Source</span></span>  
 <span data-ttu-id="57a19-117">你可以使用<xref:System.Windows.Forms.DataGridView>控制用户界面 (UI) 通过哪些用户可以访问数据保留在数据源，如数据库表或业务对象的集合。</span><span class="sxs-lookup"><span data-stu-id="57a19-117">You can use the <xref:System.Windows.Forms.DataGridView> control as a user interface (UI) through which users can access data kept in a data source such as a database table or a collection of business objects.</span></span> <span data-ttu-id="57a19-118">有关详细信息，请参阅[如何： 将数据绑定到 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-118">For more information, see [How to: Bind Data to the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="57a19-119">方案关键点</span><span class="sxs-lookup"><span data-stu-id="57a19-119">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="57a19-120">绑定的模式允许你连接到数据源、 自动生成基于数据源属性或数据库列的列和自动填充该控件。</span><span class="sxs-lookup"><span data-stu-id="57a19-120">Bound mode lets you connect to a data source, automatically generate columns based on the data source properties or database columns, and automatically populate the control.</span></span>  
  
-   <span data-ttu-id="57a19-121">绑定的模式适合用于与数据的大量用户交互。</span><span class="sxs-lookup"><span data-stu-id="57a19-121">Bound mode is suited for heavy user interaction with data.</span></span> <span data-ttu-id="57a19-122">数据可用于显示，格式设置和用户指定的数据可以解析为数据源的预期格式。</span><span class="sxs-lookup"><span data-stu-id="57a19-122">Data can be formatted for display, and user-specified data can be parsed into the format expected by the data source.</span></span> <span data-ttu-id="57a19-123">可以检测到格式设置错误和数据库约束错误的数据输入，以便用户可以会收到警告，并可以更正错误的单元格。</span><span class="sxs-lookup"><span data-stu-id="57a19-123">Data entry formatting errors and database constraint errors can be detected so that users can be warned and erroneous cells can be corrected.</span></span>  
  
-   <span data-ttu-id="57a19-124">附加功能，例如列排序，冻结，和重新排序操作使用户能够查看其工作流最方便的方法中的数据。</span><span class="sxs-lookup"><span data-stu-id="57a19-124">Additional functionality such as column sorting, freezing, and reordering enable users to view data in the way most convenient for their workflow.</span></span>  
  
-   <span data-ttu-id="57a19-125">剪贴板支持使用户能够将数据复制到其他应用程序的应用程序。</span><span class="sxs-lookup"><span data-stu-id="57a19-125">Clipboard support enables users to copy data from your application into other applications.</span></span>  
  
## <a name="scenario-3-advanced-data"></a><span data-ttu-id="57a19-126">方案 3： 高级的数据</span><span class="sxs-lookup"><span data-stu-id="57a19-126">Scenario 3: Advanced Data</span></span>  
 <span data-ttu-id="57a19-127">如果你有标准的数据绑定模型不能解决的特殊需求，你可以通过实现管理控件和你的数据之间的交互*虚拟模式*。</span><span class="sxs-lookup"><span data-stu-id="57a19-127">If you have special needs that the standard data binding model does not address, you can manage the interaction between the control and your data by implementing *virtual mode*.</span></span> <span data-ttu-id="57a19-128">需要实现虚拟模式是指实现一个或多个事件处理程序，使控件请求的信息有关单元格的信息。</span><span class="sxs-lookup"><span data-stu-id="57a19-128">Implementing virtual mode means implementing one or more event handlers that let the control request information about cells as the information is needed.</span></span>  
  
 <span data-ttu-id="57a19-129">例如，如果你使用大量的数据，你可能想要实现虚拟模式以确保最佳的效率。</span><span class="sxs-lookup"><span data-stu-id="57a19-129">For example, if you work with large amounts of data, you may want to implement virtual mode to ensure optimal efficiency.</span></span> <span data-ttu-id="57a19-130">虚拟模式也是有用的维护，以及从其他数据源检索数据的列显示未绑定列的值。</span><span class="sxs-lookup"><span data-stu-id="57a19-130">Virtual mode is also useful for maintaining the values of unbound columns that you display along with columns retrieved from another data source.</span></span>  
  
 <span data-ttu-id="57a19-131">有关虚拟模式的详细信息，请参阅[演练： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-131">For more information about virtual mode, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="57a19-132">方案关键点</span><span class="sxs-lookup"><span data-stu-id="57a19-132">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="57a19-133">虚拟模式适合需要进行微调性能时显示的数据量非常大。</span><span class="sxs-lookup"><span data-stu-id="57a19-133">Virtual mode is suited for displaying very large amounts of data when you need to fine-tune performance.</span></span>  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a><span data-ttu-id="57a19-134">方案 4： 自动调整行和列</span><span class="sxs-lookup"><span data-stu-id="57a19-134">Scenario 4: Automatically Resizing Rows and Columns</span></span>  
 <span data-ttu-id="57a19-135">当显示定期更新的数据时，您可以自动调整行和列以确保所有内容都是可见。</span><span class="sxs-lookup"><span data-stu-id="57a19-135">When you display data that is regularly updated, you can automatically resize rows and columns to ensure that all content is visible.</span></span> <span data-ttu-id="57a19-136"><xref:System.Windows.Forms.DataGridView>控件提供了几个选项，可以启用或禁用手动调整大小，在特定时间，以编程方式调整大小或大小调整内容时自动更改。</span><span class="sxs-lookup"><span data-stu-id="57a19-136">The <xref:System.Windows.Forms.DataGridView> control provides several options that let you enable or disable manual resizing, resize programmatically at specific times, or resize automatically whenever content changes.</span></span> <span data-ttu-id="57a19-137">有关详细信息，请参阅[在 Windows 窗体 DataGridView 控件中调整选项](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-137">For more information, see [Sizing Options in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="57a19-138">方案关键点</span><span class="sxs-lookup"><span data-stu-id="57a19-138">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="57a19-139">手动调整大小使用户能够调整单元格的高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="57a19-139">Manual resizing enables users to adjust cell heights and widths.</span></span>  
  
-   <span data-ttu-id="57a19-140">自动调整大小，可以以维护单元格的大小，以便永远不会剪切单元格内容。</span><span class="sxs-lookup"><span data-stu-id="57a19-140">Automatic resizing enables you to maintain cell sizes so that cell content is never clipped.</span></span>  
  
-   <span data-ttu-id="57a19-141">以编程方式调整大小，你能够调整单元格大小在特定时间，以避免对性能的影响的连续自动调整大小。</span><span class="sxs-lookup"><span data-stu-id="57a19-141">Programmatic resizing enables you to resize cells at specific times to avoid the performance penalty of continuous automatic resizing.</span></span>  
  
## <a name="scenario-5-simple-customization"></a><span data-ttu-id="57a19-142">方案 5： 简单的自定义项</span><span class="sxs-lookup"><span data-stu-id="57a19-142">Scenario 5: Simple Customization</span></span>  
 <span data-ttu-id="57a19-143"><xref:System.Windows.Forms.DataGridView>控件提供了许多方法为您要更改其基本外观和行为。</span><span class="sxs-lookup"><span data-stu-id="57a19-143">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to alter its basic appearance and behavior.</span></span> <span data-ttu-id="57a19-144">有关详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-144">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="57a19-145">方案关键点</span><span class="sxs-lookup"><span data-stu-id="57a19-145">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="57a19-146"><xref:System.Windows.Forms.DataGridViewCellStyle> 对象使您可以提供颜色、 字体格式设置，和多个级别和控件的各个元素的定位信息。</span><span class="sxs-lookup"><span data-stu-id="57a19-146"><xref:System.Windows.Forms.DataGridViewCellStyle> objects let you provide color, font, formatting, and positioning information at multiple levels and for individual elements of the control.</span></span>  
  
-   <span data-ttu-id="57a19-147">可以层和共享的多个元素，从而允许重用代码的单元格样式。</span><span class="sxs-lookup"><span data-stu-id="57a19-147">Cell styles can be layered and shared by multiple elements, letting you reuse code.</span></span>  
  
## <a name="scenario-6-advanced-customization"></a><span data-ttu-id="57a19-148">方案 6： 高级自定义</span><span class="sxs-lookup"><span data-stu-id="57a19-148">Scenario 6: Advanced Customization</span></span>  
 <span data-ttu-id="57a19-149"><xref:System.Windows.Forms.DataGridView>控件提供了许多方法供你自定义其外观和行为。</span><span class="sxs-lookup"><span data-stu-id="57a19-149">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to customize its appearance and behavior.</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="57a19-150">方案关键点</span><span class="sxs-lookup"><span data-stu-id="57a19-150">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="57a19-151">你可以提供你自己的单元格绘制代码。</span><span class="sxs-lookup"><span data-stu-id="57a19-151">You can provide your own cell painting code.</span></span> <span data-ttu-id="57a19-152">有关详细信息，请参阅[如何： 自定义 Windows 窗体 DataGridView 控件中的单元外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-152">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="57a19-153">你可以提供你自己的行绘制。</span><span class="sxs-lookup"><span data-stu-id="57a19-153">You can provide your own row painting.</span></span> <span data-ttu-id="57a19-154">这很有用，例如，若要创建具有跨多个列的内容的行。</span><span class="sxs-lookup"><span data-stu-id="57a19-154">This is useful, for example, to create rows with content that spans multiple columns.</span></span> <span data-ttu-id="57a19-155">有关详细信息，请参阅[如何： 自定义 Windows 窗体 DataGridView 控件中的行外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-155">For more information, see [How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="57a19-156">你可以实现您自己的单元格和列类以自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="57a19-156">You can implement your own cell and column classes to customize cell appearance.</span></span> <span data-ttu-id="57a19-157">有关详细信息，请参阅[如何： 自定义单元格和扩展他们行为和外观由 Windows 窗体 DataGridView 控件中的列](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-157">For more information, see [How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).</span></span>  
  
-   <span data-ttu-id="57a19-158">你可以实现您自己到提供的内置列类型之外的主机控件的单元格和列的类。</span><span class="sxs-lookup"><span data-stu-id="57a19-158">You can implement your own cell and column classes to host controls other than the ones provided by the built-in column types.</span></span> <span data-ttu-id="57a19-159">有关详细信息，请参阅[如何： 在 Windows 窗体 DataGridView 单元格的主机控件](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)。</span><span class="sxs-lookup"><span data-stu-id="57a19-159">For more information, see [How to: Host Controls in Windows Forms DataGridView Cells](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a19-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="57a19-160">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="57a19-161">DataGridView 控件概述</span><span class="sxs-lookup"><span data-stu-id="57a19-161">DataGridView Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)
