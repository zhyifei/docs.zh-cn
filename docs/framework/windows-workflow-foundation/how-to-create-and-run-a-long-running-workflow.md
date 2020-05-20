---
title: 如何创建和运行长时间运行的工作流
description: 本文介绍如何创建支持启动和恢复多个工作流实例和工作流持久性的 Windows 窗体主机应用程序。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 557b3512e534198d47c0c6f6b0a7c5f92bb71739
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419546"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a><span data-ttu-id="62704-103">如何创建和运行长时间运行的工作流</span><span class="sxs-lookup"><span data-stu-id="62704-103">How to create and run a long-running workflow</span></span>

<span data-ttu-id="62704-104">Windows Workflow Foundation （WF）的一个中心功能是运行时能够将空闲工作流保存并卸载到数据库。</span><span class="sxs-lookup"><span data-stu-id="62704-104">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span></span> <span data-ttu-id="62704-105">[如何：运行工作流](how-to-run-a-workflow.md)中的步骤演示了如何使用控制台应用程序托管工作流。</span><span class="sxs-lookup"><span data-stu-id="62704-105">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span></span> <span data-ttu-id="62704-106">示例演示了启动工作流、工作流生命周期处理程序和恢复书签。</span><span class="sxs-lookup"><span data-stu-id="62704-106">Examples were shown of starting workflows, workflow lifecycle handlers, and resuming bookmarks.</span></span> <span data-ttu-id="62704-107">为了有效演示工作流持久性，需要一个支持启动和恢复多个工作流实例的更为复杂的工作流主机。</span><span class="sxs-lookup"><span data-stu-id="62704-107">In order to demonstrate workflow persistence effectively, a more complex workflow host is required that supports starting and resuming multiple workflow instances.</span></span> <span data-ttu-id="62704-108">教程中此步骤演示了如何创建 Windows 窗体主机应用程序，此 Windows 窗体主机应用程序支持启动和恢复多个工作流实例、工作流持久性，并为高级功能（如在后续教程步骤中演示的跟踪和版本控制）提供基础。</span><span class="sxs-lookup"><span data-stu-id="62704-108">This step in the tutorial demonstrates how to create a Windows form host application that supports starting and resuming multiple workflow instances, workflow persistence, and provides a basis for the advanced features such as tracking and versioning that are demonstrated in subsequent tutorial steps.</span></span>

> [!NOTE]
> <span data-ttu-id="62704-109">此教程步骤和后续步骤使用[如何：创建工作流](how-to-create-a-workflow.md)中的所有三个工作流类型。</span><span class="sxs-lookup"><span data-stu-id="62704-109">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span> <span data-ttu-id="62704-110">如果未完成所有这三种类型，则可以从[Windows Workflow Foundation （WF45）-入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)下载完整的步骤版本。</span><span class="sxs-lookup"><span data-stu-id="62704-110">If you did not complete all three types you can download a completed version of the steps from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

