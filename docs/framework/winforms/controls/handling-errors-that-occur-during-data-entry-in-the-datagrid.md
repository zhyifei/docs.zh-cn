---
title: "演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误"
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
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c602af6799da57fec904c87da7bed77c0040eff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="1f4e8-102">演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误</span><span class="sxs-lookup"><span data-stu-id="1f4e8-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1f4e8-103">处理来自基础数据存储区的错误是为数据输入应用程序的必需的功能。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="1f4e8-104">Windows 窗体<xref:System.Windows.Forms.DataGridView>控件轻松这通过公开<xref:System.Windows.Forms.DataGridView.DataError>事件，当数据存储区检测到违反了约束或违反的业务规则时引发。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>  
  
 <span data-ttu-id="1f4e8-105">在本演练中，你将检索行从`Customers`Northwind 示例数据库中表，然后将其显示在<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1f4e8-106">当重复`CustomerID`值检测到一个新行或编辑现有行，<xref:System.Windows.Forms.DataGridView.DataError>事件会发生，这将通过显示处理<xref:System.Windows.Forms.MessageBox>描述该异常。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>  
  
 <span data-ttu-id="1f4e8-107">若要将代码复制本主题中的一个单独的清单，请参阅[如何： 处理错误，会出现在数据输入在 Windows 窗体 DataGridView 控件中](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1f4e8-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="1f4e8-108">Prerequisites</span></span>  
 <span data-ttu-id="1f4e8-109">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="1f4e8-109">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="1f4e8-110">到 Northwind SQL Server 示例数据库的服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-110">Access to a server that has the Northwind SQL Server sample database.</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="1f4e8-111">创建窗体</span><span class="sxs-lookup"><span data-stu-id="1f4e8-111">Creating the Form</span></span>  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="1f4e8-112">处理 DataGridView 控件中的数据输入错误</span><span class="sxs-lookup"><span data-stu-id="1f4e8-112">To handle data-entry errors in the DataGridView control</span></span>  
  
1.  <span data-ttu-id="1f4e8-113">创建一个类，派生自<xref:System.Windows.Forms.Form>和包含<xref:System.Windows.Forms.DataGridView>控件和<xref:System.Windows.Forms.BindingSource>组件。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     <span data-ttu-id="1f4e8-114">下面的代码示例提供了基本的初始化，并且包含`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-114">The following code example provides basic initialization and includes a `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  <span data-ttu-id="1f4e8-115">实现用于处理连接到数据库的详细信息窗体的类定义中的方法。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>  
  
     <span data-ttu-id="1f4e8-116">此代码示例使用`GetData`返回填充的方法<xref:System.Data.DataTable>对象。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="1f4e8-117">请确保你设置`connectionString`变量为适合于你的数据库的值。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1f4e8-118">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="1f4e8-119">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="1f4e8-120">有关详细信息，请参阅[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-120">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  <span data-ttu-id="1f4e8-121">实现你的窗体的处理<xref:System.Windows.Forms.Form.Load>初始化的事件<xref:System.Windows.Forms.DataGridView>和<xref:System.Windows.Forms.BindingSource>和数据绑定设置。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  <span data-ttu-id="1f4e8-122">处理<xref:System.Windows.Forms.DataGridView.DataError>上的事件<xref:System.Windows.Forms.DataGridView>。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="1f4e8-123">如果错误的上下文，提交操作显示中的错误<xref:System.Windows.Forms.MessageBox>。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="1f4e8-124">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="1f4e8-124">Testing the Application</span></span>  
 <span data-ttu-id="1f4e8-125">你现在可以测试窗体，以确保其行为与预期相同。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-125">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="1f4e8-126">若要测试窗体</span><span class="sxs-lookup"><span data-stu-id="1f4e8-126">To test the form</span></span>  
  
-   <span data-ttu-id="1f4e8-127">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-127">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="1f4e8-128">你将看到<xref:System.Windows.Forms.DataGridView>控件填充 Customers 表中的数据。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="1f4e8-129">如果输入的重复值`CustomerID`和提交编辑单元格的值将自动恢复，你将看到<xref:System.Windows.Forms.MessageBox>显示数据输入错误。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1f4e8-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1f4e8-130">Next Steps</span></span>  
 <span data-ttu-id="1f4e8-131">此应用程序提供一个基本的了解<xref:System.Windows.Forms.DataGridView>控件的功能。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="1f4e8-132">你可以自定义的外观和行为<xref:System.Windows.Forms.DataGridView>控制以下几种方式：</span><span class="sxs-lookup"><span data-stu-id="1f4e8-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="1f4e8-133">更改边框和标头的样式。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-133">Change border and header styles.</span></span> <span data-ttu-id="1f4e8-134">有关详细信息，请参阅[如何： 更改边框和网格线在 Windows 窗体 DataGridView 控件中的样式](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="1f4e8-135">允许或限制用户输入到<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1f4e8-136">有关详细信息，请参阅[如何： 防止添加和删除行在 Windows 窗体 DataGridView 控件中](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)，和[如何： 在 Windows 窗体 DataGridView 控件中使列成为只读](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="1f4e8-137">验证用户输入到<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="1f4e8-138">有关详细信息，请参阅[演练： 验证 Windows 窗体 DataGridView 控件中的数据](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="1f4e8-139">处理非常大的数据集使用的虚拟模式。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="1f4e8-140">有关详细信息，请参阅[演练： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="1f4e8-141">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-141">Customize the appearance of cells.</span></span> <span data-ttu-id="1f4e8-142">有关详细信息，请参阅[如何： 自定义 Windows 窗体 DataGridView 控件中的单元外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)和[如何： 设置 Windows 窗体 DataGridView 控件的默认单元格样式](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1f4e8-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f4e8-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f4e8-143">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="1f4e8-144">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="1f4e8-144">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1f4e8-145">如何：处理在 Windows 窗体 DataGridView 控件有数据输入时发生的错误</span><span class="sxs-lookup"><span data-stu-id="1f4e8-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [<span data-ttu-id="1f4e8-146">演练：在 Windows 窗体 DataGridView 控件中验证数据</span><span class="sxs-lookup"><span data-stu-id="1f4e8-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1f4e8-147">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="1f4e8-147">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
