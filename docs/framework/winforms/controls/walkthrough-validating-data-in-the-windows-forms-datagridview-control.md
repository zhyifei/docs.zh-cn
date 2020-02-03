---
title: 演练：在 DataGridView 控件中验证数据
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
ms.openlocfilehash: 45753fb206ad58616c9a727bd81bd2458db6053e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740104"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a0036-102">演练：验证 Windows 窗体 DataGridView 控件中的数据</span><span class="sxs-lookup"><span data-stu-id="a0036-102">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="a0036-103">向用户显示数据输入功能时，通常需要验证输入到窗体中的数据。</span><span class="sxs-lookup"><span data-stu-id="a0036-103">When you display data entry functionality to users, you frequently have to validate the data entered into your form.</span></span> <span data-ttu-id="a0036-104">在数据提交到数据存储之前，<xref:System.Windows.Forms.DataGridView> 类提供一种简便的方法来执行验证。</span><span class="sxs-lookup"><span data-stu-id="a0036-104">The <xref:System.Windows.Forms.DataGridView> class provides a convenient way to perform validation before data is committed to the data store.</span></span> <span data-ttu-id="a0036-105">可以通过处理 <xref:System.Windows.Forms.DataGridView.CellValidating> 事件来验证数据，该事件由当前单元格更改时 <xref:System.Windows.Forms.DataGridView> 引发。</span><span class="sxs-lookup"><span data-stu-id="a0036-105">You can validate data by handling the <xref:System.Windows.Forms.DataGridView.CellValidating> event, which is raised by the <xref:System.Windows.Forms.DataGridView> when the current cell changes.</span></span>

<span data-ttu-id="a0036-106">在本演练中，您将从 Northwind 示例数据库的 "`Customers`" 表中检索行，并将它们显示在 <xref:System.Windows.Forms.DataGridView> 控件中。</span><span class="sxs-lookup"><span data-stu-id="a0036-106">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a0036-107">当用户编辑 `CompanyName` 列中的单元格并尝试离开单元格时，<xref:System.Windows.Forms.DataGridView.CellValidating> 事件处理程序将检查新公司名称字符串以确保它不为空;如果新值为空字符串，则 <xref:System.Windows.Forms.DataGridView> 会阻止用户的光标离开该单元格，直到输入非空字符串。</span><span class="sxs-lookup"><span data-stu-id="a0036-107">When a user edits a cell in the `CompanyName` column and tries to leave the cell, the <xref:System.Windows.Forms.DataGridView.CellValidating> event handler will examine new company name string to make sure it is not empty; if the new value is an empty string, the <xref:System.Windows.Forms.DataGridView> will prevent the user's cursor from leaving the cell until a non-empty string is entered.</span></span>

