---
title: 演练：创建未绑定的 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ba821b461434cb7a5247d2962a161a1c171bbd14
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651463"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="56104-102">演练：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="56104-102">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="56104-103">您可能经常想要显示不是从数据库的表格数据。</span><span class="sxs-lookup"><span data-stu-id="56104-103">You may frequently want to display tabular data that does not originate from a database.</span></span> <span data-ttu-id="56104-104">例如，你可能想要显示二维数组的字符串的内容。</span><span class="sxs-lookup"><span data-stu-id="56104-104">For example, you may want to show the contents of a two-dimensional array of strings.</span></span> <span data-ttu-id="56104-105"><xref:System.Windows.Forms.DataGridView>类提供了简单且高度可自定义的方式来显示数据，而不绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="56104-105">The <xref:System.Windows.Forms.DataGridView> class provides an easy and highly customizable way to display data without binding to a data source.</span></span> <span data-ttu-id="56104-106">本演练演示如何填充<xref:System.Windows.Forms.DataGridView>控制和管理的添加和删除"取消绑定"模式中的行。</span><span class="sxs-lookup"><span data-stu-id="56104-106">This walkthrough shows how to populate a <xref:System.Windows.Forms.DataGridView> control and manage the addition and deletion of rows in "unbound" mode.</span></span> <span data-ttu-id="56104-107">默认情况下，用户可以添加新行。</span><span class="sxs-lookup"><span data-stu-id="56104-107">By default, the user can add new rows.</span></span> <span data-ttu-id="56104-108">若要禁止添加行，将设置<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="56104-108">To prevent row addition, set the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="56104-109">要将本主题中的代码作为单个列表进行复制，请参阅[如何：创建未绑定的 Windows 窗体 DataGridView 控件](how-to-create-an-unbound-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="56104-109">To copy the code in this topic as a single listing, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="56104-110">创建窗体</span><span class="sxs-lookup"><span data-stu-id="56104-110">Creating the Form</span></span>  
  
#### <a name="to-use-an-unbound-datagridview-control"></a><span data-ttu-id="56104-111">若要使用未绑定的 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="56104-111">To use an unbound DataGridView control</span></span>  
  
1. <span data-ttu-id="56104-112">创建派生的类<xref:System.Windows.Forms.Form>并且包含以下变量声明和`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="56104-112">Create a class that derives from <xref:System.Windows.Forms.Form> and contains the following variable declarations and `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. <span data-ttu-id="56104-113">实现`SetupLayout`窗体的类定义以设置窗体的布局中的方法。</span><span class="sxs-lookup"><span data-stu-id="56104-113">Implement a `SetupLayout` method in your form's class definition to set up the form's layout.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. <span data-ttu-id="56104-114">创建`SetupDataGridView`方法以设置<xref:System.Windows.Forms.DataGridView>列和属性。</span><span class="sxs-lookup"><span data-stu-id="56104-114">Create a `SetupDataGridView` method to set up the <xref:System.Windows.Forms.DataGridView> columns and properties.</span></span>  
  
     <span data-ttu-id="56104-115">此方法首先将添加<xref:System.Windows.Forms.DataGridView>控件在窗体的<xref:System.Windows.Forms.Control.Controls%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="56104-115">This method first adds the <xref:System.Windows.Forms.DataGridView> control to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="56104-116">接下来，使用设置要显示的列数<xref:System.Windows.Forms.DataGridView.ColumnCount%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="56104-116">Next, the number of columns to be displayed is set using the <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> property.</span></span> <span data-ttu-id="56104-117">通过设置来设置列标题的默认样式<xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>， <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>，并<xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>的属性<xref:System.Windows.Forms.DataGridViewCellStyle>返回<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="56104-117">The default style for the column headers is set by setting the <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, and <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> returned by the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> property.</span></span>  
  
     <span data-ttu-id="56104-118">设置布局和外观属性，并且然后分配列名称。</span><span class="sxs-lookup"><span data-stu-id="56104-118">Layout and appearance properties are set, and then the column names are assigned.</span></span> <span data-ttu-id="56104-119">当此方法退出时，<xref:System.Windows.Forms.DataGridView>控件已准备好进行填充。</span><span class="sxs-lookup"><span data-stu-id="56104-119">When this method exits, the <xref:System.Windows.Forms.DataGridView> control is ready to be populated.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. <span data-ttu-id="56104-120">创建`PopulateDataGridView`方法以将行添加到<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="56104-120">Create a `PopulateDataGridView` method to add rows to the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="56104-121">每一行代表一首歌曲和其相关的信息。</span><span class="sxs-lookup"><span data-stu-id="56104-121">Each row represents a song and its associated information.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. <span data-ttu-id="56104-122">使用实用工具方法后，可以将附加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="56104-122">With the utility methods in place, you can attach event handlers.</span></span>  
  
     <span data-ttu-id="56104-123">将处理**添加**和**删除**按钮<xref:System.Windows.Forms.Control.Click>事件、 窗体的<xref:System.Windows.Forms.Form.Load>事件，以及<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.CellFormatting>事件。</span><span class="sxs-lookup"><span data-stu-id="56104-123">You will handle the **Add** and **Delete** buttons' <xref:System.Windows.Forms.Control.Click> events, the form's <xref:System.Windows.Forms.Form.Load> event, and the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
     <span data-ttu-id="56104-124">当**外**按钮的<xref:System.Windows.Forms.Control.Click>引发事件时，新的、 空的行添加到<xref:System.Windows.Forms.DataGridView>。</span><span class="sxs-lookup"><span data-stu-id="56104-124">When the **Add** button's <xref:System.Windows.Forms.Control.Click> event is raised, a new, empty row is added to the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="56104-125">当**删除**按钮的<xref:System.Windows.Forms.Control.Click>引发事件，删除所选的行，除非它是用于新记录，用户可以使用它的行中添加新行。</span><span class="sxs-lookup"><span data-stu-id="56104-125">When the **Delete** button's <xref:System.Windows.Forms.Control.Click> event is raised, the selected row is deleted, unless it is the row for new records, which enables the user add new rows.</span></span> <span data-ttu-id="56104-126">此行始终是中的最后一行<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="56104-126">This row is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="56104-127">当窗体的<xref:System.Windows.Forms.Form.Load>引发事件时， `SetupLayout`， `SetupDataGridView`，和`PopulateDataGridView`调用实用程序方法。</span><span class="sxs-lookup"><span data-stu-id="56104-127">When the form's <xref:System.Windows.Forms.Form.Load> event is raised, the `SetupLayout`, `SetupDataGridView`, and `PopulateDataGridView` utility methods are called.</span></span>  
  
     <span data-ttu-id="56104-128">当<xref:System.Windows.Forms.DataGridView.CellFormatting>引发事件时，每个单元格中`Date`列的格式为长日期，除非该单元格的值不能分析。</span><span class="sxs-lookup"><span data-stu-id="56104-128">When the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is raised, each cell in the `Date` column is formatted as a long date, unless the cell's value cannot be parsed.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="56104-129">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="56104-129">Testing the Application</span></span>  
 <span data-ttu-id="56104-130">现在可以测试窗体，以确保其行为符合预期。</span><span class="sxs-lookup"><span data-stu-id="56104-130">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="56104-131">若要测试窗体</span><span class="sxs-lookup"><span data-stu-id="56104-131">To test the form</span></span>  
  
