---
title: "演练︰ 在 DataRepeater 控件 (Visual Studio) 中显示数据 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b795b8f3bb42aecdbdfade62f4943239fec6eac4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="77037-102">演练：在 DataRepeater 控件中显示数据 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="77037-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="77037-103">本演练提供了基本的开始-完成方案中显示绑定的数据在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="77037-104">必备组件</span><span class="sxs-lookup"><span data-stu-id="77037-104">Prerequisite</span></span>  
 <span data-ttu-id="77037-105">本演练需要 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="77037-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="77037-106">如果你的开发计算机上没有此数据库，可以从 [Microsoft 下载中心](http://go.microsoft.com/fwlink/?LinkID=98088)进行下载。</span><span class="sxs-lookup"><span data-stu-id="77037-106">If you do not have this database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span></span> <span data-ttu-id="77037-107">有关说明，请参阅[下载示例数据库](https://msdn.microsoft.com/library/bb399411)。</span><span class="sxs-lookup"><span data-stu-id="77037-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="77037-108">概述</span><span class="sxs-lookup"><span data-stu-id="77037-108">Overview</span></span>  
 <span data-ttu-id="77037-109">本演练的第一部分主要有以下四个任务：</span><span class="sxs-lookup"><span data-stu-id="77037-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="77037-110">创建解决方案。</span><span class="sxs-lookup"><span data-stu-id="77037-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="77037-111">添加<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="77037-112">添加数据源。</span><span class="sxs-lookup"><span data-stu-id="77037-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="77037-113">添加数据绑定控件。</span><span class="sxs-lookup"><span data-stu-id="77037-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="77037-114">创建 DataRepeater 解决方案</span><span class="sxs-lookup"><span data-stu-id="77037-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="77037-115">在第一步中，创建项目和解决方案。</span><span class="sxs-lookup"><span data-stu-id="77037-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="77037-116">创建 DataRepeater 解决方案的步骤</span><span class="sxs-lookup"><span data-stu-id="77037-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="77037-117">在 Visual Studio**文件**菜单上，单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="77037-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="77037-118">在 **“新建项目”** 对话框中的 **“项目类型”** 窗格中，展开 **“Visual Basic”**，然后单击 **“Windows”**。</span><span class="sxs-lookup"><span data-stu-id="77037-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="77037-119">在 **“模板”** 窗格中，单击 **“Windows 窗体应用程序”**。</span><span class="sxs-lookup"><span data-stu-id="77037-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="77037-120">在“名称”****框中键入 `DataRepeaterApp`。</span><span class="sxs-lookup"><span data-stu-id="77037-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="77037-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="77037-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="77037-122">Windows 窗体设计器即会打开。</span><span class="sxs-lookup"><span data-stu-id="77037-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="77037-123">在“Windows 窗体设计器”中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="77037-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="77037-124">在**属性**窗口中，设置**大小**属性设置为`800, 700`。</span><span class="sxs-lookup"><span data-stu-id="77037-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="77037-125">添加 DataRepeater 控件</span><span class="sxs-lookup"><span data-stu-id="77037-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="77037-126">在此步骤中，您将添加<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>到窗体的控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="77037-127">添加 DataRepeater 控件的步骤</span><span class="sxs-lookup"><span data-stu-id="77037-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="77037-128">在 **“视图”** 菜单上单击 **“工具箱”**。</span><span class="sxs-lookup"><span data-stu-id="77037-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="77037-129">将打开 **“工具箱”** 。</span><span class="sxs-lookup"><span data-stu-id="77037-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="77037-130">选择**Visual Basic PowerPacks**选项卡。</span><span class="sxs-lookup"><span data-stu-id="77037-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="77037-131">拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件拖动到**form1**。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="77037-132">在属性窗口中设置**位置**属性设置为`0, 25`。</span><span class="sxs-lookup"><span data-stu-id="77037-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="77037-133">设置**大小**属性设置为`460, 600`。</span><span class="sxs-lookup"><span data-stu-id="77037-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="77037-134">添加数据源</span><span class="sxs-lookup"><span data-stu-id="77037-134">Adding a Data Source</span></span>  
 <span data-ttu-id="77037-135">在此步骤中，添加的数据源<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="77037-136">添加数据源</span><span class="sxs-lookup"><span data-stu-id="77037-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="77037-137">在 **“数据”** 菜单上，单击 **“显示数据源”**。</span><span class="sxs-lookup"><span data-stu-id="77037-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="77037-138">在 **“数据源”** 窗口中，单击 **“添加新数据源”**。</span><span class="sxs-lookup"><span data-stu-id="77037-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="77037-139">在 **“选择数据源类型”** 页上选择 **“数据库”** ，然后单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="77037-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="77037-140">在 **“选择你的数据连接”** 页上执行下列步骤之一：</span><span class="sxs-lookup"><span data-stu-id="77037-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="77037-141">如果下拉列表中包含到 Northwind 示例数据库的数据连接，请单击该连接。</span><span class="sxs-lookup"><span data-stu-id="77037-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="77037-142">- 或 -</span><span class="sxs-lookup"><span data-stu-id="77037-142">-or-</span></span>  
  
    -   <span data-ttu-id="77037-143">单击**新连接**以配置新的数据连接。</span><span class="sxs-lookup"><span data-stu-id="77037-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="77037-144">有关详细信息，请参阅[如何︰ 创建到 SQL Server 数据库的连接](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d)。</span><span class="sxs-lookup"><span data-stu-id="77037-144">For more information, see [How to: Create Connections to SQL Server Databases](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span></span>  
  
