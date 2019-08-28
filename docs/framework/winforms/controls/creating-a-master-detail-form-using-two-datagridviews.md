---
title: 演练：使用两个 Windows 窗体 DataGridView 控件创建主-详细信息窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: 4212c7223aca6a5e7de3189d5f6b2757453cc438
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046094"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="bf65e-102">演练：使用两个 Windows 窗体 DataGridView 控件创建一个主/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="bf65e-102">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>

<span data-ttu-id="bf65e-103">使用<xref:System.Windows.Forms.DataGridView>控件的最常见方案之一是*主/详细信息*窗体, 其中显示两个数据库表之间的父/子关系。</span><span class="sxs-lookup"><span data-stu-id="bf65e-103">One of the most common scenarios for using the <xref:System.Windows.Forms.DataGridView> control is the *master/detail* form, in which a parent/child relationship between two database tables is displayed.</span></span> <span data-ttu-id="bf65e-104">如果选择主表中的行, 则会将详细信息表更新为相应的子数据。</span><span class="sxs-lookup"><span data-stu-id="bf65e-104">Selecting rows in the master table causes the detail table to update with the corresponding child data.</span></span>

<span data-ttu-id="bf65e-105">使用<xref:System.Windows.Forms.DataGridView> 控件<xref:System.Windows.Forms.BindingSource>和组件之间的交互可以轻松实现主/详细信息窗体。</span><span class="sxs-lookup"><span data-stu-id="bf65e-105">Implementing a master/detail form is easy using the interaction between the <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="bf65e-106">在本演练中, 您将使用两个<xref:System.Windows.Forms.DataGridView>控件和两个<xref:System.Windows.Forms.BindingSource>组件生成窗体。</span><span class="sxs-lookup"><span data-stu-id="bf65e-106">In this walkthrough, you will build the form using two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="bf65e-107">此窗体将在 Northwind SQL Server 示例数据库中显示两个相关`Customers`的`Orders`表: 和。</span><span class="sxs-lookup"><span data-stu-id="bf65e-107">The form will show two related tables in the Northwind SQL Server sample database: `Customers` and `Orders`.</span></span> <span data-ttu-id="bf65e-108">完成后, 您将获得一个窗体, 其中显示了主<xref:System.Windows.Forms.DataGridView>数据库中的所有客户以及所选客户在详细信息<xref:System.Windows.Forms.DataGridView>中的所有订单。</span><span class="sxs-lookup"><span data-stu-id="bf65e-108">When you are finished, you will have a form that shows all the customers in the database in the master <xref:System.Windows.Forms.DataGridView> and all the orders for the selected customer in the detail <xref:System.Windows.Forms.DataGridView>.</span></span>

