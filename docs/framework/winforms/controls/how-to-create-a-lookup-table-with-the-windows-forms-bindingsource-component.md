---
title: 如何：使用 Windows 窗体 BindingSource 组件创建查找表
ms.date: 03/30/2017
helpviewer_keywords:
- lookup tables
- tables [Windows Forms], creating lookup tables
- BindingSource component [Windows Forms], creating a lookup table
- BindingSource component [Windows Forms], examples
ms.assetid: 622fce80-879d-44be-abbf-8350ec22ca2b
ms.openlocfilehash: 79459364fba51e8e10194a5e3681d6384beb16a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539891"
---
# <a name="how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="958c3-102">如何：使用 Windows 窗体 BindingSource 组件创建查找表</span><span class="sxs-lookup"><span data-stu-id="958c3-102">How to: Create a Lookup Table with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="958c3-103">查找表是一种数据表，其中有一列显示另一个相关表的记录数据。</span><span class="sxs-lookup"><span data-stu-id="958c3-103">A lookup table is a table of data that has a column that displays data from records in a related table.</span></span> <span data-ttu-id="958c3-104">在以下过程中，<xref:System.Windows.Forms.ComboBox> 控件可用于显示具有从父表到子表的外键关系的字段。</span><span class="sxs-lookup"><span data-stu-id="958c3-104">In the following procedures, a <xref:System.Windows.Forms.ComboBox> control is used to display the field with the foreign-key relationship from the parent to the child table.</span></span>  
  
 <span data-ttu-id="958c3-105">为了帮助实现这两个表和这种关系的可视化，下面是一个父表和子表的示例：</span><span class="sxs-lookup"><span data-stu-id="958c3-105">To help visualize these two tables and this relationship, here is an example of a parent and child table:</span></span>  
  
 <span data-ttu-id="958c3-106">CustomersTable（父表）</span><span class="sxs-lookup"><span data-stu-id="958c3-106">CustomersTable (parent table)</span></span>  
  
|<span data-ttu-id="958c3-107">CustomerID</span><span class="sxs-lookup"><span data-stu-id="958c3-107">CustomerID</span></span>|<span data-ttu-id="958c3-108">CustomerName</span><span class="sxs-lookup"><span data-stu-id="958c3-108">CustomerName</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="958c3-109">712</span><span class="sxs-lookup"><span data-stu-id="958c3-109">712</span></span>|<span data-ttu-id="958c3-110">Paul Koch</span><span class="sxs-lookup"><span data-stu-id="958c3-110">Paul Koch</span></span>|  
|<span data-ttu-id="958c3-111">713</span><span class="sxs-lookup"><span data-stu-id="958c3-111">713</span></span>|<span data-ttu-id="958c3-112">Tamara Johnston</span><span class="sxs-lookup"><span data-stu-id="958c3-112">Tamara Johnston</span></span>|  
  
 <span data-ttu-id="958c3-113">OrdersTable（子表）</span><span class="sxs-lookup"><span data-stu-id="958c3-113">OrdersTable (child table)</span></span>  
  