5.  <span data-ttu-id="77037-145">如果数据库需要密码，请选择该选项以包括敏感数据，然后单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="77037-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77037-146">如果出现一个对话框中，单击**是**将文件保存到您的项目。</span><span class="sxs-lookup"><span data-stu-id="77037-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="77037-147">单击**下一步**上**连接字符串保存到应用程序配置文件**页。</span><span class="sxs-lookup"><span data-stu-id="77037-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="77037-148">在 **“选择数据库对象”** 页面上展开 **“表”** 节点。</span><span class="sxs-lookup"><span data-stu-id="77037-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="77037-149">选中的复选框旁边**客户**和**订单**表，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="77037-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="77037-150">**NorthwindDataSet**添加到您的项目和**客户**和**订单**表将显示在**数据源**窗口。</span><span class="sxs-lookup"><span data-stu-id="77037-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="77037-151">添加数据绑定控件</span><span class="sxs-lookup"><span data-stu-id="77037-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="77037-152">在此步骤中，您可以将数据绑定控件添加到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="77037-153">添加数据绑定控件</span><span class="sxs-lookup"><span data-stu-id="77037-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="77037-154">在**数据源**窗口中，选择的顶级节点**客户**表。</span><span class="sxs-lookup"><span data-stu-id="77037-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="77037-155">将表拖放类型更改**详细信息**通过单击**详细信息**表节点上的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="77037-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="77037-156">选择**客户**表节点，然后将其拖动到项模板区域 （上部区域） 的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="77037-157">一个<xref:System.Windows.Forms.BindingNavigator>控件添加到窗体中，与**NorthwindDataSet**， **CustomersBindingSource**， **CustomersTableAdapter**， **TableAdapterManager**，和**CustomersBindingNavigator**组件添加到组件栏。</xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="77037-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="77037-158">选择所有字段及其关联标签，并将它们置于项模板区域左边缘附近。</span><span class="sxs-lookup"><span data-stu-id="77037-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="77037-159">选择的最后五个字段 (**区域**， **Postal Code**，**国家/地区**，**电话**，和**传真**) 及其关联的标签并将它们移向上和向右的前六个字段。</span><span class="sxs-lookup"><span data-stu-id="77037-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="77037-160">选择项模板（控件的上半部分区域）。</span><span class="sxs-lookup"><span data-stu-id="77037-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="77037-161">在属性窗口中设置**大小**属性设置为`427, 170`。</span><span class="sxs-lookup"><span data-stu-id="77037-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="77037-162">此时，你就得到了一个有效的应用程序，该应用程序将显示客户的重复列表。</span><span class="sxs-lookup"><span data-stu-id="77037-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="77037-163">可以按 F5 运行该应用程序、更改数据以及添加或删除客户记录。</span><span class="sxs-lookup"><span data-stu-id="77037-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="77037-164">在下一个可选步骤中，您将学习如何自定义<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="77037-165">后续步骤（可选）</span><span class="sxs-lookup"><span data-stu-id="77037-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="77037-166">演练的本部分有以下四个可选任务：</span><span class="sxs-lookup"><span data-stu-id="77037-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="77037-167">更改外观的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="77037-168">防止用户添加或删除记录。</span><span class="sxs-lookup"><span data-stu-id="77037-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="77037-169">添加搜索功能<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="77037-170">添加到母版和详细信息表<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="77037-171">更改 DataRepeater 控件的外观</span><span class="sxs-lookup"><span data-stu-id="77037-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="77037-172">此可选步骤中，在您更改`BackColor`的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件在设计时。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="77037-173">你还将添加代码来以交替颜色显示行以及有条件地更改标签的 `ForeColor` 。</span><span class="sxs-lookup"><span data-stu-id="77037-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="77037-174">更改控件外观的步骤</span><span class="sxs-lookup"><span data-stu-id="77037-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="77037-175">在 Windows 窗体设计器中，选择的主 （下部） 区域<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="77037-176">在“属性”窗口中，将 `BackColor` 属性设置为白色。</span><span class="sxs-lookup"><span data-stu-id="77037-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="77037-177">双击<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>以打开代码编辑器。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="77037-178">在代码编辑器中，事件中的下拉列表中，单击**DrawItem**。</span><span class="sxs-lookup"><span data-stu-id="77037-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="77037-179">在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件处理程序中，将以下代码添加到备用`BackColor`:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem></span><span class="sxs-lookup"><span data-stu-id="77037-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     <span data-ttu-id="77037-180">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="77037-180">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]</span></span>  
  