> [!NOTE]
> <span data-ttu-id="62704-111">若要下载完整版本或观看教程的视频演练，请参阅[Windows Workflow Foundation （WF45）-入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="62704-111">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-persistence-database"></a><span data-ttu-id="62704-112">创建持久性数据库</span><span class="sxs-lookup"><span data-stu-id="62704-112">To create the persistence database</span></span>

1. <span data-ttu-id="62704-113">打开 SQL Server Management Studio 并连接到本地服务器，例如 **.\SQLEXPRESS**。</span><span class="sxs-lookup"><span data-stu-id="62704-113">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span></span> <span data-ttu-id="62704-114">右键单击本地服务器上的 "**数据库**" 节点，然后选择 "**新建数据库**"。</span><span class="sxs-lookup"><span data-stu-id="62704-114">Right-click the **Databases** node on the local server, and select **New Database**.</span></span> <span data-ttu-id="62704-115">将新数据库命名为**WF45GettingStartedTutorial**，接受所有其他值，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="62704-115">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="62704-116">在创建数据库之前，请确保在本地服务器上具有**Create database**权限。</span><span class="sxs-lookup"><span data-stu-id="62704-116">Ensure that you have **Create Database** permission on the local server before creating the database.</span></span>

2. <span data-ttu-id="62704-117">从 "**文件**" 菜单中**选择 "** **打开**"。</span><span class="sxs-lookup"><span data-stu-id="62704-117">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="62704-118">浏览到以下文件夹： *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span><span class="sxs-lookup"><span data-stu-id="62704-118">Browse to the following folder: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span></span>

    <span data-ttu-id="62704-119">选择以下两个文件，并单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="62704-119">Select the following two files and click **Open**.</span></span>

    - <span data-ttu-id="62704-120">*SqlWorkflowInstanceStoreLogic.sql*</span><span class="sxs-lookup"><span data-stu-id="62704-120">*SqlWorkflowInstanceStoreLogic.sql*</span></span>

    - <span data-ttu-id="62704-121">*SqlWorkflowInstanceStoreSchema.sql*</span><span class="sxs-lookup"><span data-stu-id="62704-121">*SqlWorkflowInstanceStoreSchema.sql*</span></span>

3. <span data-ttu-id="62704-122">从 "**窗口**" 菜单中选择 " **sqlworkflowinstancestoreschema.sql** "。</span><span class="sxs-lookup"><span data-stu-id="62704-122">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span></span> <span data-ttu-id="62704-123">确保在 "**可用数据库**" 下拉 WF45GettingStartedTutorial 中选择 " **WF45GettingStartedTutorial** "，并从 "**查询**" 菜单中选择 "**执行**"。</span><span class="sxs-lookup"><span data-stu-id="62704-123">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

4. <span data-ttu-id="62704-124">从 "**窗口**" 菜单中选择 " **sqlworkflowinstancestorelogic.sql** "。</span><span class="sxs-lookup"><span data-stu-id="62704-124">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span></span> <span data-ttu-id="62704-125">确保在 "**可用数据库**" 下拉 WF45GettingStartedTutorial 中选择 " **WF45GettingStartedTutorial** "，并从 "**查询**" 菜单中选择 "**执行**"。</span><span class="sxs-lookup"><span data-stu-id="62704-125">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

    > [!WARNING]
    > <span data-ttu-id="62704-126">请务必按正确顺序执行前面两个步骤。</span><span class="sxs-lookup"><span data-stu-id="62704-126">It is important to perform the previous two steps in the correct order.</span></span> <span data-ttu-id="62704-127">如果不按顺序执行查询，系统会发生错误，并且持久性数据库会配置不正确。</span><span class="sxs-lookup"><span data-stu-id="62704-127">If the queries are executed out of order, errors occur and the persistence database is not configured correctly.</span></span>

## <a name="to-add-the-reference-to-the-durableinstancing-assemblies"></a><span data-ttu-id="62704-128">添加对 DurableInstancing 程序集的引用</span><span class="sxs-lookup"><span data-stu-id="62704-128">To add the reference to the DurableInstancing assemblies</span></span>

1. <span data-ttu-id="62704-129">在**解决方案资源管理器**中右键单击 " **NumberGuessWorkflowHost** "，然后选择 "**添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="62704-129">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span></span>

2. <span data-ttu-id="62704-130">从 "**添加引用**" 列表中选择**程序集**，然后 `DurableInstancing` 在 "**搜索程序集**" 框中键入。</span><span class="sxs-lookup"><span data-stu-id="62704-130">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span></span> <span data-ttu-id="62704-131">这将筛选程序集，使您更易于选择所需引用。</span><span class="sxs-lookup"><span data-stu-id="62704-131">This filters the assemblies and makes the desired references easier to select.</span></span>

3. <span data-ttu-id="62704-132">选中 " **DurableInstancing** " 和 " **DurableInstancing** **" 旁边**的复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="62704-132">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span></span>

## <a name="to-create-the-workflow-host-form"></a><span data-ttu-id="62704-133">创建工作流主机窗体</span><span class="sxs-lookup"><span data-stu-id="62704-133">To create the workflow host form</span></span>

> [!NOTE]
> <span data-ttu-id="62704-134">此过程中的步骤描述了如何手动添加和配置窗体。</span><span class="sxs-lookup"><span data-stu-id="62704-134">The steps in this procedure describe how to add and configure the form manually.</span></span> <span data-ttu-id="62704-135">如果需要，您可以下载教程的解决方案文件并将完成后的窗体添加到项目。</span><span class="sxs-lookup"><span data-stu-id="62704-135">If desired, you can download the solution files for the tutorial and add the completed form to the project.</span></span> <span data-ttu-id="62704-136">若要下载教程文件，请参阅[Windows Workflow Foundation （WF45）-入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="62704-136">To download the tutorial files, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span> <span data-ttu-id="62704-137">下载文件后，右键单击**NumberGuessWorkflowHost** ，然后选择 "**添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="62704-137">Once the files are downloaded, right-click **NumberGuessWorkflowHost** and choose **Add Reference**.</span></span> <span data-ttu-id="62704-138">添加对**system.web**和**system.object**的引用。</span><span class="sxs-lookup"><span data-stu-id="62704-138">Add a reference to **System.Windows.Forms** and **System.Drawing**.</span></span> <span data-ttu-id="62704-139">如果从 "**添加**"、"**新建项**" 菜单添加新的窗体，但在导入窗体时必须手动添加，则会自动添加这些引用。</span><span class="sxs-lookup"><span data-stu-id="62704-139">These references are added automatically if you add a new form from the **Add**, **New Item** menu, but must be added manually when importing a form.</span></span> <span data-ttu-id="62704-140">添加引用后，在**解决方案资源管理器**中右键单击**NumberGuessWorkflowHost** ，然后选择 "**添加**"、"**现有项**"。</span><span class="sxs-lookup"><span data-stu-id="62704-140">Once the references are added, right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Existing Item**.</span></span> <span data-ttu-id="62704-141">浏览到 `Form` 项目文件中的文件夹，选择**WorkflowHostForm.cs** （或**WorkflowHostForm**），然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="62704-141">Browse to the `Form` folder in the project files, select **WorkflowHostForm.cs** (or **WorkflowHostForm.vb**), and click **Add**.</span></span> <span data-ttu-id="62704-142">如果选择导入窗体，则可以跳到下一部分，[添加窗体的属性和帮助器方法](#to-add-the-properties-and-helper-methods-of-the-form)。</span><span class="sxs-lookup"><span data-stu-id="62704-142">If you choose to import the form, then you can skip down to the next section, [To add the properties and helper methods of the form](#to-add-the-properties-and-helper-methods-of-the-form).</span></span>

1. <span data-ttu-id="62704-143">在**解决方案资源管理器**中右键单击 " **NumberGuessWorkflowHost** "，然后选择 "**添加**"、"**新建项**"。</span><span class="sxs-lookup"><span data-stu-id="62704-143">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span></span>

2. <span data-ttu-id="62704-144">在 "**已安装**的模板" 列表中，选择**Windows 窗体**， `WorkflowHostForm` 在 "**名称**" 框中键入，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="62704-144">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span></span>

3. <span data-ttu-id="62704-145">在窗体上配置以下属性。</span><span class="sxs-lookup"><span data-stu-id="62704-145">Configure the following properties on the form.</span></span>

    |<span data-ttu-id="62704-146">properties</span><span class="sxs-lookup"><span data-stu-id="62704-146">Property</span></span>|<span data-ttu-id="62704-147">Value</span><span class="sxs-lookup"><span data-stu-id="62704-147">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="62704-148">FormBorderStyle</span><span class="sxs-lookup"><span data-stu-id="62704-148">FormBorderStyle</span></span>|<span data-ttu-id="62704-149">FixedSingle</span><span class="sxs-lookup"><span data-stu-id="62704-149">FixedSingle</span></span>|
    |<span data-ttu-id="62704-150">MaximizeBox</span><span class="sxs-lookup"><span data-stu-id="62704-150">MaximizeBox</span></span>|<span data-ttu-id="62704-151">False</span><span class="sxs-lookup"><span data-stu-id="62704-151">False</span></span>|
    |<span data-ttu-id="62704-152">大小</span><span class="sxs-lookup"><span data-stu-id="62704-152">Size</span></span>|<span data-ttu-id="62704-153">400, 420</span><span class="sxs-lookup"><span data-stu-id="62704-153">400, 420</span></span>|

4. <span data-ttu-id="62704-154">按照指定顺序将以下控件添加到窗体，并根据指示配置这些属性。</span><span class="sxs-lookup"><span data-stu-id="62704-154">Add the following controls to the form in the order specified and configure the properties as directed.</span></span>

    |<span data-ttu-id="62704-155">控件</span><span class="sxs-lookup"><span data-stu-id="62704-155">Control</span></span>|<span data-ttu-id="62704-156">属性：值</span><span class="sxs-lookup"><span data-stu-id="62704-156">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="62704-157">**Button**</span><span class="sxs-lookup"><span data-stu-id="62704-157">**Button**</span></span>|<span data-ttu-id="62704-158">名称： NewGame</span><span class="sxs-lookup"><span data-stu-id="62704-158">Name: NewGame</span></span><br /><br /> <span data-ttu-id="62704-159">位置：13、13</span><span class="sxs-lookup"><span data-stu-id="62704-159">Location: 13, 13</span></span><br /><br /> <span data-ttu-id="62704-160">大小：75，23</span><span class="sxs-lookup"><span data-stu-id="62704-160">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="62704-161">文本：新建游戏</span><span class="sxs-lookup"><span data-stu-id="62704-161">Text: New Game</span></span>|
    |<span data-ttu-id="62704-162">**标签**</span><span class="sxs-lookup"><span data-stu-id="62704-162">**Label**</span></span>|<span data-ttu-id="62704-163">位置：94、18</span><span class="sxs-lookup"><span data-stu-id="62704-163">Location: 94, 18</span></span><br /><br /> <span data-ttu-id="62704-164">Text：推测一个从1到</span><span class="sxs-lookup"><span data-stu-id="62704-164">Text: Guess a number from 1 to</span></span>|
    |<span data-ttu-id="62704-165">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="62704-165">**ComboBox**</span></span>|<span data-ttu-id="62704-166">名称： NumberRange</span><span class="sxs-lookup"><span data-stu-id="62704-166">Name: NumberRange</span></span><br /><br /> <span data-ttu-id="62704-167">DropDownStyle： DropDownList</span><span class="sxs-lookup"><span data-stu-id="62704-167">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="62704-168">项：10，100，1000</span><span class="sxs-lookup"><span data-stu-id="62704-168">Items: 10, 100, 1000</span></span><br /><br /> <span data-ttu-id="62704-169">位置：228、12</span><span class="sxs-lookup"><span data-stu-id="62704-169">Location: 228, 12</span></span><br /><br /> <span data-ttu-id="62704-170">大小：143，21</span><span class="sxs-lookup"><span data-stu-id="62704-170">Size: 143, 21</span></span>|
    |<span data-ttu-id="62704-171">**标签**</span><span class="sxs-lookup"><span data-stu-id="62704-171">**Label**</span></span>|<span data-ttu-id="62704-172">位置：13，43</span><span class="sxs-lookup"><span data-stu-id="62704-172">Location: 13, 43</span></span><br /><br /> <span data-ttu-id="62704-173">文本：工作流类型</span><span class="sxs-lookup"><span data-stu-id="62704-173">Text: Workflow type</span></span>|
    |<span data-ttu-id="62704-174">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="62704-174">**ComboBox**</span></span>|<span data-ttu-id="62704-175">名称： WorkflowType</span><span class="sxs-lookup"><span data-stu-id="62704-175">Name: WorkflowType</span></span><br /><br /> <span data-ttu-id="62704-176">DropDownStyle： DropDownList</span><span class="sxs-lookup"><span data-stu-id="62704-176">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="62704-177">Items： Statemachinenumberguessworkflow.xaml、Flowchartnumberguessworkflow.xaml、Sequentialnumberguessworkflow.xaml</span><span class="sxs-lookup"><span data-stu-id="62704-177">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span></span><br /><br /> <span data-ttu-id="62704-178">位置：94、40</span><span class="sxs-lookup"><span data-stu-id="62704-178">Location: 94, 40</span></span><br /><br /> <span data-ttu-id="62704-179">大小：277，21</span><span class="sxs-lookup"><span data-stu-id="62704-179">Size: 277, 21</span></span>|
    |<span data-ttu-id="62704-180">**标签**</span><span class="sxs-lookup"><span data-stu-id="62704-180">**Label**</span></span>|<span data-ttu-id="62704-181">名称： WorkflowVersion</span><span class="sxs-lookup"><span data-stu-id="62704-181">Name: WorkflowVersion</span></span><br /><br /> <span data-ttu-id="62704-182">位置：13，362</span><span class="sxs-lookup"><span data-stu-id="62704-182">Location: 13, 362</span></span><br /><br /> <span data-ttu-id="62704-183">文本：工作流版本</span><span class="sxs-lookup"><span data-stu-id="62704-183">Text: Workflow version</span></span>|
    |<span data-ttu-id="62704-184">**GroupBox**</span><span class="sxs-lookup"><span data-stu-id="62704-184">**GroupBox**</span></span>|<span data-ttu-id="62704-185">位置：13，67</span><span class="sxs-lookup"><span data-stu-id="62704-185">Location: 13, 67</span></span><br /><br /> <span data-ttu-id="62704-186">大小：358、287</span><span class="sxs-lookup"><span data-stu-id="62704-186">Size: 358, 287</span></span><br /><br /> <span data-ttu-id="62704-187">文本：游戏</span><span class="sxs-lookup"><span data-stu-id="62704-187">Text: Game</span></span>|

    > [!NOTE]
    > <span data-ttu-id="62704-188">添加以下控件时，将其放入分组框。</span><span class="sxs-lookup"><span data-stu-id="62704-188">When adding the following controls, put them into the GroupBox.</span></span>

    |<span data-ttu-id="62704-189">控件</span><span class="sxs-lookup"><span data-stu-id="62704-189">Control</span></span>|<span data-ttu-id="62704-190">属性：值</span><span class="sxs-lookup"><span data-stu-id="62704-190">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="62704-191">**标签**</span><span class="sxs-lookup"><span data-stu-id="62704-191">**Label**</span></span>|<span data-ttu-id="62704-192">位置：7、20</span><span class="sxs-lookup"><span data-stu-id="62704-192">Location: 7, 20</span></span><br /><br /> <span data-ttu-id="62704-193">文本：工作流实例 Id</span><span class="sxs-lookup"><span data-stu-id="62704-193">Text: Workflow Instance Id</span></span>|
    |<span data-ttu-id="62704-194">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="62704-194">**ComboBox**</span></span>|<span data-ttu-id="62704-195">名称： InstanceId</span><span class="sxs-lookup"><span data-stu-id="62704-195">Name: InstanceId</span></span><br /><br /> <span data-ttu-id="62704-196">DropDownStyle： DropDownList</span><span class="sxs-lookup"><span data-stu-id="62704-196">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="62704-197">位置：121、17</span><span class="sxs-lookup"><span data-stu-id="62704-197">Location: 121, 17</span></span><br /><br /> <span data-ttu-id="62704-198">大小：227，21</span><span class="sxs-lookup"><span data-stu-id="62704-198">Size: 227, 21</span></span>|
    |<span data-ttu-id="62704-199">**标签**</span><span class="sxs-lookup"><span data-stu-id="62704-199">**Label**</span></span>|<span data-ttu-id="62704-200">位置：7，47</span><span class="sxs-lookup"><span data-stu-id="62704-200">Location: 7, 47</span></span><br /><br /> <span data-ttu-id="62704-201">文本：推测</span><span class="sxs-lookup"><span data-stu-id="62704-201">Text: Guess</span></span>|
    |<span data-ttu-id="62704-202">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="62704-202">**TextBox**</span></span>|<span data-ttu-id="62704-203">名称：推测</span><span class="sxs-lookup"><span data-stu-id="62704-203">Name: Guess</span></span><br /><br /> <span data-ttu-id="62704-204">位置：50、44</span><span class="sxs-lookup"><span data-stu-id="62704-204">Location: 50, 44</span></span><br /><br /> <span data-ttu-id="62704-205">大小：65，20</span><span class="sxs-lookup"><span data-stu-id="62704-205">Size: 65, 20</span></span>|
    |<span data-ttu-id="62704-206">**Button**</span><span class="sxs-lookup"><span data-stu-id="62704-206">**Button**</span></span>|<span data-ttu-id="62704-207">名称： EnterGuess</span><span class="sxs-lookup"><span data-stu-id="62704-207">Name: EnterGuess</span></span><br /><br /> <span data-ttu-id="62704-208">位置：121、42</span><span class="sxs-lookup"><span data-stu-id="62704-208">Location: 121, 42</span></span><br /><br /> <span data-ttu-id="62704-209">大小：75，23</span><span class="sxs-lookup"><span data-stu-id="62704-209">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="62704-210">文本：输入推测</span><span class="sxs-lookup"><span data-stu-id="62704-210">Text: Enter Guess</span></span>|
    |<span data-ttu-id="62704-211">**Button**</span><span class="sxs-lookup"><span data-stu-id="62704-211">**Button**</span></span>|<span data-ttu-id="62704-212">名称： QuitGame</span><span class="sxs-lookup"><span data-stu-id="62704-212">Name: QuitGame</span></span><br /><br /> <span data-ttu-id="62704-213">位置：274、42</span><span class="sxs-lookup"><span data-stu-id="62704-213">Location: 274, 42</span></span><br /><br /> <span data-ttu-id="62704-214">大小：75，23</span><span class="sxs-lookup"><span data-stu-id="62704-214">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="62704-215">文本： Quit</span><span class="sxs-lookup"><span data-stu-id="62704-215">Text: Quit</span></span>|
    |<span data-ttu-id="62704-216">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="62704-216">**TextBox**</span></span>|<span data-ttu-id="62704-217">名称： WorkflowStatus</span><span class="sxs-lookup"><span data-stu-id="62704-217">Name: WorkflowStatus</span></span><br /><br /> <span data-ttu-id="62704-218">位置：10，73</span><span class="sxs-lookup"><span data-stu-id="62704-218">Location: 10, 73</span></span><br /><br /> <span data-ttu-id="62704-219">多行： True</span><span class="sxs-lookup"><span data-stu-id="62704-219">Multiline: True</span></span><br /><br /> <span data-ttu-id="62704-220">ReadOnly： True</span><span class="sxs-lookup"><span data-stu-id="62704-220">ReadOnly: True</span></span><br /><br /> <span data-ttu-id="62704-221">滚动条：垂直</span><span class="sxs-lookup"><span data-stu-id="62704-221">ScrollBars: Vertical</span></span><br /><br /> <span data-ttu-id="62704-222">大小：338、208</span><span class="sxs-lookup"><span data-stu-id="62704-222">Size: 338, 208</span></span>|

5. <span data-ttu-id="62704-223">将窗体的**AcceptButton**属性设置为**EnterGuess**。</span><span class="sxs-lookup"><span data-stu-id="62704-223">Set the **AcceptButton** property of the form to **EnterGuess**.</span></span>

 <span data-ttu-id="62704-224">以下示例展示了完成的窗体。</span><span class="sxs-lookup"><span data-stu-id="62704-224">The following example illustrates the completed form.</span></span>

 ![Windows Workflow Foundation 工作流宿主窗体的屏幕截图。](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)

## <a name="to-add-the-properties-and-helper-methods-of-the-form"></a><span data-ttu-id="62704-226">添加窗体的属性和帮助器方法</span><span class="sxs-lookup"><span data-stu-id="62704-226">To add the properties and helper methods of the form</span></span>

<span data-ttu-id="62704-227">本节的步骤将属性和帮助器添加至窗体类，此窗体类将配置窗体的 UI，以支持运行和恢复数字猜测工作流。</span><span class="sxs-lookup"><span data-stu-id="62704-227">The steps in this section add properties and helper methods to the form class that configure the UI of the form to support running and resuming number guess workflows.</span></span>

1. <span data-ttu-id="62704-228">在**解决方案资源管理器**中右键单击 " **WorkflowHostForm** "，然后选择 "**查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="62704-228">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>

2. <span data-ttu-id="62704-229">在包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。</span><span class="sxs-lookup"><span data-stu-id="62704-229">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    Imports System.Data.SqlClient
    Imports System.IO
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DurableInstancing;
    using System.Data.SqlClient;
    using System.IO;
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="62704-230">将以下成员声明添加到**WorkflowHostForm**类。</span><span class="sxs-lookup"><span data-stu-id="62704-230">Add the following member declarations to the **WorkflowHostForm** class.</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    Dim store As SqlWorkflowInstanceStore
    Dim workflowStarting As Boolean
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    SqlWorkflowInstanceStore store;
    bool workflowStarting;
    ```

    > [!NOTE]
    > <span data-ttu-id="62704-231">如果您的连接字符串不同，请更新 `connectionString` 引用数据库。</span><span class="sxs-lookup"><span data-stu-id="62704-231">If your connection string is different, update `connectionString` to refer to your database.</span></span>

4. <span data-ttu-id="62704-232">将 `WorkflowInstanceId` 属性添加到 `WorkflowFormHost` 类中。</span><span class="sxs-lookup"><span data-stu-id="62704-232">Add a `WorkflowInstanceId` property to the `WorkflowFormHost` class.</span></span>

    ```vb
    Public ReadOnly Property WorkflowInstanceId() As Guid
        Get
            If InstanceId.SelectedIndex = -1 Then
                Return Guid.Empty
            Else
                Return New Guid(InstanceId.SelectedItem.ToString())
            End If
        End Get
    End Property
    ```

    ```csharp
    public Guid WorkflowInstanceId
    {
        get
        {
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;
        }
    }
    ```

    <span data-ttu-id="62704-233">`InstanceId`组合框显示持久化工作流实例 id 的列表， `WorkflowInstanceId` 属性返回当前选择的工作流。</span><span class="sxs-lookup"><span data-stu-id="62704-233">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span></span>

5. <span data-ttu-id="62704-234">为窗体 `Load` 事件添加处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-234">Add a handler for the form `Load` event.</span></span> <span data-ttu-id="62704-235">若要添加该处理程序，请切换到窗体的**设计视图**，单击 "**属性**" 窗口顶部的 "**事件**" 图标，然后双击 "**加载**"。</span><span class="sxs-lookup"><span data-stu-id="62704-235">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span></span>

    ```vb
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load

    End Sub
    ```

    ```csharp
    private void WorkflowHostForm_Load(object sender, EventArgs e)
    {

    }
    ```

6. <span data-ttu-id="62704-236">将下列代码添加到 `WorkflowHostForm_Load`。</span><span class="sxs-lookup"><span data-stu-id="62704-236">Add the following code to `WorkflowHostForm_Load`.</span></span>

    ```vb
    ' Initialize the store and configure it so that it can be used for
    ' multiple WorkflowApplication instances.
    store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    ' Set default ComboBox selections.
    NumberRange.SelectedIndex = 0
    WorkflowType.SelectedIndex = 0

    ListPersistedWorkflows()
    ```

    ```csharp
    // Initialize the store and configure it so that it can be used for
    // multiple WorkflowApplication instances.
    store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    // Set default ComboBox selections.
    NumberRange.SelectedIndex = 0;
    WorkflowType.SelectedIndex = 0;

    ListPersistedWorkflows();
    ```

    <span data-ttu-id="62704-237">窗体加载时，将配置 `SqlWorkflowInstanceStore`，范围和工作流类型组合框将设置为默认值，持久性工作流实例将添加到 `InstanceId` 组合框。</span><span class="sxs-lookup"><span data-stu-id="62704-237">When the form loads, the `SqlWorkflowInstanceStore` is configured, the range and workflow type combo boxes are set to default values, and the persisted workflow instances are added to the `InstanceId` combo box.</span></span>

7. <span data-ttu-id="62704-238">为 `SelectedIndexChanged` 添加 `InstanceId` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-238">Add a `SelectedIndexChanged` handler for `InstanceId`.</span></span> <span data-ttu-id="62704-239">若要添加该处理程序，请切换到窗体的**设计视图**，选择 `InstanceId` 组合框，单击 "**属性**" 窗口顶部的 "**事件**" 图标，然后双击 " **SelectedIndexChanged**"。</span><span class="sxs-lookup"><span data-stu-id="62704-239">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span></span>

    ```vb
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged

    End Sub
    ```

    ```csharp
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)
    {

    }
    ```

8. <span data-ttu-id="62704-240">将下列代码添加到 `InstanceId_SelectedIndexChanged`。</span><span class="sxs-lookup"><span data-stu-id="62704-240">Add the following code to `InstanceId_SelectedIndexChanged`.</span></span> <span data-ttu-id="62704-241">只要用户使用组合框选择一个工作流，此处理程序就会更新状态窗口。</span><span class="sxs-lookup"><span data-stu-id="62704-241">Whenever the user selects a workflow by using the combo box this handler updates the status window.</span></span>

    ```vb
    If InstanceId.SelectedIndex = -1 Then
        Return
    End If

    ' Clear the status window.
    WorkflowStatus.Clear()

    ' Get the workflow version and display it.
    ' If the workflow is just starting then this info will not
    ' be available in the persistence store so do not try and retrieve it.
    If Not workflowStarting Then
        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        WorkflowVersion.Text = _
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)

        ' Unload the instance.
        instance.Abandon()
    End If
    ```

    ```csharp
    if (InstanceId.SelectedIndex == -1)
    {
        return;
    }

    // Clear the status window.
    WorkflowStatus.Clear();

    // Get the workflow version and display it.
    // If the workflow is just starting then this info will not
    // be available in the persistence store so do not try and retrieve it.
    if (!workflowStarting)
    {
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);

        WorkflowVersion.Text =
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);

        // Unload the instance.
        instance.Abandon();
    }
    ```

9. <span data-ttu-id="62704-242">将下面的 `ListPersistedWorkflows` 方法添加到窗体类中。</span><span class="sxs-lookup"><span data-stu-id="62704-242">Add the following `ListPersistedWorkflows` method to the form class.</span></span>

    ```vb
    Private Sub ListPersistedWorkflows()
        Using localCon As New SqlConnection(connectionString)
            Dim localCmd As String = _
                "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]"

            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)

                While (reader.Read())
                    ' Get the InstanceId of the persisted Workflow.
                    Dim id As Guid = Guid.Parse(reader(0).ToString())
                    InstanceId.Items.Add(id)
                End While
            End Using
        End Using
    End Sub
    ```

    ```csharp
    using (var localCon = new SqlConnection(connectionString))
    {
        string localCmd =
            "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]";

        SqlCommand cmd = localCon.CreateCommand();
        cmd.CommandText = localCmd;
        localCon.Open();
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
        {
            while (reader.Read())
            {
                // Get the InstanceId of the persisted Workflow.
                Guid id = Guid.Parse(reader[0].ToString());
                InstanceId.Items.Add(id);
            }
        }
    }
    ```

    <span data-ttu-id="62704-243">`ListPersistedWorkflows` 查询持久性工作流实例的实例存储，并将实例 ID 添加到 `cboInstanceId` 组合框。</span><span class="sxs-lookup"><span data-stu-id="62704-243">`ListPersistedWorkflows` queries the instance store for persisted workflow instances, and adds the instance ids to the `cboInstanceId` combo box.</span></span>

10. <span data-ttu-id="62704-244">将下面的 `UpdateStatus` 方法和对应的委托添加到窗体类中。</span><span class="sxs-lookup"><span data-stu-id="62704-244">Add the following `UpdateStatus` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="62704-245">此方法使用当前正在运行的工作流的状态来更新窗体上的状态窗口。</span><span class="sxs-lookup"><span data-stu-id="62704-245">This method updates the status window on the form with the status of the currently running workflow.</span></span>

    ```vb
    Private Delegate Sub UpdateStatusDelegate(msg As String)
    Public Sub UpdateStatus(msg As String)
        ' We may be on a different thread so we need to
        ' make this call using BeginInvoke.
        If InvokeRequired Then
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)
        Else
            If Not msg.EndsWith(vbCrLf) Then
                msg = msg & vbCrLf
            End If

            WorkflowStatus.AppendText(msg)

            ' Ensure that the newly added status is visible.
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length
            WorkflowStatus.ScrollToCaret()
        End If
    End Sub
    ```

    ```csharp
    private delegate void UpdateStatusDelegate(string msg);
    public void UpdateStatus(string msg)
    {
        // We may be on a different thread so we need to
        // make this call using BeginInvoke.
        if (InvokeRequired)
        {
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);
        }
        else
        {
            if (!msg.EndsWith("\r\n"))
            {
                msg += "\r\n";
            }
            WorkflowStatus.AppendText(msg);

            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;
            WorkflowStatus.ScrollToCaret();
        }
    }
    ```

11. <span data-ttu-id="62704-246">将下面的 `GameOver` 方法和对应的委托添加到窗体类中。</span><span class="sxs-lookup"><span data-stu-id="62704-246">Add the following `GameOver` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="62704-247">当工作流完成时，此方法将通过从**InstanceId**组合框中删除已完成工作流的实例 id 来更新窗体 UI。</span><span class="sxs-lookup"><span data-stu-id="62704-247">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span></span>

    ```vb
    Private Delegate Sub GameOverDelegate()
    Private Sub GameOver()
        If InvokeRequired Then
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))
        Else
            ' Remove this instance from the InstanceId combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem)
            InstanceId.SelectedIndex = -1
        End If
    End Sub
    ```

    ```csharp
    private delegate void GameOverDelegate();
    private void GameOver()
    {
        if (InvokeRequired)
        {
            BeginInvoke(new GameOverDelegate(GameOver));
        }
        else
        {
            // Remove this instance from the combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem);
            InstanceId.SelectedIndex = -1;
        }
    }
    ```

## <a name="to-configure-the-instance-store-workflow-lifecycle-handlers-and-extensions"></a><span data-ttu-id="62704-248">配置实例存储、工作流生命周期处理程序和扩展</span><span class="sxs-lookup"><span data-stu-id="62704-248">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>

1. <span data-ttu-id="62704-249">向窗体类添加 `ConfigureWorkflowApplication` 方法。</span><span class="sxs-lookup"><span data-stu-id="62704-249">Add a `ConfigureWorkflowApplication` method to the form class.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)

    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
    }
    ```

    <span data-ttu-id="62704-250">此方法配置 `WorkflowApplication`、添加所需扩展并添加工作流生命周期事件的处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-250">This method configures the `WorkflowApplication`, adds the desired extensions, and adds handlers for the workflow lifecycle events.</span></span>