<span data-ttu-id="bf65e-109">要将本主题中的代码作为单个列表进行复制，请参阅[如何：使用两个 Windows 窗体 DataGridView 控件](create-a-master-detail-form-using-two-datagridviews.md)创建主窗体/详细信息窗体。</span><span class="sxs-lookup"><span data-stu-id="bf65e-109">To copy the code in this topic as a single listing, see [How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls](create-a-master-detail-form-using-two-datagridviews.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf65e-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="bf65e-110">Prerequisites</span></span>

<span data-ttu-id="bf65e-111">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="bf65e-111">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="bf65e-112">访问包含 Northwind SQL Server 示例数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="bf65e-112">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="bf65e-113">创建窗体</span><span class="sxs-lookup"><span data-stu-id="bf65e-113">Creating the form</span></span>

#### <a name="to-create-a-masterdetail-form"></a><span data-ttu-id="bf65e-114">创建主窗体/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="bf65e-114">To create a master/detail form</span></span>

1. <span data-ttu-id="bf65e-115">创建一个从派生的<xref:System.Windows.Forms.Form>类, 其中包含两个<xref:System.Windows.Forms.DataGridView>控件<xref:System.Windows.Forms.BindingSource>和两个组件。</span><span class="sxs-lookup"><span data-stu-id="bf65e-115">Create a class that derives from <xref:System.Windows.Forms.Form> and contains two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="bf65e-116">下面的代码提供基本的窗体初始化并`Main`包含方法。</span><span class="sxs-lookup"><span data-stu-id="bf65e-116">The following code provides basic form initialization and includes a `Main` method.</span></span> <span data-ttu-id="bf65e-117">如果你使用 Visual Studio 设计器来创建窗体, 则可以使用设计器生成的代码而不是此代码, 但请务必使用此处的变量声明中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="bf65e-117">If you use the Visual Studio designer to create your form, you can use the designer generated code instead of this code, but be sure to use the names shown in the variable declarations here.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. <span data-ttu-id="bf65e-118">在窗体的类定义中实现一个方法, 用于处理连接到数据库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bf65e-118">Implement a method in your form's class definition for handling the detail of connecting to the database.</span></span> <span data-ttu-id="bf65e-119">此示例使用一个`GetData`方法, 该方法<xref:System.Data.DataSet>填充对象, 将<xref:System.Data.DataRelation>对象添加到数据集, 并绑定这些<xref:System.Windows.Forms.BindingSource>组件。</span><span class="sxs-lookup"><span data-stu-id="bf65e-119">This example uses a `GetData` method that populates a <xref:System.Data.DataSet> object, adds a <xref:System.Data.DataRelation> object to the data set, and binds the <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="bf65e-120">请确保将 `connectionString` 变量设置为适合数据库的值。</span><span class="sxs-lookup"><span data-stu-id="bf65e-120">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bf65e-121">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="bf65e-121">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="bf65e-122">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="bf65e-122">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="bf65e-123">有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="bf65e-123">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. <span data-ttu-id="bf65e-124">实现<xref:System.Windows.Forms.Form.Load>窗体事件的处理程序, 该处理程序<xref:System.Windows.Forms.DataGridView>将控件绑定<xref:System.Windows.Forms.BindingSource>到组件并调用`GetData`方法。</span><span class="sxs-lookup"><span data-stu-id="bf65e-124">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that binds the <xref:System.Windows.Forms.DataGridView> controls to the <xref:System.Windows.Forms.BindingSource> components and calls the `GetData` method.</span></span> <span data-ttu-id="bf65e-125">下面的示例包含可调整列<xref:System.Windows.Forms.DataGridView>大小以适应显示的数据的代码。</span><span class="sxs-lookup"><span data-stu-id="bf65e-125">The following example includes code that resizes <xref:System.Windows.Forms.DataGridView> columns to fit the displayed data.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a><span data-ttu-id="bf65e-126">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="bf65e-126">Testing the Application</span></span>

<span data-ttu-id="bf65e-127">你现在可以对窗体进行测试, 以确保它按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="bf65e-127">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="bf65e-128">测试窗体</span><span class="sxs-lookup"><span data-stu-id="bf65e-128">To test the form</span></span>

- <span data-ttu-id="bf65e-129">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf65e-129">Compile and run the application.</span></span>

  <span data-ttu-id="bf65e-130">您将看到两<xref:System.Windows.Forms.DataGridView>个控件, 一个在对方。</span><span class="sxs-lookup"><span data-stu-id="bf65e-130">You will see two <xref:System.Windows.Forms.DataGridView> controls, one above the other.</span></span> <span data-ttu-id="bf65e-131">在顶部是 Northwind `Customers`表中的客户, 底部是对应于所选客户的。 `Orders`</span><span class="sxs-lookup"><span data-stu-id="bf65e-131">On top are the customers from the Northwind `Customers` table, and at the bottom are the `Orders` corresponding to the selected customer.</span></span> <span data-ttu-id="bf65e-132">选择上部<xref:System.Windows.Forms.DataGridView>的不同行时, 会相应地<xref:System.Windows.Forms.DataGridView>更改的内容。</span><span class="sxs-lookup"><span data-stu-id="bf65e-132">As you select different rows in the upper <xref:System.Windows.Forms.DataGridView>, the contents of the lower <xref:System.Windows.Forms.DataGridView> change accordingly.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf65e-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bf65e-133">Next Steps</span></span>

<span data-ttu-id="bf65e-134">此应用程序可让你对<xref:System.Windows.Forms.DataGridView>控件的功能有一个基本的了解。</span><span class="sxs-lookup"><span data-stu-id="bf65e-134">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="bf65e-135">可以通过多种方式自定义<xref:System.Windows.Forms.DataGridView>控件的外观和行为:</span><span class="sxs-lookup"><span data-stu-id="bf65e-135">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="bf65e-136">更改边框和标题样式。</span><span class="sxs-lookup"><span data-stu-id="bf65e-136">Change border and header styles.</span></span> <span data-ttu-id="bf65e-137">有关详细信息，请参阅[如何：更改 Windows 窗体 DataGridView 控件](change-the-border-and-gridline-styles-in-the-datagrid.md)中的边框和网格线样式。</span><span class="sxs-lookup"><span data-stu-id="bf65e-137">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="bf65e-138">启用或限制控件的<xref:System.Windows.Forms.DataGridView>用户输入。</span><span class="sxs-lookup"><span data-stu-id="bf65e-138">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bf65e-139">有关详细信息，请参阅[如何：禁止 Windows 窗体 DataGridView 控件](prevent-row-addition-and-deletion-datagridview.md)中添加和删除行, 以及[如何:在 Windows 窗体 DataGridView 控件](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)中将列设为只读。</span><span class="sxs-lookup"><span data-stu-id="bf65e-139">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="bf65e-140">验证控件的<xref:System.Windows.Forms.DataGridView>用户输入。</span><span class="sxs-lookup"><span data-stu-id="bf65e-140">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bf65e-141">有关详细信息，请参见[演练：正在验证 Windows 窗体 DataGridView 控件](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)中的数据。</span><span class="sxs-lookup"><span data-stu-id="bf65e-141">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="bf65e-142">使用虚拟模式处理非常大的数据集。</span><span class="sxs-lookup"><span data-stu-id="bf65e-142">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="bf65e-143">有关详细信息，请参见[演练：在 Windows 窗体 DataGridView 控件](implementing-virtual-mode-wf-datagridview-control.md)中实现虚拟模式。</span><span class="sxs-lookup"><span data-stu-id="bf65e-143">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="bf65e-144">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="bf65e-144">Customize the appearance of cells.</span></span> <span data-ttu-id="bf65e-145">有关详细信息，请参阅[如何：自定义 Windows 窗体 DataGridView 控件](customize-the-appearance-of-cells-in-the-datagrid.md)中单元格的外观, 以及[如何执行以下操作:设置 Windows 窗体 DataGridView 控件](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)的默认单元格样式。</span><span class="sxs-lookup"><span data-stu-id="bf65e-145">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf65e-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf65e-146">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="bf65e-147">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="bf65e-147">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bf65e-148">如何：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="bf65e-148">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](create-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="bf65e-149">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="bf65e-149">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
