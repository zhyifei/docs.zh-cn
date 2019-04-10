---
title: 演练：验证 Windows 窗体 DataGridView 控件中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: a4bf0850b28b7101ba76f1c1fedc6633eccb81a1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346049"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="74d0c-102">演练：验证 Windows 窗体 DataGridView 控件中的数据</span><span class="sxs-lookup"><span data-stu-id="74d0c-102">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="74d0c-103">向用户显示数据条目的功能，经常需要验证你的窗体中输入的数据。</span><span class="sxs-lookup"><span data-stu-id="74d0c-103">When you display data entry functionality to users, you frequently have to validate the data entered into your form.</span></span> <span data-ttu-id="74d0c-104"><xref:System.Windows.Forms.DataGridView>类提供了方便地在数据提交到数据存储区之前执行验证。</span><span class="sxs-lookup"><span data-stu-id="74d0c-104">The <xref:System.Windows.Forms.DataGridView> class provides a convenient way to perform validation before data is committed to the data store.</span></span> <span data-ttu-id="74d0c-105">可以通过处理在验证数据<xref:System.Windows.Forms.DataGridView.CellValidating>事件，引发的<xref:System.Windows.Forms.DataGridView>当前单元格发生更改时。</span><span class="sxs-lookup"><span data-stu-id="74d0c-105">You can validate data by handling the <xref:System.Windows.Forms.DataGridView.CellValidating> event, which is raised by the <xref:System.Windows.Forms.DataGridView> when the current cell changes.</span></span>  
  
 <span data-ttu-id="74d0c-106">在本演练中，您将检索中的行`Customers`Northwind 示例数据库中表，然后将它们显示在<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="74d0c-106">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="74d0c-107">当用户编辑中的单元格`CompanyName`列，尝试将单元格，保留<xref:System.Windows.Forms.DataGridView.CellValidating>事件处理程序将检查新的公司名称字符串，以确保它不为空; 如果新值为空字符串，<xref:System.Windows.Forms.DataGridView>将阻止用户的光标从离开该单元格，直到输入一个非空字符串。</span><span class="sxs-lookup"><span data-stu-id="74d0c-107">When a user edits a cell in the `CompanyName` column and tries to leave the cell, the <xref:System.Windows.Forms.DataGridView.CellValidating> event handler will examine new company name string to make sure it is not empty; if the new value is an empty string, the <xref:System.Windows.Forms.DataGridView> will prevent the user's cursor from leaving the cell until a non-empty string is entered.</span></span>  
  
 <span data-ttu-id="74d0c-108">要将本主题中的代码作为单个列表进行复制，请参阅[如何：验证 Windows 窗体 DataGridView 控件中的数据](how-to-validate-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="74d0c-108">To copy the code in this topic as a single listing, see [How to: Validate Data in the Windows Forms DataGridView Control](how-to-validate-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="74d0c-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="74d0c-109">Prerequisites</span></span>  
 <span data-ttu-id="74d0c-110">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="74d0c-110">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="74d0c-111">对具有 Northwind SQL Server 示例数据库的服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="74d0c-111">Access to a server that has the Northwind SQL Server sample database.</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="74d0c-112">创建窗体</span><span class="sxs-lookup"><span data-stu-id="74d0c-112">Creating the Form</span></span>  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a><span data-ttu-id="74d0c-113">若要验证在 DataGridView 中输入数据</span><span class="sxs-lookup"><span data-stu-id="74d0c-113">To validate data entered in a DataGridView</span></span>  
  
1. <span data-ttu-id="74d0c-114">创建派生的类<xref:System.Windows.Forms.Form>并且包含<xref:System.Windows.Forms.DataGridView>控件和一个<xref:System.Windows.Forms.BindingSource>组件。</span><span class="sxs-lookup"><span data-stu-id="74d0c-114">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     <span data-ttu-id="74d0c-115">下面的代码示例提供了基本的初始化，并包括`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="74d0c-115">The following code example provides basic initialization and includes a `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2. <span data-ttu-id="74d0c-116">用于处理连接到数据库的详细信息窗体的类定义中实现的方法。</span><span class="sxs-lookup"><span data-stu-id="74d0c-116">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>  
  
     <span data-ttu-id="74d0c-117">此代码示例使用`GetData`方法，它返回已填充<xref:System.Data.DataTable>对象。</span><span class="sxs-lookup"><span data-stu-id="74d0c-117">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="74d0c-118">请确保您设置`connectionString`变量为适合于您的数据库的值。</span><span class="sxs-lookup"><span data-stu-id="74d0c-118">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="74d0c-119">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="74d0c-119">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="74d0c-120">使用 Windows 身份验证，也称为集成安全性，是更安全的方式来控制对数据库的访问。</span><span class="sxs-lookup"><span data-stu-id="74d0c-120">Using Windows Authentication, also known as integrated security, is a more secure way to control access to a database.</span></span> <span data-ttu-id="74d0c-121">有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="74d0c-121">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3. <span data-ttu-id="74d0c-122">实现窗体的一个处理程序<xref:System.Windows.Forms.Form.Load>初始化的事件<xref:System.Windows.Forms.DataGridView>和<xref:System.Windows.Forms.BindingSource>和数据绑定设置。</span><span class="sxs-lookup"><span data-stu-id="74d0c-122">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4. <span data-ttu-id="74d0c-123">实现的处理程序<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.CellValidating>和<xref:System.Windows.Forms.DataGridView.CellEndEdit>事件。</span><span class="sxs-lookup"><span data-stu-id="74d0c-123">Implement handlers for the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellValidating> and <xref:System.Windows.Forms.DataGridView.CellEndEdit> events.</span></span>  
  
     <span data-ttu-id="74d0c-124"><xref:System.Windows.Forms.DataGridView.CellValidating>事件处理程序，确定是否在单元格的值`CompanyName`列为空。</span><span class="sxs-lookup"><span data-stu-id="74d0c-124">The <xref:System.Windows.Forms.DataGridView.CellValidating> event handler is where you determine whether the value of a cell in the `CompanyName` column is empty.</span></span> <span data-ttu-id="74d0c-125">如果单元格的值未通过验证，则设置<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>的属性<xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType>类到`true`。</span><span class="sxs-lookup"><span data-stu-id="74d0c-125">If the cell value fails validation, set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property of the <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> class to `true`.</span></span> <span data-ttu-id="74d0c-126">这将导致<xref:System.Windows.Forms.DataGridView>控制，以阻止光标离开该单元格。</span><span class="sxs-lookup"><span data-stu-id="74d0c-126">This causes the <xref:System.Windows.Forms.DataGridView> control to prevent the cursor from leaving the cell.</span></span> <span data-ttu-id="74d0c-127">设置<xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>到说明性字符串的行上的属性。</span><span class="sxs-lookup"><span data-stu-id="74d0c-127">Set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to an explanatory string.</span></span> <span data-ttu-id="74d0c-128">这将显示错误图标，包含错误文本的工具提示。</span><span class="sxs-lookup"><span data-stu-id="74d0c-128">This displays an error icon with a ToolTip that contains the error text.</span></span> <span data-ttu-id="74d0c-129">在中<xref:System.Windows.Forms.DataGridView.CellEndEdit>事件处理程序设置<xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>属性为空字符串的行。</span><span class="sxs-lookup"><span data-stu-id="74d0c-129">In the <xref:System.Windows.Forms.DataGridView.CellEndEdit> event handler, set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to the empty string.</span></span> <span data-ttu-id="74d0c-130"><xref:System.Windows.Forms.DataGridView.CellEndEdit>仅当该单元格退出编辑模式下，如果它未通过验证，无法执行发生的事件。</span><span class="sxs-lookup"><span data-stu-id="74d0c-130">The <xref:System.Windows.Forms.DataGridView.CellEndEdit> event occurs only when the cell exits edit mode, which it cannot do if it fails validation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="74d0c-131">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="74d0c-131">Testing the Application</span></span>  
 <span data-ttu-id="74d0c-132">现在可以测试窗体，以确保其行为符合预期。</span><span class="sxs-lookup"><span data-stu-id="74d0c-132">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="74d0c-133">若要测试窗体</span><span class="sxs-lookup"><span data-stu-id="74d0c-133">To test the form</span></span>  
  
-   <span data-ttu-id="74d0c-134">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="74d0c-134">Compile and run the application.</span></span>  
  
     <span data-ttu-id="74d0c-135">你将看到<xref:System.Windows.Forms.DataGridView>中的数据填充`Customers`表。</span><span class="sxs-lookup"><span data-stu-id="74d0c-135">You will see a <xref:System.Windows.Forms.DataGridView> filled with data from the `Customers` table.</span></span> <span data-ttu-id="74d0c-136">当双击中的单元格`CompanyName`列中，可以编辑的值。</span><span class="sxs-lookup"><span data-stu-id="74d0c-136">When you double-click a cell in the `CompanyName` column, you can edit the value.</span></span> <span data-ttu-id="74d0c-137">如果你删除所有字符并按 TAB 键退出单元格，<xref:System.Windows.Forms.DataGridView>会阻止你退出。</span><span class="sxs-lookup"><span data-stu-id="74d0c-137">If you delete all the characters and hit the TAB key to exit the cell, the <xref:System.Windows.Forms.DataGridView> prevents you from exiting.</span></span> <span data-ttu-id="74d0c-138">在单元格中，键入一个非空字符串时<xref:System.Windows.Forms.DataGridView>控件，可以退出单元格。</span><span class="sxs-lookup"><span data-stu-id="74d0c-138">When you type a non-empty string into the cell, the <xref:System.Windows.Forms.DataGridView> control lets you exit the cell.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="74d0c-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="74d0c-139">Next Steps</span></span>  
 <span data-ttu-id="74d0c-140">此应用程序为您提供了一个基本的了解<xref:System.Windows.Forms.DataGridView>控件的功能。</span><span class="sxs-lookup"><span data-stu-id="74d0c-140">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="74d0c-141">你可以自定义外观和行为<xref:System.Windows.Forms.DataGridView>控制几种方式：</span><span class="sxs-lookup"><span data-stu-id="74d0c-141">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="74d0c-142">更改边框和标头的样式。</span><span class="sxs-lookup"><span data-stu-id="74d0c-142">Change border and header styles.</span></span> <span data-ttu-id="74d0c-143">有关详细信息，请参阅[如何：更改边框和网格线的样式中的 Windows 窗体 DataGridView 控件](change-the-border-and-gridline-styles-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="74d0c-143">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="74d0c-144">启用或限制的用户输入<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="74d0c-144">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="74d0c-145">有关详细信息，请参阅[如何：防止行中添加和删除 Windows 窗体 DataGridView 控件](prevent-row-addition-and-deletion-datagridview.md)，和[如何：将列设为只读、 只在 Windows 窗体 DataGridView 控件](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="74d0c-145">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="74d0c-146">检查用户输入与数据库相关的错误。</span><span class="sxs-lookup"><span data-stu-id="74d0c-146">Check user input for database-related errors.</span></span> <span data-ttu-id="74d0c-147">有关详细信息，请参见[演练：在 Windows 中的数据输入时发生的错误处理窗体 DataGridView 控件](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="74d0c-147">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="74d0c-148">处理极大型数据集使用的虚拟模式。</span><span class="sxs-lookup"><span data-stu-id="74d0c-148">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="74d0c-149">有关详细信息，请参见[演练：在 Windows 中实现虚拟模式窗体 DataGridView 控件](implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="74d0c-149">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="74d0c-150">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="74d0c-150">Customize the appearance of cells.</span></span> <span data-ttu-id="74d0c-151">有关详细信息，请参阅[如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)和[如何：在 Windows 窗体 DataGridView 控件中设置字体和颜色样式](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="74d0c-151">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Font and Color Styles in the Windows Forms DataGridView Control](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d0c-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="74d0c-152">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="74d0c-153">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="74d0c-153">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="74d0c-154">如何：验证 Windows 窗体 DataGridView 控件中的数据</span><span class="sxs-lookup"><span data-stu-id="74d0c-154">How to: Validate Data in the Windows Forms DataGridView Control</span></span>](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="74d0c-155">演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误</span><span class="sxs-lookup"><span data-stu-id="74d0c-155">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="74d0c-156">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="74d0c-156">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