2. <span data-ttu-id="62704-251">在 `ConfigureWorkflowApplication` 中，指定 `SqlWorkflowInstanceStore` 的 `WorkflowApplication`。</span><span class="sxs-lookup"><span data-stu-id="62704-251">In `ConfigureWorkflowApplication`, specify the `SqlWorkflowInstanceStore` for the `WorkflowApplication`.</span></span>

    ```vb
    ' Configure the persistence store.
    wfApp.InstanceStore = store
    ```

    ```csharp
    // Configure the persistence store.
    wfApp.InstanceStore = store;
    ```

3. <span data-ttu-id="62704-252">接下来，创建一个 `StringWriter` 实例，并将它添加到 `Extensions` 的 `WorkflowApplication` 集合中。</span><span class="sxs-lookup"><span data-stu-id="62704-252">Next, create a `StringWriter` instance and add it to the `Extensions` collection of the `WorkflowApplication`.</span></span> <span data-ttu-id="62704-253">当将 `StringWriter` 添加到扩展时，它将捕获所有 `WriteLine` 活动输出。</span><span class="sxs-lookup"><span data-stu-id="62704-253">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span></span> <span data-ttu-id="62704-254">当工作流进入空闲状态时，`WriteLine` 输出可从 `StringWriter` 提取并显示在窗体上。</span><span class="sxs-lookup"><span data-stu-id="62704-254">When the workflow becomes idle, the `WriteLine` output can be extracted from the `StringWriter` and displayed on the form.</span></span>

    ```vb
    ' Add a StringWriter to the extensions. This captures the output
    ' from the WriteLine activities so we can display it in the form.
    Dim sw As New StringWriter()
    wfApp.Extensions.Add(sw)
    ```

    ```csharp
    // Add a StringWriter to the extensions. This captures the output
    // from the WriteLine activities so we can display it in the form.
    var sw = new StringWriter();
    wfApp.Extensions.Add(sw);
    ```