|<span data-ttu-id="958c3-114">OrderID</span><span class="sxs-lookup"><span data-stu-id="958c3-114">OrderID</span></span>|<span data-ttu-id="958c3-115">OrderDate</span><span class="sxs-lookup"><span data-stu-id="958c3-115">OrderDate</span></span>|<span data-ttu-id="958c3-116">CustomerID</span><span class="sxs-lookup"><span data-stu-id="958c3-116">CustomerID</span></span>|  
|-------------|---------------|----------------|  
|<span data-ttu-id="958c3-117">903</span><span class="sxs-lookup"><span data-stu-id="958c3-117">903</span></span>|<span data-ttu-id="958c3-118">2004 年 2 月 12 日</span><span class="sxs-lookup"><span data-stu-id="958c3-118">February 12, 2004</span></span>|<span data-ttu-id="958c3-119">712</span><span class="sxs-lookup"><span data-stu-id="958c3-119">712</span></span>|  
|<span data-ttu-id="958c3-120">904</span><span class="sxs-lookup"><span data-stu-id="958c3-120">904</span></span>|<span data-ttu-id="958c3-121">2004 年 2 月 13 日</span><span class="sxs-lookup"><span data-stu-id="958c3-121">February 13, 2004</span></span>|<span data-ttu-id="958c3-122">713</span><span class="sxs-lookup"><span data-stu-id="958c3-122">713</span></span>|  
  
 <span data-ttu-id="958c3-123">在这种情况下，表 CustomersTable 存储了想要显示和保存的实际信息。</span><span class="sxs-lookup"><span data-stu-id="958c3-123">In this scenario, one table, CustomersTable, stores the actual information you want to display and save.</span></span> <span data-ttu-id="958c3-124">但为了节省空间，此表省略了可增加清晰度的数据。</span><span class="sxs-lookup"><span data-stu-id="958c3-124">But to save space, the table leaves out data that adds clarity.</span></span> <span data-ttu-id="958c3-125">另一张表 OrdersTable 只包含有关哪个客户 ID 号等同于哪个订单日期和订单 ID 的表面相关信息。</span><span class="sxs-lookup"><span data-stu-id="958c3-125">The other table, OrdersTable, contains only appearance-related information about which customer ID number is equivalent to which order date and order ID.</span></span> <span data-ttu-id="958c3-126">并没有提及客户的名称。</span><span class="sxs-lookup"><span data-stu-id="958c3-126">There is no mention of the customers' names.</span></span>  
  
 <span data-ttu-id="958c3-127">在 [ComboBox 控件](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)控件上设置了 4 种重要属性来创建查找表。</span><span class="sxs-lookup"><span data-stu-id="958c3-127">Four important properties are set on the [ComboBox Control](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md) control to create the lookup table.</span></span>  
  
-   <span data-ttu-id="958c3-128"><xref:System.Windows.Forms.ComboBox.DataSource%2A> 属性包含查找表的名称。</span><span class="sxs-lookup"><span data-stu-id="958c3-128">The <xref:System.Windows.Forms.ComboBox.DataSource%2A> property contains the name of the table.</span></span>  
  