- <span data-ttu-id="56104-132">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="56104-132">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="56104-133">你将看到<xref:System.Windows.Forms.DataGridView>控件，用于显示中列出的歌曲`PopulateDataGridView`。</span><span class="sxs-lookup"><span data-stu-id="56104-133">You will see a <xref:System.Windows.Forms.DataGridView> control that displays the songs listed in `PopulateDataGridView`.</span></span> <span data-ttu-id="56104-134">您可以添加新行与**添加行**按钮，并且您可以删除与所选的行**删除行**按钮。</span><span class="sxs-lookup"><span data-stu-id="56104-134">You can add new rows with the **Add Row** button, and you can delete selected rows with the **Delete Row** button.</span></span> <span data-ttu-id="56104-135">未绑定<xref:System.Windows.Forms.DataGridView>控件的数据存储，并且其数据独立于任何外部源，如<xref:System.Data.DataSet>或数组。</span><span class="sxs-lookup"><span data-stu-id="56104-135">The unbound <xref:System.Windows.Forms.DataGridView> control is the data store, and its data is independent of any external source, such as a <xref:System.Data.DataSet> or an array.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="56104-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56104-136">Next Steps</span></span>  
 <span data-ttu-id="56104-137">此应用程序为您提供了一个基本的了解<xref:System.Windows.Forms.DataGridView>控件的功能。</span><span class="sxs-lookup"><span data-stu-id="56104-137">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="56104-138">你可以自定义外观和行为<xref:System.Windows.Forms.DataGridView>控制几种方式：</span><span class="sxs-lookup"><span data-stu-id="56104-138">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
- <span data-ttu-id="56104-139">更改边框和标头的样式。</span><span class="sxs-lookup"><span data-stu-id="56104-139">Change border and header styles.</span></span> <span data-ttu-id="56104-140">有关详细信息，请参阅[如何：更改边框和网格线的样式中的 Windows 窗体 DataGridView 控件](change-the-border-and-gridline-styles-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="56104-140">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="56104-141">启用或限制的用户输入<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="56104-141">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="56104-142">有关详细信息，请参阅[如何：防止行中添加和删除 Windows 窗体 DataGridView 控件](prevent-row-addition-and-deletion-datagridview.md)，和[如何：将列设为只读、 只在 Windows 窗体 DataGridView 控件](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="56104-142">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="56104-143">检查用户输入与数据库相关的错误。</span><span class="sxs-lookup"><span data-stu-id="56104-143">Check user input for database-related errors.</span></span> <span data-ttu-id="56104-144">有关详细信息，请参见[演练：在 Windows 中的数据输入时发生的错误处理窗体 DataGridView 控件](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="56104-144">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="56104-145">处理极大型数据集使用的虚拟模式。</span><span class="sxs-lookup"><span data-stu-id="56104-145">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="56104-146">有关详细信息，请参见[演练：在 Windows 中实现虚拟模式窗体 DataGridView 控件](implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="56104-146">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="56104-147">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="56104-147">Customize the appearance of cells.</span></span> <span data-ttu-id="56104-148">有关详细信息，请参阅[如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)和[如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="56104-148">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56104-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="56104-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="56104-150">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="56104-150">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="56104-151">如何：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="56104-151">How to: Create an Unbound Windows Forms DataGridView Control</span></span>](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="56104-152">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="56104-152">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