4. <span data-ttu-id="62704-255">为 `Completed` 事件添加以下处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-255">Add the following handler for the `Completed` event.</span></span> <span data-ttu-id="62704-256">在工作流成功完成时，执行猜测数字的轮数会显示到状态窗口。</span><span class="sxs-lookup"><span data-stu-id="62704-256">When a workflow successfully completes, the number of turns taken to guess the number is displayed to the status window.</span></span> <span data-ttu-id="62704-257">如果工作流终止，系统会显示导致终止的异常信息。</span><span class="sxs-lookup"><span data-stu-id="62704-257">If the workflow terminates, the exception information that caused the termination is displayed.</span></span> <span data-ttu-id="62704-258">在处理程序结尾处调用了 `GameOver` 方法，该方法从工作流列表中删除已完成的工作流。</span><span class="sxs-lookup"><span data-stu-id="62704-258">At the end of the handler the `GameOver` method is called, which removes the completed workflow from the workflow list.</span></span>

    ```vb
    wfApp.Completed = _
        Sub(e As WorkflowApplicationCompletedEventArgs)
            If e.CompletionState = ActivityInstanceState.Faulted Then
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                UpdateStatus("Workflow Canceled.")
            Else
                Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
            End If
            GameOver()
        End Sub
    ```

    ```csharp
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
    {
        if (e.CompletionState == ActivityInstanceState.Faulted)
        {
            UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
        }
        else if (e.CompletionState == ActivityInstanceState.Canceled)
        {
            UpdateStatus("Workflow Canceled.");
        }
        else
        {
            int turns = Convert.ToInt32(e.Outputs["Turns"]);
            UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
        }
        GameOver();
    };
    ```

