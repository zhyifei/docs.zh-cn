---
title: "演练：创建未绑定的 Windows 窗体 DataGridView 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d737959ee0ecab4c611cebf996741516fc7be031
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="cf8b3-102">演练：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="cf8b3-102">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cf8b3-103">你可能经常想要显示不是从数据库的表格数据。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-103">You may frequently want to display tabular data that does not originate from a database.</span></span> <span data-ttu-id="cf8b3-104">例如，你可能想要显示的字符串的二维数组的内容。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-104">For example, you may want to show the contents of a two-dimensional array of strings.</span></span> <span data-ttu-id="cf8b3-105"><xref:System.Windows.Forms.DataGridView>类提供了一种简单且高度可自定义的方法，以显示数据不绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-105">The <xref:System.Windows.Forms.DataGridView> class provides an easy and highly customizable way to display data without binding to a data source.</span></span> <span data-ttu-id="cf8b3-106">本演练演示如何填充<xref:System.Windows.Forms.DataGridView>控制和管理的添加和删除的"取消绑定"模式中的行。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-106">This walkthrough shows how to populate a <xref:System.Windows.Forms.DataGridView> control and manage the addition and deletion of rows in "unbound" mode.</span></span> <span data-ttu-id="cf8b3-107">默认情况下，用户可以添加新行。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-107">By default, the user can add new rows.</span></span> <span data-ttu-id="cf8b3-108">若要禁止添加行，将设置<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-108">To prevent row addition, set the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="cf8b3-109">若要将代码复制本主题中的一个单独的清单，请参阅[如何： 创建未绑定的 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-109">To copy the code in this topic as a single listing, see [How to: Create an Unbound Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="cf8b3-110">创建窗体</span><span class="sxs-lookup"><span data-stu-id="cf8b3-110">Creating the Form</span></span>  
  
#### <a name="to-use-an-unbound-datagridview-control"></a><span data-ttu-id="cf8b3-111">若要使用未绑定的 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="cf8b3-111">To use an unbound DataGridView control</span></span>  
  
1.  <span data-ttu-id="cf8b3-112">创建一个类，派生自<xref:System.Windows.Forms.Form>和包含以下变量声明和`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-112">Create a class that derives from <xref:System.Windows.Forms.Form> and contains the following variable declarations and `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  <span data-ttu-id="cf8b3-113">实现`SetupLayout`设置窗体的布局的窗体的类定义中的方法。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-113">Implement a `SetupLayout` method in your form's class definition to set up the form's layout.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  <span data-ttu-id="cf8b3-114">创建`SetupDataGridView`方法以设置<xref:System.Windows.Forms.DataGridView>列和属性。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-114">Create a `SetupDataGridView` method to set up the <xref:System.Windows.Forms.DataGridView> columns and properties.</span></span>  
  
     <span data-ttu-id="cf8b3-115">此方法首先将添加<xref:System.Windows.Forms.DataGridView>控件添加到窗体的<xref:System.Windows.Forms.Control.Controls%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-115">This method first adds the <xref:System.Windows.Forms.DataGridView> control to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="cf8b3-116">接下来，使用设置要显示的列数<xref:System.Windows.Forms.DataGridView.ColumnCount%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-116">Next, the number of columns to be displayed is set using the <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> property.</span></span> <span data-ttu-id="cf8b3-117">通过设置来设置列标题的默认样式<xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>， <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>，和<xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>属性<xref:System.Windows.Forms.DataGridViewCellStyle>返回<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-117">The default style for the column headers is set by setting the <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, and <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> returned by the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> property.</span></span>  
  
     <span data-ttu-id="cf8b3-118">设置布局和外观属性，并将分配列名称。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-118">Layout and appearance properties are set, and then the column names are assigned.</span></span> <span data-ttu-id="cf8b3-119">当此方法退出时，<xref:System.Windows.Forms.DataGridView>控件已准备好进行填充。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-119">When this method exits, the <xref:System.Windows.Forms.DataGridView> control is ready to be populated.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  <span data-ttu-id="cf8b3-120">创建`PopulateDataGridView`方法以将行添加到<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-120">Create a `PopulateDataGridView` method to add rows to the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="cf8b3-121">每一行代表一首歌曲和其相关的信息。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-121">Each row represents a song and its associated information.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  <span data-ttu-id="cf8b3-122">与就地的实用工具方法，你可以附加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-122">With the utility methods in place, you can attach event handlers.</span></span>  
  
     <span data-ttu-id="cf8b3-123">将处理**添加**和**删除**按钮的<xref:System.Windows.Forms.Control.Click>事件、 窗体的<xref:System.Windows.Forms.Form.Load>事件，和<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.CellFormatting>事件。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-123">You will handle the **Add** and **Delete** buttons' <xref:System.Windows.Forms.Control.Click> events, the form's <xref:System.Windows.Forms.Form.Load> event, and the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
     <span data-ttu-id="cf8b3-124">当**添加**按钮的<xref:System.Windows.Forms.Control.Click>引发事件时，新的空的行添加到<xref:System.Windows.Forms.DataGridView>。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-124">When the **Add** button's <xref:System.Windows.Forms.Control.Click> event is raised, a new, empty row is added to the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="cf8b3-125">当**删除**按钮的<xref:System.Windows.Forms.Control.Click>引发事件，删除所选的行，除非它是新记录，以便用户可以在行中添加新行。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-125">When the **Delete** button's <xref:System.Windows.Forms.Control.Click> event is raised, the selected row is deleted, unless it is the row for new records, which enables the user add new rows.</span></span> <span data-ttu-id="cf8b3-126">该行始终是中的最后一行<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-126">This row is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="cf8b3-127">当窗体的<xref:System.Windows.Forms.Form.Load>引发事件时， `SetupLayout`， `SetupDataGridView`，和`PopulateDataGridView`调用实用工具方法。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-127">When the form's <xref:System.Windows.Forms.Form.Load> event is raised, the `SetupLayout`, `SetupDataGridView`, and `PopulateDataGridView` utility methods are called.</span></span>  
  
     <span data-ttu-id="cf8b3-128">当<xref:System.Windows.Forms.DataGridView.CellFormatting>引发事件时，每个单元格中`Date`列将格式化为长日期，除非无法分析该单元格的值。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-128">When the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is raised, each cell in the `Date` column is formatted as a long date, unless the cell's value cannot be parsed.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="cf8b3-129">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="cf8b3-129">Testing the Application</span></span>  
 <span data-ttu-id="cf8b3-130">你现在可以测试窗体，以确保其行为与预期相同。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-130">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="cf8b3-131">若要测试窗体</span><span class="sxs-lookup"><span data-stu-id="cf8b3-131">To test the form</span></span>  
  
-   <span data-ttu-id="cf8b3-132">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-132">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="cf8b3-133">你将看到<xref:System.Windows.Forms.DataGridView>显示中列出的歌曲控件`PopulateDataGridView`。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-133">You will see a <xref:System.Windows.Forms.DataGridView> control that displays the songs listed in `PopulateDataGridView`.</span></span> <span data-ttu-id="cf8b3-134">你可以添加新行和的**添加行**按钮，并且您可以删除与所选的行**删除行**按钮。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-134">You can add new rows with the **Add Row** button, and you can delete selected rows with the **Delete Row** button.</span></span> <span data-ttu-id="cf8b3-135">未绑定<xref:System.Windows.Forms.DataGridView>控件是数据存储，其数据是独立于任何外部源，如<xref:System.Data.DataSet>或数组。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-135">The unbound <xref:System.Windows.Forms.DataGridView> control is the data store, and its data is independent of any external source, such as a <xref:System.Data.DataSet> or an array.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cf8b3-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cf8b3-136">Next Steps</span></span>  
 <span data-ttu-id="cf8b3-137">此应用程序提供一个基本的了解<xref:System.Windows.Forms.DataGridView>控件的功能。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-137">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="cf8b3-138">你可以自定义的外观和行为<xref:System.Windows.Forms.DataGridView>控制以下几种方式：</span><span class="sxs-lookup"><span data-stu-id="cf8b3-138">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="cf8b3-139">更改边框和标头的样式。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-139">Change border and header styles.</span></span> <span data-ttu-id="cf8b3-140">有关详细信息，请参阅[如何： 更改边框和网格线在 Windows 窗体 DataGridView 控件中的样式](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-140">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="cf8b3-141">允许或限制用户输入到<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-141">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="cf8b3-142">有关详细信息，请参阅[如何： 防止添加和删除行在 Windows 窗体 DataGridView 控件中](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)，和[如何： 在 Windows 窗体 DataGridView 控件中使列成为只读](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-142">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="cf8b3-143">检查与数据库相关的错误的用户输入。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-143">Check user input for database-related errors.</span></span> <span data-ttu-id="cf8b3-144">有关详细信息，请参阅[演练： 处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-144">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="cf8b3-145">处理非常大的数据集使用的虚拟模式。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-145">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="cf8b3-146">有关详细信息，请参阅[演练： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-146">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="cf8b3-147">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-147">Customize the appearance of cells.</span></span> <span data-ttu-id="cf8b3-148">有关详细信息，请参阅[如何： 自定义 Windows 窗体 DataGridView 控件中的单元外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)和[如何： 设置 Windows 窗体 DataGridView 控件的默认单元格样式](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="cf8b3-148">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf8b3-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf8b3-149">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="cf8b3-150">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="cf8b3-150">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="cf8b3-151">如何：创建未绑定 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="cf8b3-151">How to: Create an Unbound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="cf8b3-152">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="cf8b3-152">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