-   <span data-ttu-id="958c3-129"><xref:System.Windows.Forms.ListControl.DisplayMember%2A> 属性包含查找表中要作为控件文本（客户名称）显示的数据列。</span><span class="sxs-lookup"><span data-stu-id="958c3-129">The <xref:System.Windows.Forms.ListControl.DisplayMember%2A> property contains the data column of that table that you want to display for the control text (the customer's name).</span></span>  
  
-   <span data-ttu-id="958c3-130"><xref:System.Windows.Forms.ListControl.ValueMember%2A> 属性包含查找表中具有存储信息（父表中的 ID 号）的数据列。</span><span class="sxs-lookup"><span data-stu-id="958c3-130">The <xref:System.Windows.Forms.ListControl.ValueMember%2A> property contains the data column of that table with the stored information (the ID number in the parent table).</span></span>  
  
-   <span data-ttu-id="958c3-131"><xref:System.Windows.Forms.ListControl.SelectedValue%2A> 属性根据 <xref:System.Windows.Forms.ListControl.ValueMember%2A> 为子表提供查找值。</span><span class="sxs-lookup"><span data-stu-id="958c3-131">The <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property provides the lookup value for the child table, based on the <xref:System.Windows.Forms.ListControl.ValueMember%2A>.</span></span>  
  
 <span data-ttu-id="958c3-132">下面的过程显示了如何将窗体布局设置为一个查找表，并将数据绑定到它上面的控件。</span><span class="sxs-lookup"><span data-stu-id="958c3-132">The procedures below show you how to lay out your form as a lookup table and bind data to the controls on it.</span></span> <span data-ttu-id="958c3-133">为了成功完成这些过程，必须像上面提到的一样有一个带有存在外键关系的父表和子表的数据源。</span><span class="sxs-lookup"><span data-stu-id="958c3-133">To successfully complete the procedures, you must have a data source with parent and child tables that have a foreign-key relationship, as mentioned previously.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="958c3-134">创建用户界面</span><span class="sxs-lookup"><span data-stu-id="958c3-134">To create the user interface</span></span>  
  
1.  <span data-ttu-id="958c3-135">从**工具箱**，拖动<xref:System.Windows.Forms.ComboBox>拖到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="958c3-135">From the **ToolBox**, drag a <xref:System.Windows.Forms.ComboBox> control onto the form.</span></span>  
  
     <span data-ttu-id="958c3-136">此控件将显示父表的列。</span><span class="sxs-lookup"><span data-stu-id="958c3-136">This control will display the column from parent table.</span></span>  
  
2.  <span data-ttu-id="958c3-137">拖动其他控件以显示子表的详细信息。</span><span class="sxs-lookup"><span data-stu-id="958c3-137">Drag other controls to display details from the child table.</span></span> <span data-ttu-id="958c3-138">表中数据的格式决定了应当选择哪些控件。</span><span class="sxs-lookup"><span data-stu-id="958c3-138">The format of the data in the table should determine which controls you choose.</span></span> <span data-ttu-id="958c3-139">有关详细信息，请参阅[按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)。</span><span class="sxs-lookup"><span data-stu-id="958c3-139">For more information, see [Windows Forms Controls by Function](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md).</span></span>  
  
3.  <span data-ttu-id="958c3-140">将一个 <xref:System.Windows.Forms.BindingNavigator> 控件拖到窗体上；这将允许你导航子表中的数据。</span><span class="sxs-lookup"><span data-stu-id="958c3-140">Drag a <xref:System.Windows.Forms.BindingNavigator> control onto the form; this will allow you to navigate the data in the child table.</span></span>  
  
### <a name="to-connect-to-the-data-and-bind-it-to-controls"></a><span data-ttu-id="958c3-141">连接到数据并将其绑定到控件</span><span class="sxs-lookup"><span data-stu-id="958c3-141">To connect to the data and bind it to controls</span></span>  
  
1.  <span data-ttu-id="958c3-142">选择 <xref:System.Windows.Forms.ComboBox> 并单击“智能任务”标志符号，以显示“智能任务”对话框。</span><span class="sxs-lookup"><span data-stu-id="958c3-142">Select the <xref:System.Windows.Forms.ComboBox> and click the Smart Task glyph to display the Smart Task dialog box.</span></span>  
  
2.  <span data-ttu-id="958c3-143">选择“使用数据绑定项”。</span><span class="sxs-lookup"><span data-stu-id="958c3-143">Select **Use data bound items**.</span></span>  
  
3.  <span data-ttu-id="958c3-144">单击“数据源”下拉框旁边的箭头。</span><span class="sxs-lookup"><span data-stu-id="958c3-144">Click the arrow next to the **Data Source** drop-down box.</span></span> <span data-ttu-id="958c3-145">如果以前已经为项目或窗体配置了数据源，将显示该数据源；否则，完成以下步骤（此示例使用 Northwind 示例数据库中的 Customers 表和 Orders 表，并在括号中引用它们）。</span><span class="sxs-lookup"><span data-stu-id="958c3-145">If a data source has previously been configured for the project or form, it will appear; otherwise, complete the following steps (This example uses the Customers and Orders tables of the Northwind sample database and refers to them in parentheses).</span></span>  
  
    1.  <span data-ttu-id="958c3-146">单击“添加项目数据源”以连接到数据并创建一个数据源。</span><span class="sxs-lookup"><span data-stu-id="958c3-146">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
    2.  <span data-ttu-id="958c3-147">在“数据源配置向导”欢迎页上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="958c3-147">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
    3.  <span data-ttu-id="958c3-148">在“选择数据源类型”页面上选择“数据库”。</span><span class="sxs-lookup"><span data-stu-id="958c3-148">Select **Database** on the **Choose a Data Source Type** page.</span></span>  
  
    4.  <span data-ttu-id="958c3-149">从“选择你的数据连接”页面上的可用连接列表中选择一个数据连接。</span><span class="sxs-lookup"><span data-stu-id="958c3-149">Select a data connection from the list of available connections on the **Choose Your Data Connection** page.</span></span> <span data-ttu-id="958c3-150">如果所需的数据连接不可用，则选择“新建连接”以创建一个新的数据连接。</span><span class="sxs-lookup"><span data-stu-id="958c3-150">If your desired data connection is not available, select **New Connection** to create a new data connection.</span></span>  
  
    5.  <span data-ttu-id="958c3-151">单击“是，保存连接”，将连接字符串保存到应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="958c3-151">Click **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
    6.  <span data-ttu-id="958c3-152">选择要放置到应用程序中的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="958c3-152">Select the database objects to bring into your application.</span></span> <span data-ttu-id="958c3-153">在这种情况下，选择具有外键关系的一个父表和一个子表（例如 Customers 和 Orders）。</span><span class="sxs-lookup"><span data-stu-id="958c3-153">In this case, select a parent table and child table (for example, Customers and Orders) with a foreign key relationship.</span></span>  
  
    7.  <span data-ttu-id="958c3-154">如果愿意，可以替换默认的数据集名称。</span><span class="sxs-lookup"><span data-stu-id="958c3-154">Replace the default dataset name if you want.</span></span>  
  
    8.  <span data-ttu-id="958c3-155">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="958c3-155">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="958c3-156">在“显示成员”下拉框中，选择将在组合框中显示的列名（例如，ContactName）。</span><span class="sxs-lookup"><span data-stu-id="958c3-156">In the **Display Member** drop-down box, select the column name (for example, ContactName) to be displayed in the combo box.</span></span>  
  
5.  <span data-ttu-id="958c3-157">在“值成员”下拉框中，选择该列（例如，CustomerID）以在子表中执行查找操作。</span><span class="sxs-lookup"><span data-stu-id="958c3-157">In the **Value Member** drop-down box, select the column (for example, CustomerID) to perform the lookup operation in the child table.</span></span>  
  
6.  <span data-ttu-id="958c3-158">在“选定值”下拉框中，导航到“项目数据源”和刚创建的包含父表和子表的数据集。</span><span class="sxs-lookup"><span data-stu-id="958c3-158">In the **Selected Value** drop-down box, navigate to **Project Data Sources** and the dataset you just created that contains the parent and child tables.</span></span> <span data-ttu-id="958c3-159">选择与父表的值成员相同的子表属性（例如，Orders.CustomerID）。</span><span class="sxs-lookup"><span data-stu-id="958c3-159">Select the same property of the child table that is the Value Member of the parent table (for example, Orders.CustomerID).</span></span> <span data-ttu-id="958c3-160">将创建适当的 <xref:System.Windows.Forms.BindingSource>、数据集和表适配器组件，并将其添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="958c3-160">The appropriate <xref:System.Windows.Forms.BindingSource> , data set, and table adapter components will be created and added to the form.</span></span>  
  
7.  <span data-ttu-id="958c3-161">将 <xref:System.Windows.Forms.BindingNavigator> 控件绑定到子表的 <xref:System.Windows.Forms.BindingSource>（例如，`OrdersBindingSource`）。</span><span class="sxs-lookup"><span data-stu-id="958c3-161">Bind the <xref:System.Windows.Forms.BindingNavigator> control to the <xref:System.Windows.Forms.BindingSource> of the child table (for example, `OrdersBindingSource`).</span></span>  
  
8.  <span data-ttu-id="958c3-162">从想要显示的子表的 <xref:System.Windows.Forms.ComboBox>（例如，<xref:System.Windows.Forms.BindingNavigator>）中，将除了 <xref:System.Windows.Forms.BindingSource> 和 `OrdersBindingSource` 外的控件绑定到详细信息字段上。</span><span class="sxs-lookup"><span data-stu-id="958c3-162">Bind the controls other than the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.BindingNavigator> control to the details fields from the child table's <xref:System.Windows.Forms.BindingSource> (for example, `OrdersBindingSource`) that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958c3-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="958c3-163">See also</span></span>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="958c3-164">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="958c3-164">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="958c3-165">ComboBox 控件</span><span class="sxs-lookup"><span data-stu-id="958c3-165">ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)
- [<span data-ttu-id="958c3-166">在 Visual Studio 中将控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="958c3-166">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