5. <span data-ttu-id="62704-259">添加以下 `Aborted` 和 `OnUnhandledException` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-259">Add the following `Aborted` and `OnUnhandledException` handlers.</span></span> <span data-ttu-id="62704-260">`GameOver` 方法不从 `Aborted` 处理程序中调用，因为在工作流实例中止时，它并未终止，且以后可能恢复实例。</span><span class="sxs-lookup"><span data-stu-id="62704-260">The `GameOver` method is not called from the `Aborted` handler because when a workflow instance is aborted, it does not terminate, and it is possible to resume the instance at a later time.</span></span>

    ```vb
    wfApp.Aborted = _
        Sub(e As WorkflowApplicationAbortedEventArgs)
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
        End Sub

    wfApp.OnUnhandledException = _
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
            GameOver()
            Return UnhandledExceptionAction.Terminate
        End Function
    ```

    ```csharp
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
    {
        UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
    };

    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
    {
        UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
        GameOver();
        return UnhandledExceptionAction.Terminate;
    };
    ```

6. <span data-ttu-id="62704-261">添加以下 `PersistableIdle` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-261">Add the following `PersistableIdle` handler.</span></span> <span data-ttu-id="62704-262">此处理程序检索添加的 `StringWriter` 扩展，提取 `WriteLine` 活动的输出，并将它显示在状态窗口中。</span><span class="sxs-lookup"><span data-stu-id="62704-262">This handler retrieves the `StringWriter` extension that was added, extracts the output from the `WriteLine` activities, and displays it in the status window.</span></span>

    ```vb
    wfApp.PersistableIdle = _
        Function(e As WorkflowApplicationIdleEventArgs)
            ' Send the current WriteLine outputs to the status window.
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()
            For Each writer In writers
                UpdateStatus(writer.ToString())
            Next
            Return PersistableIdleAction.Unload
        End Function
    ```

    ```csharp
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
    {
        // Send the current WriteLine outputs to the status window.
        var writers = e.GetInstanceExtensions<StringWriter>();
        foreach (var writer in writers)
        {
            UpdateStatus(writer.ToString());
        }
        return PersistableIdleAction.Unload;
    };
    ```

    <span data-ttu-id="62704-263"><xref:System.Activities.PersistableIdleAction> 枚举有三个值：<xref:System.Activities.PersistableIdleAction.None>、 <xref:System.Activities.PersistableIdleAction.Persist> 和 <xref:System.Activities.PersistableIdleAction.Unload>。</span><span class="sxs-lookup"><span data-stu-id="62704-263">The <xref:System.Activities.PersistableIdleAction> enumeration has three values: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist>, and <xref:System.Activities.PersistableIdleAction.Unload>.</span></span> <span data-ttu-id="62704-264"><xref:System.Activities.PersistableIdleAction.Persist> 会导致工作流持久保存，但不会导致工作流卸载。</span><span class="sxs-lookup"><span data-stu-id="62704-264"><xref:System.Activities.PersistableIdleAction.Persist> causes the workflow to persist but it does not cause the workflow to unload.</span></span> <span data-ttu-id="62704-265"><xref:System.Activities.PersistableIdleAction.Unload> 会导致工作流持久保存并卸载。</span><span class="sxs-lookup"><span data-stu-id="62704-265"><xref:System.Activities.PersistableIdleAction.Unload> causes the workflow to persist and be unloaded.</span></span>

    <span data-ttu-id="62704-266">以下示例是完成的 `ConfigureWorkflowApplication` 方法。</span><span class="sxs-lookup"><span data-stu-id="62704-266">The following example is the completed `ConfigureWorkflowApplication` method.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)
        ' Configure the persistence store.
        wfApp.InstanceStore = store

        ' Add a StringWriter to the extensions. This captures the output
        ' from the WriteLine activities so we can display it in the form.
        Dim sw As New StringWriter()
        wfApp.Extensions.Add(sw)

        wfApp.Completed = _
            Sub(e As WorkflowApplicationCompletedEventArgs)
                If e.CompletionState = ActivityInstanceState.Faulted Then
                    UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                    UpdateStatus("Workflow Canceled.")
                Else
                    Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                    UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
                End If
                GameOver()
            End Sub

        wfApp.Aborted = _
            Sub(e As WorkflowApplicationAbortedEventArgs)
                UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
            End Sub

        wfApp.OnUnhandledException = _
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
                UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
                GameOver()
                Return UnhandledExceptionAction.Terminate
            End Function

        wfApp.PersistableIdle = _
            Function(e As WorkflowApplicationIdleEventArgs)
                ' Send the current WriteLine outputs to the status window.
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()
                For Each writer In writers
                    UpdateStatus(writer.ToString())
                Next
                Return PersistableIdleAction.Unload
            End Function
    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
        // Configure the persistence store.
        wfApp.InstanceStore = store;

        // Add a StringWriter to the extensions. This captures the output
        // from the WriteLine activities so we can display it in the form.
        var sw = new StringWriter();
        wfApp.Extensions.Add(sw);

        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
        {
            if (e.CompletionState == ActivityInstanceState.Faulted)
            {
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
            }
            else if (e.CompletionState == ActivityInstanceState.Canceled)
            {
                UpdateStatus("Workflow Canceled.");
            }
            else
            {
                int turns = Convert.ToInt32(e.Outputs["Turns"]);
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
            }
            GameOver();
        };

        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
        {
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
        };

        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
        {
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
            GameOver();
            return UnhandledExceptionAction.Terminate;
        };

        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
        {
            // Send the current WriteLine outputs to the status window.
            var writers = e.GetInstanceExtensions<StringWriter>();
            foreach (var writer in writers)
            {
                UpdateStatus(writer.ToString());
            }
            return PersistableIdleAction.Unload;
        };
    }
    ```

## <a name="to-enable-starting-and-resuming-multiple-workflow-types"></a><span data-ttu-id="62704-267">支持启动和恢复多个工作流类型</span><span class="sxs-lookup"><span data-stu-id="62704-267">To enable starting and resuming multiple workflow types</span></span>

<span data-ttu-id="62704-268">要恢复工作流实例，主机必须提供工作流定义。</span><span class="sxs-lookup"><span data-stu-id="62704-268">In order to resume a workflow instance, the host has to provide the workflow definition.</span></span> <span data-ttu-id="62704-269">在此教程中有三个工作流类型，且后续教程步骤会介绍这些类型的多个版本。</span><span class="sxs-lookup"><span data-stu-id="62704-269">In this tutorial there are three workflow types, and subsequent tutorial steps introduce multiple versions of these types.</span></span> <span data-ttu-id="62704-270">主机应用程序可通过 `WorkflowIdentity` 将标识信息与持久化工作流实例相关联。</span><span class="sxs-lookup"><span data-stu-id="62704-270">`WorkflowIdentity` provides a way for a host application to associate identifying information with a persisted workflow instance.</span></span> <span data-ttu-id="62704-271">本节中的步骤演示了如何创建一个实用工具类，以帮助将工作流标识从持久化工作流实例映射到对应的工作流定义。</span><span class="sxs-lookup"><span data-stu-id="62704-271">The steps in this section demonstrate how to create a utility class to assist with mapping the workflow identity from a persisted workflow instance to the corresponding workflow definition.</span></span> <span data-ttu-id="62704-272">有关 `WorkflowIdentity` 和版本控制的详细信息，请参阅[使用 WorkflowIdentity 和版本控制](using-workflowidentity-and-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="62704-272">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>

1. <span data-ttu-id="62704-273">在**解决方案资源管理器**中右键单击 " **NumberGuessWorkflowHost** "，然后选择 "**添加**"、"**类**"。</span><span class="sxs-lookup"><span data-stu-id="62704-273">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="62704-274">`WorkflowVersionMap`在 "**名称**" 框中键入，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="62704-274">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span></span>

2. <span data-ttu-id="62704-275">在包含其他 `using` 或 `Imports` 语句的文件的顶部添加以下 `using` 或 `Imports` 语句。</span><span class="sxs-lookup"><span data-stu-id="62704-275">Add the following `using` or `Imports` statements at the top of the file with the other `using` or `Imports` statements.</span></span>

    ```vb
    Imports System.Activities
    Imports NumberGuessWorkflowActivities
    ```

    ```csharp
    using System.Activities;
    using NumberGuessWorkflowActivities;
    ```

3. <span data-ttu-id="62704-276">使用以下声明替换 `WorkflowVersionMap` 类声明。</span><span class="sxs-lookup"><span data-stu-id="62704-276">Replace the `WorkflowVersionMap` class declaration with the following declaration.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        ' Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            ' Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
       }
    }
    ```

    <span data-ttu-id="62704-277">`WorkflowVersionMap` 包含与此教程中的三个工作流定义对应的三个工作流标识，并在以下各节中工作流启动和恢复时使用。</span><span class="sxs-lookup"><span data-stu-id="62704-277">`WorkflowVersionMap` contains three workflow identities that map to the three workflow definitions from this tutorial and is used in the following sections when workflows are started and resumed.</span></span>