<span data-ttu-id="a0036-108">若要将本主题中的代码复制为单个列表，请参阅[如何：验证 Windows 窗体 DataGridView 控件中的数据](how-to-validate-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a0036-108">To copy the code in this topic as a single listing, see [How to: Validate Data in the Windows Forms DataGridView Control](how-to-validate-data-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0036-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="a0036-109">Prerequisites</span></span>

<span data-ttu-id="a0036-110">为了完成本演练，您需要：</span><span class="sxs-lookup"><span data-stu-id="a0036-110">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="a0036-111">访问包含 Northwind SQL Server 示例数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="a0036-111">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="a0036-112">创建窗体</span><span class="sxs-lookup"><span data-stu-id="a0036-112">Creating the Form</span></span>

#### <a name="to-validate-data-entered-in-a-datagridview"></a><span data-ttu-id="a0036-113">验证 DataGridView 中输入的数据</span><span class="sxs-lookup"><span data-stu-id="a0036-113">To validate data entered in a DataGridView</span></span>

1. <span data-ttu-id="a0036-114">创建一个派生自 <xref:System.Windows.Forms.Form> 的类，其中包含一个 <xref:System.Windows.Forms.DataGridView> 控件和一个 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="a0036-114">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="a0036-115">下面的代码示例提供了基本的初始化，并包括 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="a0036-115">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. <span data-ttu-id="a0036-116">在窗体的类定义中实现一个方法，用于处理连接到数据库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a0036-116">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="a0036-117">此代码示例使用 `GetData` 方法，该方法返回填充的 <xref:System.Data.DataTable> 对象。</span><span class="sxs-lookup"><span data-stu-id="a0036-117">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="a0036-118">请确保将 `connectionString` 变量设置为适合数据库的值。</span><span class="sxs-lookup"><span data-stu-id="a0036-118">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a0036-119">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="a0036-119">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="a0036-120">使用 Windows 身份验证（也称为集成安全性）是一种更安全的方式来控制对数据库的访问。</span><span class="sxs-lookup"><span data-stu-id="a0036-120">Using Windows Authentication, also known as integrated security, is a more secure way to control access to a database.</span></span> <span data-ttu-id="a0036-121">有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="a0036-121">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. <span data-ttu-id="a0036-122">为窗体的 <xref:System.Windows.Forms.Form.Load> 事件实现处理程序，该事件初始化 <xref:System.Windows.Forms.DataGridView> 并 <xref:System.Windows.Forms.BindingSource> 和设置数据绑定。</span><span class="sxs-lookup"><span data-stu-id="a0036-122">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. <span data-ttu-id="a0036-123">为 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CellValidating> 和 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 事件实现处理程序。</span><span class="sxs-lookup"><span data-stu-id="a0036-123">Implement handlers for the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellValidating> and <xref:System.Windows.Forms.DataGridView.CellEndEdit> events.</span></span>

    <span data-ttu-id="a0036-124"><xref:System.Windows.Forms.DataGridView.CellValidating> 事件处理程序可用于确定 `CompanyName` 列中单元格的值是否为空。</span><span class="sxs-lookup"><span data-stu-id="a0036-124">The <xref:System.Windows.Forms.DataGridView.CellValidating> event handler is where you determine whether the value of a cell in the `CompanyName` column is empty.</span></span> <span data-ttu-id="a0036-125">如果单元格值验证失败，请将 <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> 类的 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 属性设置为 "`true`"。</span><span class="sxs-lookup"><span data-stu-id="a0036-125">If the cell value fails validation, set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property of the <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> class to `true`.</span></span> <span data-ttu-id="a0036-126">这会导致 <xref:System.Windows.Forms.DataGridView> 控件阻止光标离开该单元格。</span><span class="sxs-lookup"><span data-stu-id="a0036-126">This causes the <xref:System.Windows.Forms.DataGridView> control to prevent the cursor from leaving the cell.</span></span> <span data-ttu-id="a0036-127">将行的 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 属性设置为解释性字符串。</span><span class="sxs-lookup"><span data-stu-id="a0036-127">Set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to an explanatory string.</span></span> <span data-ttu-id="a0036-128">这会显示一个错误图标，其中包含包含错误文本的工具提示。</span><span class="sxs-lookup"><span data-stu-id="a0036-128">This displays an error icon with a ToolTip that contains the error text.</span></span> <span data-ttu-id="a0036-129">在 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 事件处理程序中，将行的 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 属性设置为空字符串。</span><span class="sxs-lookup"><span data-stu-id="a0036-129">In the <xref:System.Windows.Forms.DataGridView.CellEndEdit> event handler, set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to the empty string.</span></span> <span data-ttu-id="a0036-130">仅当单元格退出编辑模式时，才会发生 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 事件，如果未通过验证，则无法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a0036-130">The <xref:System.Windows.Forms.DataGridView.CellEndEdit> event occurs only when the cell exits edit mode, which it cannot do if it fails validation.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="a0036-131">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="a0036-131">Testing the Application</span></span>

<span data-ttu-id="a0036-132">你现在可以对窗体进行测试，以确保它按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="a0036-132">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="a0036-133">测试窗体</span><span class="sxs-lookup"><span data-stu-id="a0036-133">To test the form</span></span>

- <span data-ttu-id="a0036-134">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0036-134">Compile and run the application.</span></span>

  <span data-ttu-id="a0036-135">您将看到一个 <xref:System.Windows.Forms.DataGridView> 填写 `Customers` 表中的数据。</span><span class="sxs-lookup"><span data-stu-id="a0036-135">You will see a <xref:System.Windows.Forms.DataGridView> filled with data from the `Customers` table.</span></span> <span data-ttu-id="a0036-136">双击 `CompanyName` 列中的某个单元时，可以编辑值。</span><span class="sxs-lookup"><span data-stu-id="a0036-136">When you double-click a cell in the `CompanyName` column, you can edit the value.</span></span> <span data-ttu-id="a0036-137">如果删除所有字符并按 TAB 键退出单元格，则 <xref:System.Windows.Forms.DataGridView> 会阻止你退出。</span><span class="sxs-lookup"><span data-stu-id="a0036-137">If you delete all the characters and hit the TAB key to exit the cell, the <xref:System.Windows.Forms.DataGridView> prevents you from exiting.</span></span> <span data-ttu-id="a0036-138">当您在单元格中键入非空字符串时，<xref:System.Windows.Forms.DataGridView> 控件允许您退出单元。</span><span class="sxs-lookup"><span data-stu-id="a0036-138">When you type a non-empty string into the cell, the <xref:System.Windows.Forms.DataGridView> control lets you exit the cell.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0036-139">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a0036-139">Next Steps</span></span>

<span data-ttu-id="a0036-140">此应用程序可让你基本了解 <xref:System.Windows.Forms.DataGridView> 控件的功能。</span><span class="sxs-lookup"><span data-stu-id="a0036-140">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="a0036-141">可以通过多种方式自定义 <xref:System.Windows.Forms.DataGridView> 控件的外观和行为：</span><span class="sxs-lookup"><span data-stu-id="a0036-141">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="a0036-142">更改边框和标题样式。</span><span class="sxs-lookup"><span data-stu-id="a0036-142">Change border and header styles.</span></span> <span data-ttu-id="a0036-143">有关详细信息，请参阅[如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线样式](change-the-border-and-gridline-styles-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="a0036-143">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="a0036-144">启用或限制 <xref:System.Windows.Forms.DataGridView> 控件的用户输入。</span><span class="sxs-lookup"><span data-stu-id="a0036-144">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a0036-145">有关详细信息，请参阅[如何：防止在 Windows 窗体 Datagridview 控件中添加和删除行](prevent-row-addition-and-deletion-datagridview.md)以及[如何：在 Windows 窗体 DataGridView 控件中将列设为只读](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a0036-145">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="a0036-146">检查用户输入中的数据库相关错误。</span><span class="sxs-lookup"><span data-stu-id="a0036-146">Check user input for database-related errors.</span></span> <span data-ttu-id="a0036-147">有关详细信息，请参阅[演练：处理 Windows 窗体 DataGridView 控件中的数据输入过程中发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="a0036-147">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

- <span data-ttu-id="a0036-148">使用虚拟模式处理非常大的数据集。</span><span class="sxs-lookup"><span data-stu-id="a0036-148">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="a0036-149">有关详细信息，请参阅[演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a0036-149">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="a0036-150">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="a0036-150">Customize the appearance of cells.</span></span> <span data-ttu-id="a0036-151">有关详细信息，请参阅[如何：自定义 Windows 窗体 Datagridview 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)和[如何：在 Windows 窗体 Datagridview 控件中设置字体和颜色样式](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a0036-151">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Font and Color Styles in the Windows Forms DataGridView Control](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0036-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0036-152">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="a0036-153">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="a0036-153">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a0036-154">如何：在 Windows 窗体 DataGridView 控件中验证数据</span><span class="sxs-lookup"><span data-stu-id="a0036-154">How to: Validate Data in the Windows Forms DataGridView Control</span></span>](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a0036-155">演练：处理在 Windows 窗体 DataGridView 控件有数据输入时发生的错误</span><span class="sxs-lookup"><span data-stu-id="a0036-155">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="a0036-156">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="a0036-156">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