6.  <span data-ttu-id="77037-181">在<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>事件处理程序中，添加以下代码，以更改`ForeColor`视情况标签的︰</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem></span><span class="sxs-lookup"><span data-stu-id="77037-181">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     <span data-ttu-id="77037-182">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&#2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="77037-182">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]</span></span>  
  
7.  <span data-ttu-id="77037-183">按 F5 运行该应用程序并查看自定义项。</span><span class="sxs-lookup"><span data-stu-id="77037-183">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="77037-184">防止用户添加或删除记录</span><span class="sxs-lookup"><span data-stu-id="77037-184">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="77037-185">在此可选步骤中，添加代码来防止用户添加或删除中的记录<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-185">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="77037-186">防止用户添加和删除记录的步骤</span><span class="sxs-lookup"><span data-stu-id="77037-186">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="77037-187">在 Windows 窗体设计器中，双击窗体打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="77037-187">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="77037-188">将以下代码添加到 `Form_Load` 事件中：</span><span class="sxs-lookup"><span data-stu-id="77037-188">Add the following code to the `Form_Load` event:</span></span>  
  
     <span data-ttu-id="77037-189">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&#3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="77037-189">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]</span></span>  
  
3.  <span data-ttu-id="77037-190">在类名称下拉列表中，单击**BindingNavigatorDeleteItem**。</span><span class="sxs-lookup"><span data-stu-id="77037-190">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="77037-191">在方法名称下拉列表中，单击**EnabledChanged**。</span><span class="sxs-lookup"><span data-stu-id="77037-191">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="77037-192">将以下代码添加到 `BindingNavigatorDeleteItem_EnabledChanged` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="77037-192">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     <span data-ttu-id="77037-193">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&#4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="77037-193">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77037-194">此步骤是必需因为<xref:System.Windows.Forms.BindingSource>将启用**DeleteItem**按钮当前记录发生更改的每次。</xref:System.Windows.Forms.BindingSource></span><span class="sxs-lookup"><span data-stu-id="77037-194">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="77037-195">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="77037-195">Press F5 to run the application.</span></span> <span data-ttu-id="77037-196">请注意， **DeleteItem**按钮被禁用，以及不能删除项目，通过按 DELETE 键。</span><span class="sxs-lookup"><span data-stu-id="77037-196">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="77037-197">向 DataRepeater 控件添加搜索功能</span><span class="sxs-lookup"><span data-stu-id="77037-197">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="77037-198">在此步骤可选实现搜索中的值的功能<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-198">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="77037-199">如果找到了搜索字符串，该控件将选中包含该值的项并将该项滚动到视图中。</span><span class="sxs-lookup"><span data-stu-id="77037-199">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="77037-200">添加搜索功能的步骤</span><span class="sxs-lookup"><span data-stu-id="77037-200">To add search capability</span></span>  
  