## <a name="to-start-a-new-workflow"></a><span data-ttu-id="62704-278">启动新工作流</span><span class="sxs-lookup"><span data-stu-id="62704-278">To start a new workflow</span></span>

1. <span data-ttu-id="62704-279">为 `Click` 添加 `NewGame` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-279">Add a `Click` handler for `NewGame`.</span></span> <span data-ttu-id="62704-280">若要添加该处理程序，请切换到窗体的**设计视图**，然后双击 `NewGame` 。</span><span class="sxs-lookup"><span data-stu-id="62704-280">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span></span> <span data-ttu-id="62704-281">此时将添加 `NewGame_Click` 处理程序，视图将切换为窗体的代码视图。</span><span class="sxs-lookup"><span data-stu-id="62704-281">A `NewGame_Click` handler is added and the view switches to code view for the form.</span></span> <span data-ttu-id="62704-282">每当用户单击此按钮时，就会启动新工作流。</span><span class="sxs-lookup"><span data-stu-id="62704-282">Whenever the user clicks this button a new workflow is started.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click

    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="62704-283">将以下代码添加到 click 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-283">Add the following code to the click handler.</span></span> <span data-ttu-id="62704-284">此代码创建工作流输入自变量的字典，以变量名称作为键。</span><span class="sxs-lookup"><span data-stu-id="62704-284">This code creates a dictionary of input arguments for the workflow, keyed by argument name.</span></span> <span data-ttu-id="62704-285">此字典有一个条目，其中包含从范围组合框检索到的随机生成的数字范围。</span><span class="sxs-lookup"><span data-stu-id="62704-285">This dictionary has one entry that contains the range of the randomly generated number retrieved from the range combo box.</span></span>

    ```vb
    Dim inputs As New Dictionary(Of String, Object)()
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))
    ```

    ```csharp
    var inputs = new Dictionary<string, object>();
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));
    ```

