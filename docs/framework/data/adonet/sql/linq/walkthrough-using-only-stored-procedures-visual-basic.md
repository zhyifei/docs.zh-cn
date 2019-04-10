---
title: 演练：仅使用存储过程 (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 1527e3b4b614d4e700ae0c2c0fc555e14c7bc8d2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314823"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a><span data-ttu-id="d0078-102">演练：仅使用存储过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0078-102">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>
<span data-ttu-id="d0078-103">本演练提供了通过仅使用存储过程来访问数据的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 基本端对端方案。</span><span class="sxs-lookup"><span data-stu-id="d0078-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by using stored procedures only.</span></span> <span data-ttu-id="d0078-104">数据库管理员经常使用此方法来限制数据存储的访问方式。</span><span class="sxs-lookup"><span data-stu-id="d0078-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0078-105">您还可以在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序中使用存储过程来重写默认行为，尤其是 `Create`、`Update` 和 `Delete` 进程的默认行为。</span><span class="sxs-lookup"><span data-stu-id="d0078-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="d0078-106">有关详细信息，请参阅[自定义插入、 更新和删除操作](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="d0078-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="d0078-107">对于本演练的目的，你将使用已映射到 Northwind 示例数据库中的存储过程的两种方法：CustOrdersDetail 和 CustOrderHist。</span><span class="sxs-lookup"><span data-stu-id="d0078-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="d0078-108">此映射发生在运行 SqlMetal 命令行工具生成的 Visual Basic 文件。</span><span class="sxs-lookup"><span data-stu-id="d0078-108">The mapping occurs when you run the SqlMetal command-line tool to generate a Visual Basic file.</span></span> <span data-ttu-id="d0078-109">有关更多信息，请参见本演练后面的“先决条件”一节。</span><span class="sxs-lookup"><span data-stu-id="d0078-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="d0078-110">本演练不依赖于[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d0078-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="d0078-111">使用 Visual Studio 的开发人员还可以使用[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]实现存储的过程功能。</span><span class="sxs-lookup"><span data-stu-id="d0078-111">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="d0078-112">请参阅[LINQ to SQL 工具在 Visual Studio 中](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)。</span><span class="sxs-lookup"><span data-stu-id="d0078-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="d0078-113">本演练是使用 Visual Basic 开发设置编写的。</span><span class="sxs-lookup"><span data-stu-id="d0078-113">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d0078-114">系统必备</span><span class="sxs-lookup"><span data-stu-id="d0078-114">Prerequisites</span></span>  
 <span data-ttu-id="d0078-115">本演练需要如下内容：</span><span class="sxs-lookup"><span data-stu-id="d0078-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="d0078-116">本演练使用专用文件夹（“c:\linqtest3”）来保存文件。</span><span class="sxs-lookup"><span data-stu-id="d0078-116">This walkthrough uses a dedicated folder ("c:\linqtest3") to hold files.</span></span> <span data-ttu-id="d0078-117">请在开始本演练前创建此文件夹。</span><span class="sxs-lookup"><span data-stu-id="d0078-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="d0078-118">Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="d0078-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="d0078-119">如果您的开发计算机上没有此数据库，您可以从 Microsoft 下载网站下载它。</span><span class="sxs-lookup"><span data-stu-id="d0078-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="d0078-120">有关说明，请参阅[下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="d0078-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="d0078-121">下载此数据库后，请将 northwnd.mdf 文件复制到 c:\linqtest3 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d0078-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest3 folder.</span></span>  
  
-   <span data-ttu-id="d0078-122">从 Northwind 数据库生成的 Visual Basic 代码文件。</span><span class="sxs-lookup"><span data-stu-id="d0078-122">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="d0078-123">本演练是通过使用 SqlMetal 工具以及如下命令行编写的：</span><span class="sxs-lookup"><span data-stu-id="d0078-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     **<span data-ttu-id="d0078-124">sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize</span><span class="sxs-lookup"><span data-stu-id="d0078-124">sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize</span></span>**  
  
     <span data-ttu-id="d0078-125">有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="d0078-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d0078-126">概述</span><span class="sxs-lookup"><span data-stu-id="d0078-126">Overview</span></span>  
 <span data-ttu-id="d0078-127">本演练由六项主要任务组成：</span><span class="sxs-lookup"><span data-stu-id="d0078-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="d0078-128">设置[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Visual Studio 中的解决方案。</span><span class="sxs-lookup"><span data-stu-id="d0078-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="d0078-129">将 System.Data.Linq 程序集添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="d0078-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="d0078-130">向项目添加数据库代码文件。</span><span class="sxs-lookup"><span data-stu-id="d0078-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="d0078-131">创建与数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="d0078-131">Creating a connection to the database.</span></span>  
  
-   <span data-ttu-id="d0078-132">设置用户界面。</span><span class="sxs-lookup"><span data-stu-id="d0078-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="d0078-133">运行和测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="d0078-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="d0078-134">创建 LINQ to SQL 解决方案</span><span class="sxs-lookup"><span data-stu-id="d0078-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="d0078-135">在此第一个任务中，创建一个包含必要的引用，生成并运行的 Visual Studio 解决方案[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="d0078-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="d0078-136">创建 LINQ to SQL 解决方案</span><span class="sxs-lookup"><span data-stu-id="d0078-136">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="d0078-137">在 Visual Studio**文件**菜单上，单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="d0078-137">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="d0078-138">在 **“新建项目”** 对话框中的 **“项目类型”** 窗格中，展开 **“Visual Basic”**，然后单击 **“Windows”**。</span><span class="sxs-lookup"><span data-stu-id="d0078-138">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3. <span data-ttu-id="d0078-139">在 **“模板”** 窗格中，单击 **“Windows 窗体应用程序”**。</span><span class="sxs-lookup"><span data-stu-id="d0078-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4. <span data-ttu-id="d0078-140">在中**名称**框中，键入**SprocOnlyApp**。</span><span class="sxs-lookup"><span data-stu-id="d0078-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5. <span data-ttu-id="d0078-141">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d0078-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="d0078-142">Windows 窗体设计器即会打开。</span><span class="sxs-lookup"><span data-stu-id="d0078-142">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="d0078-143">添加 LINQ to SQL 程序集引用</span><span class="sxs-lookup"><span data-stu-id="d0078-143">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="d0078-144">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 程序集未包含在标准的 Windows 窗体应用程序模板中。</span><span class="sxs-lookup"><span data-stu-id="d0078-144">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="d0078-145">您将需要按照以下步骤中的说明自行添加此程序集：</span><span class="sxs-lookup"><span data-stu-id="d0078-145">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="d0078-146">添加 System.Data.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="d0078-146">To add System.Data.Linq.dll</span></span>  
  
1. <span data-ttu-id="d0078-147">在中**解决方案资源管理器**，单击**显示所有文件**。</span><span class="sxs-lookup"><span data-stu-id="d0078-147">In **Solution Explorer**, click **Show All Files**.</span></span>  
  
2. <span data-ttu-id="d0078-148">在中**解决方案资源管理器**，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d0078-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
3. <span data-ttu-id="d0078-149">在中**添加引用**对话框中，单击 **.NET**，单击 System.Data.Linq 程序集，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d0078-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d0078-150">此程序集即被添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="d0078-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="d0078-151">将 Northwind 代码文件添加到项目</span><span class="sxs-lookup"><span data-stu-id="d0078-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="d0078-152">此步骤假定你已使用 SqlMetal 工具从 Northwind 示例数据库生成代码文件。</span><span class="sxs-lookup"><span data-stu-id="d0078-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="d0078-153">有关更多信息，请参见本演练前面部分的“先决条件”一节。</span><span class="sxs-lookup"><span data-stu-id="d0078-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="d0078-154">将 northwind 代码文件添加到项目</span><span class="sxs-lookup"><span data-stu-id="d0078-154">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="d0078-155">上**项目**菜单上，单击**添加现有项**。</span><span class="sxs-lookup"><span data-stu-id="d0078-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="d0078-156">在中**添加现有项**对话框中，移动到 c:\linqtest3\northwind.vb，然后依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="d0078-156">In the **Add Existing Item** dialog box, move to c:\linqtest3\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="d0078-157">northwind.vb 文件即被添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="d0078-157">The northwind.vb file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="d0078-158">创建数据库连接</span><span class="sxs-lookup"><span data-stu-id="d0078-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="d0078-159">在此步骤中，您要定义与 Northwind 示例数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="d0078-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="d0078-160">本演练使用“c:\linqtest3\northwnd.mdf”作为路径。</span><span class="sxs-lookup"><span data-stu-id="d0078-160">This walkthrough uses "c:\linqtest3\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="d0078-161">创建数据库连接</span><span class="sxs-lookup"><span data-stu-id="d0078-161">To create the database connection</span></span>  
  
1. <span data-ttu-id="d0078-162">在中**解决方案资源管理器**，右键单击**Form1.vb**，然后单击**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="d0078-162">In **Solution Explorer**, right-click **Form1.vb**, and then click **View Code**.</span></span>  
  
     `Class Form1` <span data-ttu-id="d0078-163">将显示在代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="d0078-163">appears in the code editor.</span></span>  
  
2. <span data-ttu-id="d0078-164">在 `Form1` 代码块中键入如下代码：</span><span class="sxs-lookup"><span data-stu-id="d0078-164">Type the following code into the `Form1` code block:</span></span>  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="d0078-165">设置用户界面</span><span class="sxs-lookup"><span data-stu-id="d0078-165">Setting up the User Interface</span></span>  
 <span data-ttu-id="d0078-166">在此任务中，你要创建用户界面，供用户执行存储过程以访问数据库中的数据之用。</span><span class="sxs-lookup"><span data-stu-id="d0078-166">In this task you create an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="d0078-167">在您按照本演练开发的应用程序中，用户可以只使用嵌入在此应用程序中的存储过程来访问数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="d0078-167">In the application that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="d0078-168">设置用户界面</span><span class="sxs-lookup"><span data-stu-id="d0078-168">To set up the user interface</span></span>  
  
1. <span data-ttu-id="d0078-169">返回 Windows 窗体设计器 (**Form1.vb[Design]**)。</span><span class="sxs-lookup"><span data-stu-id="d0078-169">Return to the Windows Forms Designer (**Form1.vb[Design]**).</span></span>  
  
2. <span data-ttu-id="d0078-170">在 **“视图”** 菜单上单击 **“工具箱”**。</span><span class="sxs-lookup"><span data-stu-id="d0078-170">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="d0078-171">工具箱即会打开。</span><span class="sxs-lookup"><span data-stu-id="d0078-171">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0078-172">单击**自动隐藏**图钉，以使工具箱保持打开状态，而执行的其余步骤在本部分中。</span><span class="sxs-lookup"><span data-stu-id="d0078-172">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3. <span data-ttu-id="d0078-173">将两个按钮、 两个文本框和两个标签拖从工具箱中拖动**Form1**。</span><span class="sxs-lookup"><span data-stu-id="d0078-173">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="d0078-174">按照附图排列这些控件。</span><span class="sxs-lookup"><span data-stu-id="d0078-174">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="d0078-175">展开**Form1** ，以便控件更便于显示。</span><span class="sxs-lookup"><span data-stu-id="d0078-175">Expand **Form1** so that the controls fit easily.</span></span>  
  
4. <span data-ttu-id="d0078-176">右键单击**Label1**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d0078-176">Right-click **Label1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="d0078-177">更改**文本**属性从**Label1**到**Enter OrderID:**。</span><span class="sxs-lookup"><span data-stu-id="d0078-177">Change the **Text** property from **Label1** to **Enter OrderID:**.</span></span>  
  
6. <span data-ttu-id="d0078-178">在相同的方式对**Label2**，更改**文本**属性从**Label2**到**Enter CustomerID:**。</span><span class="sxs-lookup"><span data-stu-id="d0078-178">In the same way for **Label2**, change the **Text** property from **Label2** to **Enter CustomerID:**.</span></span>  
  
7. <span data-ttu-id="d0078-179">同样，在更改**文本**属性**Button1**到**订单详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0078-179">In the same way, change the **Text** property for **Button1** to **Order Details**.</span></span>  
  
8. <span data-ttu-id="d0078-180">更改**文本**属性**Button2**到**订单历史记录**。</span><span class="sxs-lookup"><span data-stu-id="d0078-180">Change the **Text** property for **Button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="d0078-181">将这些按钮控件加宽，以使所有文本均可见。</span><span class="sxs-lookup"><span data-stu-id="d0078-181">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="d0078-182">处理按钮单击</span><span class="sxs-lookup"><span data-stu-id="d0078-182">To handle button clicks</span></span>  
  
1. <span data-ttu-id="d0078-183">双击**订单详细信息**上**Form1**创建`Button1`事件处理程序并打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="d0078-183">Double-click **Order Details** on **Form1** to create the `Button1` event handler and open the code editor.</span></span>  
  
2. <span data-ttu-id="d0078-184">将如下代码键入到 `Button1` 处理程序中：</span><span class="sxs-lookup"><span data-stu-id="d0078-184">Type the following code into the `Button1` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. <span data-ttu-id="d0078-185">现在双击**Button2**若要创建的 Form1 上`Button2`事件处理程序并打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="d0078-185">Now double-click **Button2** on Form1 to create the `Button2` event handler and open the code editor.</span></span>  
  
4. <span data-ttu-id="d0078-186">将如下代码键入到 `Button2` 处理程序中：</span><span class="sxs-lookup"><span data-stu-id="d0078-186">Type the following code into the `Button2` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="d0078-187">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="d0078-187">Testing the Application</span></span>  
 <span data-ttu-id="d0078-188">现在，可以开始测试您的应用程序了。</span><span class="sxs-lookup"><span data-stu-id="d0078-188">Now it is time to test your application.</span></span> <span data-ttu-id="d0078-189">请注意，您可对数据存储施加的影响仅限于这两个存储过程能够执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d0078-189">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="d0078-190">这些操作是要根据您输入的所有 orderID 返回相应订单包括的产品，或根据您输入的所有 CustomerID 返回相应客户的产品订购历史记录。</span><span class="sxs-lookup"><span data-stu-id="d0078-190">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="d0078-191">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="d0078-191">To test the application</span></span>  
  
1. <span data-ttu-id="d0078-192">按 F5 开始调试。</span><span class="sxs-lookup"><span data-stu-id="d0078-192">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="d0078-193">此时将显示 Form1。</span><span class="sxs-lookup"><span data-stu-id="d0078-193">Form1 appears.</span></span>  
  
2. <span data-ttu-id="d0078-194">在中**Enter OrderID**框中，键入**10249** ，然后单击**Order Details**。</span><span class="sxs-lookup"><span data-stu-id="d0078-194">In the **Enter OrderID** box, type **10249** and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="d0078-195">随即会显示一个消息框，其中列出了 10249 号订单中所包括的产品。</span><span class="sxs-lookup"><span data-stu-id="d0078-195">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="d0078-196">单击**确定**以关闭消息框。</span><span class="sxs-lookup"><span data-stu-id="d0078-196">Click **OK** to close the message box.</span></span>  
  
3. <span data-ttu-id="d0078-197">在中**输入 CustomerID**框中，键入`ALFKI`，然后单击**订单历史记录**。</span><span class="sxs-lookup"><span data-stu-id="d0078-197">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="d0078-198">随即会显示一个消息框，其中列出了 ALFKI 客户的订单历史记录。</span><span class="sxs-lookup"><span data-stu-id="d0078-198">A message box lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="d0078-199">单击**确定**以关闭消息框。</span><span class="sxs-lookup"><span data-stu-id="d0078-199">Click **OK** to close the message box.</span></span>  
  
4. <span data-ttu-id="d0078-200">在中**Enter OrderID**框中，键入`123`，然后单击**订单详细信息**。</span><span class="sxs-lookup"><span data-stu-id="d0078-200">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="d0078-201">随即会显示一个消息框，其中显示“无结果”。</span><span class="sxs-lookup"><span data-stu-id="d0078-201">A message box displays "No results."</span></span>  
  
     <span data-ttu-id="d0078-202">单击**确定**以关闭消息框。</span><span class="sxs-lookup"><span data-stu-id="d0078-202">Click **OK** to close the message box.</span></span>  
  
5. <span data-ttu-id="d0078-203">上**调试**菜单上，单击**停止调试**。</span><span class="sxs-lookup"><span data-stu-id="d0078-203">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="d0078-204">调试会话即会关闭。</span><span class="sxs-lookup"><span data-stu-id="d0078-204">The debug session closes.</span></span>  
  
6. <span data-ttu-id="d0078-205">如果您已试验完毕，则可以单击**关闭项目**上**文件**菜单中，并在提示时保存你的项目。</span><span class="sxs-lookup"><span data-stu-id="d0078-205">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d0078-206">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d0078-206">Next Steps</span></span>  
 <span data-ttu-id="d0078-207">您可以通过做一些更改来增强此项目的功能。</span><span class="sxs-lookup"><span data-stu-id="d0078-207">You can enhance this project by making some changes.</span></span> <span data-ttu-id="d0078-208">例如，您可以在列表框中列出可用的存储过程，供用户选择要执行哪些过程。</span><span class="sxs-lookup"><span data-stu-id="d0078-208">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="d0078-209">您还可以将报告的输出以流的方式传输到文本文件。</span><span class="sxs-lookup"><span data-stu-id="d0078-209">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0078-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0078-210">See also</span></span>

- [<span data-ttu-id="d0078-211">通过演练学习</span><span class="sxs-lookup"><span data-stu-id="d0078-211">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [<span data-ttu-id="d0078-212">存储过程</span><span class="sxs-lookup"><span data-stu-id="d0078-212">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