1.  <span data-ttu-id="77037-201">拖动<xref:System.Windows.Forms.TextBox>控件从**工具箱**拖到窗体，其中包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="77037-201">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="77037-202">将在下其位置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-202">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="77037-203">在属性窗口中，将更改**名称**属性设置为**搜索文本框**。</span><span class="sxs-lookup"><span data-stu-id="77037-203">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="77037-204">拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖到窗体，其中包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="77037-204">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="77037-205">将在下其位置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-205">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="77037-206">在属性窗口中，将更改**名称**属性设置为**SearchButton**。</span><span class="sxs-lookup"><span data-stu-id="77037-206">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="77037-207">更改**文本**属性设置为**搜索**。</span><span class="sxs-lookup"><span data-stu-id="77037-207">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="77037-208">双击<xref:System.Windows.Forms.Button>控件以打开代码编辑器中，并将添加到下面的代码`SearchButton_Click`事件处理程序。</xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="77037-208">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     <span data-ttu-id="77037-209">[!code-cs[VbPowerPacksDataRepeaterWalkthrough&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="77037-209">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]</span></span>  
  
6.  <span data-ttu-id="77037-210">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="77037-210">Press F5 to run the application.</span></span> <span data-ttu-id="77037-211">键入客户 ID 在**搜索文本框**，然后单击**搜索**按钮。</span><span class="sxs-lookup"><span data-stu-id="77037-211">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="77037-212">向 DataRepeater 添加主表和详细信息表</span><span class="sxs-lookup"><span data-stu-id="77037-212">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="77037-213">在此可选步骤中，添加第二个<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件来显示每个客户的相关的订单。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-213">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="77037-214">添加主表和详细信息表的步骤</span><span class="sxs-lookup"><span data-stu-id="77037-214">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="77037-215">拖动第二个<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**拖到窗体。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-215">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="77037-216">在属性窗口中设置**位置**属性设置为`465, 25`。</span><span class="sxs-lookup"><span data-stu-id="77037-216">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="77037-217">设置**大小**属性设置为`315, 600`。</span><span class="sxs-lookup"><span data-stu-id="77037-217">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="77037-218">在**数据源**窗口中，展开**客户**表节点，然后选择的详细信息节点**订单**表。</span><span class="sxs-lookup"><span data-stu-id="77037-218">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="77037-219">此拖放类型更改**订单**通过单击详细信息表**详细信息**表节点上的下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="77037-219">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="77037-220">拖动此**订单**表节点拖动的项模板区域 （上部区域） 的第二个<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-220">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="77037-221">**Ordersbindingsource**组件和一个**OrdersTableAdapter**组件添加到组件栏。</span><span class="sxs-lookup"><span data-stu-id="77037-221">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="77037-222">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="77037-222">Press F5 to run the application.</span></span> <span data-ttu-id="77037-223">当您在第一个选择每个客户<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控制，订单为该客户将显示在第二个<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="77037-223">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77037-224">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77037-224">See Also</span></span>  
 <span data-ttu-id="77037-225">[DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77037-225">[Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="77037-226"> [如何︰ 在 DataRepeater 控件中显示绑定的数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77037-226"> [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="77037-227"> [如何︰ 在 DataRepeater 控件中的控件显示未绑定](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77037-227"> [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="77037-228"> [如何︰ 更改 DataRepeater 控件的布局](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77037-228"> [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="77037-229"> [如何︰ 在 DataRepeater 控件中显示项标题](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77037-229"> [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="77037-230"> [如何︰ 在 DataRepeater 控件中搜索数据](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77037-230"> [How to: Search Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="77037-231"> [如何︰ 使用两个 DataRepeater 控件 (Visual Studio) 创建母版/详细信息窗体](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span><span class="sxs-lookup"><span data-stu-id="77037-231"> [How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span></span>  
<span data-ttu-id="77037-232"> [如何︰ 更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77037-232"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="77037-233"> [如何︰ 禁止添加和删除 DataRepeater 项](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77037-233"> [How to: Disable Adding and Deleting DataRepeater Items](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md) </span></span>  
<span data-ttu-id="77037-234"> [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="77037-234"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