3. <span data-ttu-id="62704-286">接下来，添加以下用于启动工作流的代码。</span><span class="sxs-lookup"><span data-stu-id="62704-286">Next, add the following code that starts the workflow.</span></span> <span data-ttu-id="62704-287">对应于所选工作流类型的 `WorkflowIdentity` 和工作流定义通过 `WorkflowVersionMap` 帮助器类进行检索。</span><span class="sxs-lookup"><span data-stu-id="62704-287">The `WorkflowIdentity` and workflow definition corresponding to the type of workflow selected are retrieved using the `WorkflowVersionMap` helper class.</span></span> <span data-ttu-id="62704-288">接下来，将使用工作流定义、`WorkflowApplication` 和输入变量字典创建新的 `WorkflowIdentity` 实例。</span><span class="sxs-lookup"><span data-stu-id="62704-288">Next, a new `WorkflowApplication` instance is created using the workflow definition, `WorkflowIdentity`, and dictionary of input arguments.</span></span>

    ```vb
    Dim identity As WorkflowIdentity = Nothing
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
    End Select

    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

    Dim wfApp = New WorkflowApplication(wf, inputs, identity)
    ```

    ```csharp
    WorkflowIdentity identity = null;
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;
    };

    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);
    ```

4. <span data-ttu-id="62704-289">接下来，添加以下代码，此代码将工作流添加到工作流列表中，并在窗体上显示工作流的版本信息。</span><span class="sxs-lookup"><span data-stu-id="62704-289">Next, add the following code which adds the workflow to the workflow list and displays the workflow's version information on the form.</span></span>

    ```vb
    ' Add the workflow to the list and display the version information.
    workflowStarting = True
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
    WorkflowVersion.Text = identity.ToString()
    workflowStarting = False
    ```

    ```csharp
    // Add the workflow to the list and display the version information.
    workflowStarting = true;
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
    WorkflowVersion.Text = identity.ToString();
    workflowStarting = false;
    ```

5. <span data-ttu-id="62704-290">调用 `ConfigureWorkflowApplication` 为此 `WorkflowApplication` 实例配置实例存储、扩展以及工作流生命周期处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-290">Call `ConfigureWorkflowApplication` to configure the instance store, extensions, and workflow lifecycle handlers for this `WorkflowApplication` instance.</span></span>

    ```vb
    ' Configure the instance store, extensions, and
    ' workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)
    ```

    ```csharp
    // Configure the instance store, extensions, and
    // workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp);
    ```

6. <span data-ttu-id="62704-291">最后，调用 `Run`。</span><span class="sxs-lookup"><span data-stu-id="62704-291">Finally, call `Run`.</span></span>

    ```vb
    ' Start the workflow.
    wfApp.Run()
    ```

    ```csharp
    // Start the workflow.
    wfApp.Run();
    ```

     <span data-ttu-id="62704-292">以下示例是完成的 `NewGame_Click` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-292">The following example is the completed `NewGame_Click` handler.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click
        ' Start a new workflow.
        Dim inputs As New Dictionary(Of String, Object)()
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))

        Dim identity As WorkflowIdentity = Nothing
        Select Case WorkflowType.SelectedItem.ToString()
            Case "SequentialNumberGuessWorkflow"
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity

            Case "StateMachineNumberGuessWorkflow"
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

            Case "FlowchartNumberGuessWorkflow"
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
        End Select

        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

        Dim wfApp = New WorkflowApplication(wf, inputs, identity)

        ' Add the workflow to the list and display the version information.
        workflowStarting = True
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
        WorkflowVersion.Text = identity.ToString()
        workflowStarting = False

        ' Configure the instance store, extensions, and
        ' workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp)

        ' Start the workflow.
        wfApp.Run()
    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {
        var inputs = new Dictionary<string, object>();
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));

        WorkflowIdentity identity = null;
        switch (WorkflowType.SelectedItem.ToString())
        {
            case "SequentialNumberGuessWorkflow":
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
                break;

            case "StateMachineNumberGuessWorkflow":
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
                break;

            case "FlowchartNumberGuessWorkflow":
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
                break;
        };

        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

        var wfApp = new WorkflowApplication(wf, inputs, identity);

        // Add the workflow to the list and display the version information.
        workflowStarting = true;
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
        WorkflowVersion.Text = identity.ToString();
        workflowStarting = false;

        // Configure the instance store, extensions, and
        // workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp);

        // Start the workflow.
        wfApp.Run();
    }
    ```

## <a name="to-resume-a-workflow"></a><span data-ttu-id="62704-293">恢复工作流</span><span class="sxs-lookup"><span data-stu-id="62704-293">To resume a workflow</span></span>

1. <span data-ttu-id="62704-294">为 `Click` 添加 `EnterGuess` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-294">Add a `Click` handler for `EnterGuess`.</span></span> <span data-ttu-id="62704-295">若要添加该处理程序，请切换到窗体的**设计视图**，然后双击 `EnterGuess` 。</span><span class="sxs-lookup"><span data-stu-id="62704-295">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span></span> <span data-ttu-id="62704-296">每当用户单击此按钮时，就会恢复工作流。</span><span class="sxs-lookup"><span data-stu-id="62704-296">Whenever the user clicks this button a workflow is resumed.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click

    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="62704-297">添加以下代码，以确保在工作流列表中选择了一个工作流，且用户的猜测有效。</span><span class="sxs-lookup"><span data-stu-id="62704-297">Add the following code to ensure that a workflow is selected in the workflow list, and that the user's guess is valid.</span></span>

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim userGuess As Integer
    If Not Int32.TryParse(Guess.Text, userGuess) Then
        MessageBox.Show("Please enter an integer.")
        Guess.SelectAll()
        Guess.Focus()
        Return
    End If
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    int guess;
    if (!Int32.TryParse(Guess.Text, out guess))
    {
        MessageBox.Show("Please enter an integer.");
        Guess.SelectAll();
        Guess.Focus();
        return;
    }
    ```

3. <span data-ttu-id="62704-298">接下来，检索持久化工作流实例的 `WorkflowApplicationInstance`。</span><span class="sxs-lookup"><span data-stu-id="62704-298">Next, retrieve the `WorkflowApplicationInstance` of the persisted workflow instance.</span></span> <span data-ttu-id="62704-299">`WorkflowApplicationInstance` 表示尚未与工作流定义关联的持久化工作流实例。</span><span class="sxs-lookup"><span data-stu-id="62704-299">A `WorkflowApplicationInstance` represents a persisted workflow instance that has not yet been associated with a workflow definition.</span></span> <span data-ttu-id="62704-300">`DefinitionIdentity` 的 `WorkflowApplicationInstance` 包含持久化工作流实例的 `WorkflowIdentity`。</span><span class="sxs-lookup"><span data-stu-id="62704-300">The `DefinitionIdentity` of the `WorkflowApplicationInstance` contains the `WorkflowIdentity` of the persisted workflow instance.</span></span> <span data-ttu-id="62704-301">本教程中使用 `WorkflowVersionMap` 实用工具类，将 `WorkflowIdentity` 映射到正确的工作流定义。</span><span class="sxs-lookup"><span data-stu-id="62704-301">In this tutorial, the `WorkflowVersionMap` utility class is used to map the `WorkflowIdentity` to the correct workflow definition.</span></span> <span data-ttu-id="62704-302">检索工作流定义后，即使用正确的工作流定义创建 `WorkflowApplication`。</span><span class="sxs-lookup"><span data-stu-id="62704-302">Once the workflow definition is retrieved, a `WorkflowApplication` is created, using the correct workflow definition.</span></span>

    ```vb
    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = _
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)
    ```

    ```csharp
    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf =
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);
    ```

4. <span data-ttu-id="62704-303">创建 `WorkflowApplication` 后，请调用 `ConfigureWorkflowApplication` 以配置实例存储、工作流生命周期处理程序以及扩展。</span><span class="sxs-lookup"><span data-stu-id="62704-303">Once the `WorkflowApplication` is created, configure the instance store, workflow lifecycle handlers, and extensions by calling `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="62704-304">每次创建新 `WorkflowApplication` 时都必须执行这些步骤，并且必须在将工作流实例加载到 `WorkflowApplication` 中之前完成。</span><span class="sxs-lookup"><span data-stu-id="62704-304">These steps must be done every time a new `WorkflowApplication` is created, and they must be done before the workflow instance is loaded into the `WorkflowApplication`.</span></span> <span data-ttu-id="62704-305">在加载工作流后，此工作流通过用户的猜测恢复执行。</span><span class="sxs-lookup"><span data-stu-id="62704-305">After the workflow is loaded, it is resumed with the user's guess.</span></span>

    ```vb
    ' Configure the extensions and lifecycle handlers.
    ' Do this before the instance is loaded. Once the instance is
    ' loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", userGuess)
    ```

    ```csharp
    // Configure the extensions and lifecycle handlers.
    // Do this before the instance is loaded. Once the instance is
    // loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", guess);
    ```

5. <span data-ttu-id="62704-306">最后，清除猜测文本框，并使窗体准备接受其他猜测。</span><span class="sxs-lookup"><span data-stu-id="62704-306">Finally, clear the guess textbox and prepare the form to accept another guess.</span></span>

    ```vb
    ' Clear the Guess textbox.
    Guess.Clear()
    Guess.Focus()
    ```

    ```csharp
    // Clear the Guess textbox.
    Guess.Clear();
    Guess.Focus();
    ```

    <span data-ttu-id="62704-307">以下示例是完成的 `EnterGuess_Click` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-307">The following example is the completed `EnterGuess_Click` handler.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click
        If WorkflowInstanceId = Guid.Empty Then
            MessageBox.Show("Please select a workflow.")
            Return
        End If

        Dim userGuess As Integer
        If Not Int32.TryParse(Guess.Text, userGuess) Then
            MessageBox.Show("Please enter an integer.")
            Guess.SelectAll()
            Guess.Focus()
            Return
        End If

        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        ' Use the persisted WorkflowIdentity to retrieve the correct workflow
        ' definition from the dictionary.
        Dim wf As Activity = _
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

        ' Associate the WorkflowApplication with the correct definition
        Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

        ' Configure the extensions and lifecycle handlers.
        ' Do this before the instance is loaded. Once the instance is
        ' loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp)

        ' Load the workflow.
        wfApp.Load(instance)

        ' Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", userGuess)

        ' Clear the Guess textbox.
        Guess.Clear()
        Guess.Focus()
    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {
        if (WorkflowInstanceId == Guid.Empty)
        {
            MessageBox.Show("Please select a workflow.");
            return;
        }

        int guess;
        if (!Int32.TryParse(Guess.Text, out guess))
        {
            MessageBox.Show("Please enter an integer.");
            Guess.SelectAll();
            Guess.Focus();
            return;
        }

        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);

        // Use the persisted WorkflowIdentity to retrieve the correct workflow
        // definition from the dictionary.
        Activity wf =
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

        // Associate the WorkflowApplication with the correct definition
        var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

        // Configure the extensions and lifecycle handlers.
        // Do this before the instance is loaded. Once the instance is
        // loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp);

        // Load the workflow.
        wfApp.Load(instance);

        // Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", guess);

        // Clear the Guess textbox.
        Guess.Clear();
        Guess.Focus();
    }
    ```

## <a name="to-terminate-a-workflow"></a><span data-ttu-id="62704-308">终止工作流</span><span class="sxs-lookup"><span data-stu-id="62704-308">To terminate a workflow</span></span>

1. <span data-ttu-id="62704-309">为 `Click` 添加 `QuitGame` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-309">Add a `Click` handler for `QuitGame`.</span></span> <span data-ttu-id="62704-310">若要添加该处理程序，请切换到窗体的**设计视图**，然后双击 `QuitGame` 。</span><span class="sxs-lookup"><span data-stu-id="62704-310">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span></span> <span data-ttu-id="62704-311">每当用户单击此按钮，即终止当前选择的工作流。</span><span class="sxs-lookup"><span data-stu-id="62704-311">Whenever the user clicks this button the currently selected workflow is terminated.</span></span>

    ```vb
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click

    End Sub
    ```

    ```csharp
    private void QuitGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="62704-312">将以下代码添加到 `QuitGame_Click` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-312">Add the following code to the `QuitGame_Click` handler.</span></span> <span data-ttu-id="62704-313">此代码首先进行检查，以确保在工作流列表中选择了一个工作流。</span><span class="sxs-lookup"><span data-stu-id="62704-313">This code first checks to ensure that a workflow is selected in the workflow list.</span></span> <span data-ttu-id="62704-314">然后，它将该持久化实例加载到 `WorkflowApplicationInstance` 中，使用 `DefinitionIdentity` 确定正确的工作流定义，然后初始化 `WorkflowApplication`。</span><span class="sxs-lookup"><span data-stu-id="62704-314">Then it loads the persisted instance into a `WorkflowApplicationInstance`, uses the `DefinitionIdentity` to determine the correct workflow definition, and then initializes the `WorkflowApplication`.</span></span> <span data-ttu-id="62704-315">接下来，通过调用 `ConfigureWorkflowApplication` 来配置扩展和工作流生命周期处理程序。</span><span class="sxs-lookup"><span data-stu-id="62704-315">Next the extensions and workflow lifecycle handlers are configured with a call to `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="62704-316">`WorkflowApplication` 配置好后，将加载它，然后调用 `Terminate`。</span><span class="sxs-lookup"><span data-stu-id="62704-316">Once the `WorkflowApplication` is configured, it is loaded, and then `Terminate` is called.</span></span>

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition.
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

    ' Configure the extensions and lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Terminate the workflow.
    wfApp.Terminate("User resigns.")
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

    // Configure the extensions and lifecycle handlers
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Terminate the workflow.
    wfApp.Terminate("User resigns.");
    ```

## <a name="to-build-and-run-the-application"></a><span data-ttu-id="62704-317">生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="62704-317">To build and run the application</span></span>

1. <span data-ttu-id="62704-318">双击**解决方案资源管理器**中的**Program.cs** （或**Module1**）以显示代码。</span><span class="sxs-lookup"><span data-stu-id="62704-318">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span></span>

2. <span data-ttu-id="62704-319">在包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。</span><span class="sxs-lookup"><span data-stu-id="62704-319">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="62704-320">从[如何：运行工作流](how-to-run-a-workflow.md)，删除或注释掉现有工作流宿主代码，并将其替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="62704-320">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span></span>

    ```vb
    Sub Main()
        Application.EnableVisualStyles()
        Application.Run(New WorkflowHostForm())
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        Application.EnableVisualStyles();
        Application.Run(new WorkflowHostForm());
    }
    ```

4. <span data-ttu-id="62704-321">在**解决方案资源管理器**中右键单击 " **NumberGuessWorkflowHost** "，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="62704-321">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span></span> <span data-ttu-id="62704-322">在 "**应用程序**" 选项卡中，为**输出类型**指定**Windows 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="62704-322">In the **Application** tab, specify **Windows Application** for the **Output type**.</span></span> <span data-ttu-id="62704-323">此步骤是可选的，但如果不执行此步骤，则除了窗体之外还会显示控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="62704-323">This step is optional, but if it is not followed the console window is displayed in addition to the form.</span></span>

5. <span data-ttu-id="62704-324">按 Ctrl+Shift+B 生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="62704-324">Press Ctrl+Shift+B to build the application.</span></span>

6. <span data-ttu-id="62704-325">确保将**NumberGuessWorkflowHost**设置为启动应用程序，然后按 Ctrl + F5 启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="62704-325">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span></span>

7. <span data-ttu-id="62704-326">为推测游戏选择一个范围，并选择要启动的工作流类型，然后单击 "**新建游戏**"。</span><span class="sxs-lookup"><span data-stu-id="62704-326">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="62704-327">在**推测**框中输入推测，然后单击 "**开始**" 以提交推测。</span><span class="sxs-lookup"><span data-stu-id="62704-327">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="62704-328">请注意，`WriteLine` 活动的输出将显示在窗体上。</span><span class="sxs-lookup"><span data-stu-id="62704-328">Note that the output from the `WriteLine` activities is displayed on the form.</span></span>

8. <span data-ttu-id="62704-329">使用不同的工作流类型和编号范围启动多个工作流，输入一些推测，并通过从 "**工作流实例 Id** " 列表中进行选择来在工作流之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="62704-329">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span></span>

    <span data-ttu-id="62704-330">请注意，当切换到新工作流时，状态窗口中不会显示以前的猜测值和工作流进度。</span><span class="sxs-lookup"><span data-stu-id="62704-330">Note that when you switch to a new workflow, the previous guesses and progress of the workflow are not displayed in the status window.</span></span> <span data-ttu-id="62704-331">状态不可用的原因是未将它捕获并保存在任何位置。</span><span class="sxs-lookup"><span data-stu-id="62704-331">The reason the status is not available is because it is not captured and saved anywhere.</span></span> <span data-ttu-id="62704-332">在本教程的后续步骤中，[如何：创建自定义跟踪参与者](how-to-create-a-custom-tracking-participant.md)，创建用于保存此信息的自定义跟踪参与者。</span><span class="sxs-lookup"><span data-stu-id="62704-332">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span></span>
