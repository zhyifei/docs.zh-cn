---
title: How to create and run a long-running workflow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 10eb4e2947bed9cea89f1cda05272aa3fa0fadaa
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204883"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a><span data-ttu-id="6b108-102">How to create and run a long-running workflow</span><span class="sxs-lookup"><span data-stu-id="6b108-102">How to create and run a long-running workflow</span></span>

<span data-ttu-id="6b108-103">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span><span class="sxs-lookup"><span data-stu-id="6b108-103">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span></span> <span data-ttu-id="6b108-104">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span><span class="sxs-lookup"><span data-stu-id="6b108-104">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span></span> <span data-ttu-id="6b108-105">示例演示了启动工作流、工作流生命周期处理程序和恢复书签。</span><span class="sxs-lookup"><span data-stu-id="6b108-105">Examples were shown of starting workflows, workflow lifecycle handlers, and resuming bookmarks.</span></span> <span data-ttu-id="6b108-106">为了有效演示工作流持久性，需要一个支持启动和恢复多个工作流实例的更为复杂的工作流主机。</span><span class="sxs-lookup"><span data-stu-id="6b108-106">In order to demonstrate workflow persistence effectively, a more complex workflow host is required that supports starting and resuming multiple workflow instances.</span></span> <span data-ttu-id="6b108-107">教程中此步骤演示了如何创建 Windows 窗体主机应用程序，此 Windows 窗体主机应用程序支持启动和恢复多个工作流实例、工作流持久性，并为高级功能（如在后续教程步骤中演示的跟踪和版本控制）提供基础。</span><span class="sxs-lookup"><span data-stu-id="6b108-107">This step in the tutorial demonstrates how to create a Windows form host application that supports starting and resuming multiple workflow instances, workflow persistence, and provides a basis for the advanced features such as tracking and versioning that are demonstrated in subsequent tutorial steps.</span></span>

> [!NOTE]
> <span data-ttu-id="6b108-108">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="6b108-108">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span> <span data-ttu-id="6b108-109">If you did not complete all three types you can download a completed version of the steps from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="6b108-109">If you did not complete all three types you can download a completed version of the steps from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

> [!NOTE]
> <span data-ttu-id="6b108-110">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="6b108-110">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-persistence-database"></a><span data-ttu-id="6b108-111">创建持久性数据库</span><span class="sxs-lookup"><span data-stu-id="6b108-111">To create the persistence database</span></span>

1. <span data-ttu-id="6b108-112">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="6b108-112">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span></span> <span data-ttu-id="6b108-113">Right-click the **Databases** node on the local server, and select **New Database**.</span><span class="sxs-lookup"><span data-stu-id="6b108-113">Right-click the **Databases** node on the local server, and select **New Database**.</span></span> <span data-ttu-id="6b108-114">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b108-114">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b108-115">Ensure that you have **Create Database** permission on the local server before creating the database.</span><span class="sxs-lookup"><span data-stu-id="6b108-115">Ensure that you have **Create Database** permission on the local server before creating the database.</span></span>

2. <span data-ttu-id="6b108-116">Choose **Open**, **File** from the **File** menu.</span><span class="sxs-lookup"><span data-stu-id="6b108-116">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="6b108-117">Browse to the following folder: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span><span class="sxs-lookup"><span data-stu-id="6b108-117">Browse to the following folder: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span></span>

    <span data-ttu-id="6b108-118">Select the following two files and click **Open**.</span><span class="sxs-lookup"><span data-stu-id="6b108-118">Select the following two files and click **Open**.</span></span>

    - <span data-ttu-id="6b108-119">*SqlWorkflowInstanceStoreLogic.sql*</span><span class="sxs-lookup"><span data-stu-id="6b108-119">*SqlWorkflowInstanceStoreLogic.sql*</span></span>

    - <span data-ttu-id="6b108-120">*SqlWorkflowInstanceStoreSchema.sql*</span><span class="sxs-lookup"><span data-stu-id="6b108-120">*SqlWorkflowInstanceStoreSchema.sql*</span></span>

3. <span data-ttu-id="6b108-121">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span><span class="sxs-lookup"><span data-stu-id="6b108-121">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span></span> <span data-ttu-id="6b108-122">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span><span class="sxs-lookup"><span data-stu-id="6b108-122">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

4. <span data-ttu-id="6b108-123">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span><span class="sxs-lookup"><span data-stu-id="6b108-123">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span></span> <span data-ttu-id="6b108-124">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span><span class="sxs-lookup"><span data-stu-id="6b108-124">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

    > [!WARNING]
    > <span data-ttu-id="6b108-125">请务必按正确顺序执行前面两个步骤。</span><span class="sxs-lookup"><span data-stu-id="6b108-125">It is important to perform the previous two steps in the correct order.</span></span> <span data-ttu-id="6b108-126">如果不按顺序执行查询，系统会发生错误，并且持久性数据库会配置不正确。</span><span class="sxs-lookup"><span data-stu-id="6b108-126">If the queries are executed out of order, errors occur and the persistence database is not configured correctly.</span></span>

## <a name="to-add-the-reference-to-the-durableinstancing-assemblies"></a><span data-ttu-id="6b108-127">添加对 DurableInstancing 程序集的引用</span><span class="sxs-lookup"><span data-stu-id="6b108-127">To add the reference to the DurableInstancing assemblies</span></span>

1. <span data-ttu-id="6b108-128">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span><span class="sxs-lookup"><span data-stu-id="6b108-128">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span></span>

2. <span data-ttu-id="6b108-129">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span><span class="sxs-lookup"><span data-stu-id="6b108-129">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span></span> <span data-ttu-id="6b108-130">这将筛选程序集，使您更易于选择所需引用。</span><span class="sxs-lookup"><span data-stu-id="6b108-130">This filters the assemblies and makes the desired references easier to select.</span></span>

3. <span data-ttu-id="6b108-131">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b108-131">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span></span>

## <a name="to-create-the-workflow-host-form"></a><span data-ttu-id="6b108-132">创建工作流主机窗体</span><span class="sxs-lookup"><span data-stu-id="6b108-132">To create the workflow host form</span></span>

> [!NOTE]
> <span data-ttu-id="6b108-133">此过程中的步骤描述了如何手动添加和配置窗体。</span><span class="sxs-lookup"><span data-stu-id="6b108-133">The steps in this procedure describe how to add and configure the form manually.</span></span> <span data-ttu-id="6b108-134">如果需要，您可以下载教程的解决方案文件并将完成后的窗体添加到项目。</span><span class="sxs-lookup"><span data-stu-id="6b108-134">If desired, you can download the solution files for the tutorial and add the completed form to the project.</span></span> <span data-ttu-id="6b108-135">To download the tutorial files, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="6b108-135">To download the tutorial files, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span> <span data-ttu-id="6b108-136">Once the files are downloaded, right-click **NumberGuessWorkflowHost** and choose **Add Reference**.</span><span class="sxs-lookup"><span data-stu-id="6b108-136">Once the files are downloaded, right-click **NumberGuessWorkflowHost** and choose **Add Reference**.</span></span> <span data-ttu-id="6b108-137">Add a reference to **System.Windows.Forms** and **System.Drawing**.</span><span class="sxs-lookup"><span data-stu-id="6b108-137">Add a reference to **System.Windows.Forms** and **System.Drawing**.</span></span> <span data-ttu-id="6b108-138">These references are added automatically if you add a new form from the **Add**, **New Item** menu, but must be added manually when importing a form.</span><span class="sxs-lookup"><span data-stu-id="6b108-138">These references are added automatically if you add a new form from the **Add**, **New Item** menu, but must be added manually when importing a form.</span></span> <span data-ttu-id="6b108-139">Once the references are added, right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Existing Item**.</span><span class="sxs-lookup"><span data-stu-id="6b108-139">Once the references are added, right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Existing Item**.</span></span> <span data-ttu-id="6b108-140">Browse to the `Form` folder in the project files, select **WorkflowHostForm.cs** (or **WorkflowHostForm.vb**), and click **Add**.</span><span class="sxs-lookup"><span data-stu-id="6b108-140">Browse to the `Form` folder in the project files, select **WorkflowHostForm.cs** (or **WorkflowHostForm.vb**), and click **Add**.</span></span> <span data-ttu-id="6b108-141">If you choose to import the form, then you can skip down to the next section, [To add the properties and helper methods of the form](#to-add-the-properties-and-helper-methods-of-the-form).</span><span class="sxs-lookup"><span data-stu-id="6b108-141">If you choose to import the form, then you can skip down to the next section, [To add the properties and helper methods of the form](#to-add-the-properties-and-helper-methods-of-the-form).</span></span>

1. <span data-ttu-id="6b108-142">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span><span class="sxs-lookup"><span data-stu-id="6b108-142">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span></span>

2. <span data-ttu-id="6b108-143">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span><span class="sxs-lookup"><span data-stu-id="6b108-143">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span></span>

3. <span data-ttu-id="6b108-144">在窗体上配置以下属性。</span><span class="sxs-lookup"><span data-stu-id="6b108-144">Configure the following properties on the form.</span></span>

    |<span data-ttu-id="6b108-145">Property</span><span class="sxs-lookup"><span data-stu-id="6b108-145">Property</span></span>|<span data-ttu-id="6b108-146">“值”</span><span class="sxs-lookup"><span data-stu-id="6b108-146">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="6b108-147">FormBorderStyle</span><span class="sxs-lookup"><span data-stu-id="6b108-147">FormBorderStyle</span></span>|<span data-ttu-id="6b108-148">FixedSingle</span><span class="sxs-lookup"><span data-stu-id="6b108-148">FixedSingle</span></span>|
    |<span data-ttu-id="6b108-149">MaximizeBox</span><span class="sxs-lookup"><span data-stu-id="6b108-149">MaximizeBox</span></span>|<span data-ttu-id="6b108-150">False</span><span class="sxs-lookup"><span data-stu-id="6b108-150">False</span></span>|
    |<span data-ttu-id="6b108-151">大小</span><span class="sxs-lookup"><span data-stu-id="6b108-151">Size</span></span>|<span data-ttu-id="6b108-152">400, 420</span><span class="sxs-lookup"><span data-stu-id="6b108-152">400, 420</span></span>|

4. <span data-ttu-id="6b108-153">按照指定顺序将以下控件添加到窗体，并根据指示配置这些属性。</span><span class="sxs-lookup"><span data-stu-id="6b108-153">Add the following controls to the form in the order specified and configure the properties as directed.</span></span>

    |<span data-ttu-id="6b108-154">控件</span><span class="sxs-lookup"><span data-stu-id="6b108-154">Control</span></span>|<span data-ttu-id="6b108-155">Property: Value</span><span class="sxs-lookup"><span data-stu-id="6b108-155">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="6b108-156">**Button**</span><span class="sxs-lookup"><span data-stu-id="6b108-156">**Button**</span></span>|<span data-ttu-id="6b108-157">Name: NewGame</span><span class="sxs-lookup"><span data-stu-id="6b108-157">Name: NewGame</span></span><br /><br /> <span data-ttu-id="6b108-158">Location: 13, 13</span><span class="sxs-lookup"><span data-stu-id="6b108-158">Location: 13, 13</span></span><br /><br /> <span data-ttu-id="6b108-159">Size: 75, 23</span><span class="sxs-lookup"><span data-stu-id="6b108-159">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="6b108-160">Text: New Game</span><span class="sxs-lookup"><span data-stu-id="6b108-160">Text: New Game</span></span>|
    |<span data-ttu-id="6b108-161">**标签**</span><span class="sxs-lookup"><span data-stu-id="6b108-161">**Label**</span></span>|<span data-ttu-id="6b108-162">Location: 94, 18</span><span class="sxs-lookup"><span data-stu-id="6b108-162">Location: 94, 18</span></span><br /><br /> <span data-ttu-id="6b108-163">Text: Guess a number from 1 to</span><span class="sxs-lookup"><span data-stu-id="6b108-163">Text: Guess a number from 1 to</span></span>|
    |<span data-ttu-id="6b108-164">**组合框**</span><span class="sxs-lookup"><span data-stu-id="6b108-164">**ComboBox**</span></span>|<span data-ttu-id="6b108-165">Name: NumberRange</span><span class="sxs-lookup"><span data-stu-id="6b108-165">Name: NumberRange</span></span><br /><br /> <span data-ttu-id="6b108-166">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="6b108-166">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="6b108-167">Items: 10, 100, 1000</span><span class="sxs-lookup"><span data-stu-id="6b108-167">Items: 10, 100, 1000</span></span><br /><br /> <span data-ttu-id="6b108-168">Location: 228, 12</span><span class="sxs-lookup"><span data-stu-id="6b108-168">Location: 228, 12</span></span><br /><br /> <span data-ttu-id="6b108-169">Size: 143, 21</span><span class="sxs-lookup"><span data-stu-id="6b108-169">Size: 143, 21</span></span>|
    |<span data-ttu-id="6b108-170">**标签**</span><span class="sxs-lookup"><span data-stu-id="6b108-170">**Label**</span></span>|<span data-ttu-id="6b108-171">Location: 13, 43</span><span class="sxs-lookup"><span data-stu-id="6b108-171">Location: 13, 43</span></span><br /><br /> <span data-ttu-id="6b108-172">Text: Workflow type</span><span class="sxs-lookup"><span data-stu-id="6b108-172">Text: Workflow type</span></span>|
    |<span data-ttu-id="6b108-173">**组合框**</span><span class="sxs-lookup"><span data-stu-id="6b108-173">**ComboBox**</span></span>|<span data-ttu-id="6b108-174">Name: WorkflowType</span><span class="sxs-lookup"><span data-stu-id="6b108-174">Name: WorkflowType</span></span><br /><br /> <span data-ttu-id="6b108-175">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="6b108-175">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="6b108-176">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="6b108-176">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span></span><br /><br /> <span data-ttu-id="6b108-177">Location: 94, 40</span><span class="sxs-lookup"><span data-stu-id="6b108-177">Location: 94, 40</span></span><br /><br /> <span data-ttu-id="6b108-178">Size: 277, 21</span><span class="sxs-lookup"><span data-stu-id="6b108-178">Size: 277, 21</span></span>|
    |<span data-ttu-id="6b108-179">**标签**</span><span class="sxs-lookup"><span data-stu-id="6b108-179">**Label**</span></span>|<span data-ttu-id="6b108-180">Name: WorkflowVersion</span><span class="sxs-lookup"><span data-stu-id="6b108-180">Name: WorkflowVersion</span></span><br /><br /> <span data-ttu-id="6b108-181">Location: 13, 362</span><span class="sxs-lookup"><span data-stu-id="6b108-181">Location: 13, 362</span></span><br /><br /> <span data-ttu-id="6b108-182">Text: Workflow version</span><span class="sxs-lookup"><span data-stu-id="6b108-182">Text: Workflow version</span></span>|
    |<span data-ttu-id="6b108-183">**GroupBox**</span><span class="sxs-lookup"><span data-stu-id="6b108-183">**GroupBox**</span></span>|<span data-ttu-id="6b108-184">Location: 13, 67</span><span class="sxs-lookup"><span data-stu-id="6b108-184">Location: 13, 67</span></span><br /><br /> <span data-ttu-id="6b108-185">Size: 358, 287</span><span class="sxs-lookup"><span data-stu-id="6b108-185">Size: 358, 287</span></span><br /><br /> <span data-ttu-id="6b108-186">Text: Game</span><span class="sxs-lookup"><span data-stu-id="6b108-186">Text: Game</span></span>|

    > [!NOTE]
    > <span data-ttu-id="6b108-187">When adding the following controls, put them into the GroupBox.</span><span class="sxs-lookup"><span data-stu-id="6b108-187">When adding the following controls, put them into the GroupBox.</span></span>

    |<span data-ttu-id="6b108-188">控件</span><span class="sxs-lookup"><span data-stu-id="6b108-188">Control</span></span>|<span data-ttu-id="6b108-189">Property: Value</span><span class="sxs-lookup"><span data-stu-id="6b108-189">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="6b108-190">**标签**</span><span class="sxs-lookup"><span data-stu-id="6b108-190">**Label**</span></span>|<span data-ttu-id="6b108-191">Location: 7, 20</span><span class="sxs-lookup"><span data-stu-id="6b108-191">Location: 7, 20</span></span><br /><br /> <span data-ttu-id="6b108-192">Text: Workflow Instance Id</span><span class="sxs-lookup"><span data-stu-id="6b108-192">Text: Workflow Instance Id</span></span>|
    |<span data-ttu-id="6b108-193">**组合框**</span><span class="sxs-lookup"><span data-stu-id="6b108-193">**ComboBox**</span></span>|<span data-ttu-id="6b108-194">Name: InstanceId</span><span class="sxs-lookup"><span data-stu-id="6b108-194">Name: InstanceId</span></span><br /><br /> <span data-ttu-id="6b108-195">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="6b108-195">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="6b108-196">Location: 121, 17</span><span class="sxs-lookup"><span data-stu-id="6b108-196">Location: 121, 17</span></span><br /><br /> <span data-ttu-id="6b108-197">Size: 227, 21</span><span class="sxs-lookup"><span data-stu-id="6b108-197">Size: 227, 21</span></span>|
    |<span data-ttu-id="6b108-198">**标签**</span><span class="sxs-lookup"><span data-stu-id="6b108-198">**Label**</span></span>|<span data-ttu-id="6b108-199">Location: 7, 47</span><span class="sxs-lookup"><span data-stu-id="6b108-199">Location: 7, 47</span></span><br /><br /> <span data-ttu-id="6b108-200">Text: Guess</span><span class="sxs-lookup"><span data-stu-id="6b108-200">Text: Guess</span></span>|
    |<span data-ttu-id="6b108-201">**文本框**</span><span class="sxs-lookup"><span data-stu-id="6b108-201">**TextBox**</span></span>|<span data-ttu-id="6b108-202">Name: Guess</span><span class="sxs-lookup"><span data-stu-id="6b108-202">Name: Guess</span></span><br /><br /> <span data-ttu-id="6b108-203">Location: 50, 44</span><span class="sxs-lookup"><span data-stu-id="6b108-203">Location: 50, 44</span></span><br /><br /> <span data-ttu-id="6b108-204">Size: 65, 20</span><span class="sxs-lookup"><span data-stu-id="6b108-204">Size: 65, 20</span></span>|
    |<span data-ttu-id="6b108-205">**Button**</span><span class="sxs-lookup"><span data-stu-id="6b108-205">**Button**</span></span>|<span data-ttu-id="6b108-206">Name: EnterGuess</span><span class="sxs-lookup"><span data-stu-id="6b108-206">Name: EnterGuess</span></span><br /><br /> <span data-ttu-id="6b108-207">Location: 121, 42</span><span class="sxs-lookup"><span data-stu-id="6b108-207">Location: 121, 42</span></span><br /><br /> <span data-ttu-id="6b108-208">Size: 75, 23</span><span class="sxs-lookup"><span data-stu-id="6b108-208">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="6b108-209">Text: Enter Guess</span><span class="sxs-lookup"><span data-stu-id="6b108-209">Text: Enter Guess</span></span>|
    |<span data-ttu-id="6b108-210">**Button**</span><span class="sxs-lookup"><span data-stu-id="6b108-210">**Button**</span></span>|<span data-ttu-id="6b108-211">Name: QuitGame</span><span class="sxs-lookup"><span data-stu-id="6b108-211">Name: QuitGame</span></span><br /><br /> <span data-ttu-id="6b108-212">Location: 274, 42</span><span class="sxs-lookup"><span data-stu-id="6b108-212">Location: 274, 42</span></span><br /><br /> <span data-ttu-id="6b108-213">Size: 75, 23</span><span class="sxs-lookup"><span data-stu-id="6b108-213">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="6b108-214">Text: Quit</span><span class="sxs-lookup"><span data-stu-id="6b108-214">Text: Quit</span></span>|
    |<span data-ttu-id="6b108-215">**文本框**</span><span class="sxs-lookup"><span data-stu-id="6b108-215">**TextBox**</span></span>|<span data-ttu-id="6b108-216">Name: WorkflowStatus</span><span class="sxs-lookup"><span data-stu-id="6b108-216">Name: WorkflowStatus</span></span><br /><br /> <span data-ttu-id="6b108-217">Location: 10, 73</span><span class="sxs-lookup"><span data-stu-id="6b108-217">Location: 10, 73</span></span><br /><br /> <span data-ttu-id="6b108-218">Multiline: True</span><span class="sxs-lookup"><span data-stu-id="6b108-218">Multiline: True</span></span><br /><br /> <span data-ttu-id="6b108-219">ReadOnly: True</span><span class="sxs-lookup"><span data-stu-id="6b108-219">ReadOnly: True</span></span><br /><br /> <span data-ttu-id="6b108-220">ScrollBars: Vertical</span><span class="sxs-lookup"><span data-stu-id="6b108-220">ScrollBars: Vertical</span></span><br /><br /> <span data-ttu-id="6b108-221">Size: 338, 208</span><span class="sxs-lookup"><span data-stu-id="6b108-221">Size: 338, 208</span></span>|

5. <span data-ttu-id="6b108-222">Set the **AcceptButton** property of the form to **EnterGuess**.</span><span class="sxs-lookup"><span data-stu-id="6b108-222">Set the **AcceptButton** property of the form to **EnterGuess**.</span></span>

 <span data-ttu-id="6b108-223">以下示例展示了完成的窗体。</span><span class="sxs-lookup"><span data-stu-id="6b108-223">The following example illustrates the completed form.</span></span>

 ![Screenshot of a Windows Workflow Foundation Workflow Host Form.](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)

## <a name="to-add-the-properties-and-helper-methods-of-the-form"></a><span data-ttu-id="6b108-225">添加窗体的属性和帮助器方法</span><span class="sxs-lookup"><span data-stu-id="6b108-225">To add the properties and helper methods of the form</span></span>

<span data-ttu-id="6b108-226">本节的步骤将属性和帮助器添加至窗体类，此窗体类将配置窗体的 UI，以支持运行和恢复数字猜测工作流。</span><span class="sxs-lookup"><span data-stu-id="6b108-226">The steps in this section add properties and helper methods to the form class that configure the UI of the form to support running and resuming number guess workflows.</span></span>

1. <span data-ttu-id="6b108-227">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span><span class="sxs-lookup"><span data-stu-id="6b108-227">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>

2. <span data-ttu-id="6b108-228">在包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。</span><span class="sxs-lookup"><span data-stu-id="6b108-228">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

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

3. <span data-ttu-id="6b108-229">Add the following member declarations to the **WorkflowHostForm** class.</span><span class="sxs-lookup"><span data-stu-id="6b108-229">Add the following member declarations to the **WorkflowHostForm** class.</span></span>

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
    > <span data-ttu-id="6b108-230">如果您的连接字符串不同，请更新 `connectionString` 引用数据库。</span><span class="sxs-lookup"><span data-stu-id="6b108-230">If your connection string is different, update `connectionString` to refer to your database.</span></span>

4. <span data-ttu-id="6b108-231">将 `WorkflowInstanceId` 属性添加到 `WorkflowFormHost` 类中。</span><span class="sxs-lookup"><span data-stu-id="6b108-231">Add a `WorkflowInstanceId` property to the `WorkflowFormHost` class.</span></span>

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

    <span data-ttu-id="6b108-232">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span><span class="sxs-lookup"><span data-stu-id="6b108-232">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span></span>

5. <span data-ttu-id="6b108-233">为窗体 `Load` 事件添加处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-233">Add a handler for the form `Load` event.</span></span> <span data-ttu-id="6b108-234">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span><span class="sxs-lookup"><span data-stu-id="6b108-234">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span></span>

    ```vb
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load

    End Sub
    ```

    ```csharp
    private void WorkflowHostForm_Load(object sender, EventArgs e)
    {

    }
    ```

6. <span data-ttu-id="6b108-235">将下列代码添加到 `WorkflowHostForm_Load`。</span><span class="sxs-lookup"><span data-stu-id="6b108-235">Add the following code to `WorkflowHostForm_Load`.</span></span>

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

    <span data-ttu-id="6b108-236">窗体加载时，将配置 `SqlWorkflowInstanceStore`，范围和工作流类型组合框将设置为默认值，持久性工作流实例将添加到 `InstanceId` 组合框。</span><span class="sxs-lookup"><span data-stu-id="6b108-236">When the form loads, the `SqlWorkflowInstanceStore` is configured, the range and workflow type combo boxes are set to default values, and the persisted workflow instances are added to the `InstanceId` combo box.</span></span>

7. <span data-ttu-id="6b108-237">为 `SelectedIndexChanged` 添加 `InstanceId` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-237">Add a `SelectedIndexChanged` handler for `InstanceId`.</span></span> <span data-ttu-id="6b108-238">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span><span class="sxs-lookup"><span data-stu-id="6b108-238">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span></span>

    ```vb
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged

    End Sub
    ```

    ```csharp
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)
    {

    }
    ```

8. <span data-ttu-id="6b108-239">将下列代码添加到 `InstanceId_SelectedIndexChanged`。</span><span class="sxs-lookup"><span data-stu-id="6b108-239">Add the following code to `InstanceId_SelectedIndexChanged`.</span></span> <span data-ttu-id="6b108-240">只要用户使用组合框选择一个工作流，此处理程序就会更新状态窗口。</span><span class="sxs-lookup"><span data-stu-id="6b108-240">Whenever the user selects a workflow by using the combo box this handler updates the status window.</span></span>

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

9. <span data-ttu-id="6b108-241">将下面的 `ListPersistedWorkflows` 方法添加到窗体类中。</span><span class="sxs-lookup"><span data-stu-id="6b108-241">Add the following `ListPersistedWorkflows` method to the form class.</span></span>

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

    <span data-ttu-id="6b108-242">`ListPersistedWorkflows` 查询持久性工作流实例的实例存储，并将实例 ID 添加到 `cboInstanceId` 组合框。</span><span class="sxs-lookup"><span data-stu-id="6b108-242">`ListPersistedWorkflows` queries the instance store for persisted workflow instances, and adds the instance ids to the `cboInstanceId` combo box.</span></span>

10. <span data-ttu-id="6b108-243">将下面的 `UpdateStatus` 方法和对应的委托添加到窗体类中。</span><span class="sxs-lookup"><span data-stu-id="6b108-243">Add the following `UpdateStatus` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="6b108-244">此方法使用当前正在运行的工作流的状态来更新窗体上的状态窗口。</span><span class="sxs-lookup"><span data-stu-id="6b108-244">This method updates the status window on the form with the status of the currently running workflow.</span></span>

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

11. <span data-ttu-id="6b108-245">将下面的 `GameOver` 方法和对应的委托添加到窗体类中。</span><span class="sxs-lookup"><span data-stu-id="6b108-245">Add the following `GameOver` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="6b108-246">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span><span class="sxs-lookup"><span data-stu-id="6b108-246">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span></span>

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

## <a name="to-configure-the-instance-store-workflow-lifecycle-handlers-and-extensions"></a><span data-ttu-id="6b108-247">配置实例存储、工作流生命周期处理程序和扩展</span><span class="sxs-lookup"><span data-stu-id="6b108-247">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>

1. <span data-ttu-id="6b108-248">向窗体类添加 `ConfigureWorkflowApplication` 方法。</span><span class="sxs-lookup"><span data-stu-id="6b108-248">Add a `ConfigureWorkflowApplication` method to the form class.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)

    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
    }
    ```

    <span data-ttu-id="6b108-249">此方法配置 `WorkflowApplication`、添加所需扩展并添加工作流生命周期事件的处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-249">This method configures the `WorkflowApplication`, adds the desired extensions, and adds handlers for the workflow lifecycle events.</span></span>

2. <span data-ttu-id="6b108-250">在 `ConfigureWorkflowApplication` 中，指定 `SqlWorkflowInstanceStore` 的 `WorkflowApplication`。</span><span class="sxs-lookup"><span data-stu-id="6b108-250">In `ConfigureWorkflowApplication`, specify the `SqlWorkflowInstanceStore` for the `WorkflowApplication`.</span></span>

    ```vb
    ' Configure the persistence store.
    wfApp.InstanceStore = store
    ```

    ```csharp
    // Configure the persistence store.
    wfApp.InstanceStore = store;
    ```

3. <span data-ttu-id="6b108-251">接下来，创建一个 `StringWriter` 实例，并将它添加到 `Extensions` 的 `WorkflowApplication` 集合中。</span><span class="sxs-lookup"><span data-stu-id="6b108-251">Next, create a `StringWriter` instance and add it to the `Extensions` collection of the `WorkflowApplication`.</span></span> <span data-ttu-id="6b108-252">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span><span class="sxs-lookup"><span data-stu-id="6b108-252">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span></span> <span data-ttu-id="6b108-253">当工作流进入空闲状态时，`WriteLine` 输出可从 `StringWriter` 提取并显示在窗体上。</span><span class="sxs-lookup"><span data-stu-id="6b108-253">When the workflow becomes idle, the `WriteLine` output can be extracted from the `StringWriter` and displayed on the form.</span></span>

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

4. <span data-ttu-id="6b108-254">为 `Completed` 事件添加以下处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-254">Add the following handler for the `Completed` event.</span></span> <span data-ttu-id="6b108-255">在工作流成功完成时，执行猜测数字的轮数会显示到状态窗口。</span><span class="sxs-lookup"><span data-stu-id="6b108-255">When a workflow successfully completes, the number of turns taken to guess the number is displayed to the status window.</span></span> <span data-ttu-id="6b108-256">如果工作流终止，系统会显示导致终止的异常信息。</span><span class="sxs-lookup"><span data-stu-id="6b108-256">If the workflow terminates, the exception information that caused the termination is displayed.</span></span> <span data-ttu-id="6b108-257">在处理程序结尾处调用了 `GameOver` 方法，该方法从工作流列表中删除已完成的工作流。</span><span class="sxs-lookup"><span data-stu-id="6b108-257">At the end of the handler the `GameOver` method is called, which removes the completed workflow from the workflow list.</span></span>

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

5. <span data-ttu-id="6b108-258">添加以下 `Aborted` 和 `OnUnhandledException` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-258">Add the following `Aborted` and `OnUnhandledException` handlers.</span></span> <span data-ttu-id="6b108-259">`GameOver` 方法不从 `Aborted` 处理程序中调用，因为在工作流实例中止时，它并未终止，且以后可能恢复实例。</span><span class="sxs-lookup"><span data-stu-id="6b108-259">The `GameOver` method is not called from the `Aborted` handler because when a workflow instance is aborted, it does not terminate, and it is possible to resume the instance at a later time.</span></span>

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

6. <span data-ttu-id="6b108-260">添加以下 `PersistableIdle` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-260">Add the following `PersistableIdle` handler.</span></span> <span data-ttu-id="6b108-261">此处理程序检索添加的 `StringWriter` 扩展，提取 `WriteLine` 活动的输出，并将它显示在状态窗口中。</span><span class="sxs-lookup"><span data-stu-id="6b108-261">This handler retrieves the `StringWriter` extension that was added, extracts the output from the `WriteLine` activities, and displays it in the status window.</span></span>

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

    <span data-ttu-id="6b108-262"><xref:System.Activities.PersistableIdleAction> 枚举有三个值：<xref:System.Activities.PersistableIdleAction.None>、 <xref:System.Activities.PersistableIdleAction.Persist> 和 <xref:System.Activities.PersistableIdleAction.Unload>。</span><span class="sxs-lookup"><span data-stu-id="6b108-262">The <xref:System.Activities.PersistableIdleAction> enumeration has three values: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist>, and <xref:System.Activities.PersistableIdleAction.Unload>.</span></span> <span data-ttu-id="6b108-263"><xref:System.Activities.PersistableIdleAction.Persist> 会导致工作流持久保存，但不会导致工作流卸载。</span><span class="sxs-lookup"><span data-stu-id="6b108-263"><xref:System.Activities.PersistableIdleAction.Persist> causes the workflow to persist but it does not cause the workflow to unload.</span></span> <span data-ttu-id="6b108-264"><xref:System.Activities.PersistableIdleAction.Unload> 会导致工作流持久保存并卸载。</span><span class="sxs-lookup"><span data-stu-id="6b108-264"><xref:System.Activities.PersistableIdleAction.Unload> causes the workflow to persist and be unloaded.</span></span>

    <span data-ttu-id="6b108-265">以下示例是完成的 `ConfigureWorkflowApplication` 方法。</span><span class="sxs-lookup"><span data-stu-id="6b108-265">The following example is the completed `ConfigureWorkflowApplication` method.</span></span>

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

## <a name="to-enable-starting-and-resuming-multiple-workflow-types"></a><span data-ttu-id="6b108-266">支持启动和恢复多个工作流类型</span><span class="sxs-lookup"><span data-stu-id="6b108-266">To enable starting and resuming multiple workflow types</span></span>

<span data-ttu-id="6b108-267">要恢复工作流实例，主机必须提供工作流定义。</span><span class="sxs-lookup"><span data-stu-id="6b108-267">In order to resume a workflow instance, the host has to provide the workflow definition.</span></span> <span data-ttu-id="6b108-268">在此教程中有三个工作流类型，且后续教程步骤会介绍这些类型的多个版本。</span><span class="sxs-lookup"><span data-stu-id="6b108-268">In this tutorial there are three workflow types, and subsequent tutorial steps introduce multiple versions of these types.</span></span> <span data-ttu-id="6b108-269">主机应用程序可通过 `WorkflowIdentity` 将标识信息与持久化工作流实例相关联。</span><span class="sxs-lookup"><span data-stu-id="6b108-269">`WorkflowIdentity` provides a way for a host application to associate identifying information with a persisted workflow instance.</span></span> <span data-ttu-id="6b108-270">本节中的步骤演示了如何创建一个实用工具类，以帮助将工作流标识从持久化工作流实例映射到对应的工作流定义。</span><span class="sxs-lookup"><span data-stu-id="6b108-270">The steps in this section demonstrate how to create a utility class to assist with mapping the workflow identity from a persisted workflow instance to the corresponding workflow definition.</span></span> <span data-ttu-id="6b108-271">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="6b108-271">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>

1. <span data-ttu-id="6b108-272">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span><span class="sxs-lookup"><span data-stu-id="6b108-272">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="6b108-273">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span><span class="sxs-lookup"><span data-stu-id="6b108-273">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span></span>

2. <span data-ttu-id="6b108-274">在包含其他 `using` 或 `Imports` 语句的文件的顶部添加以下 `using` 或 `Imports` 语句。</span><span class="sxs-lookup"><span data-stu-id="6b108-274">Add the following `using` or `Imports` statements at the top of the file with the other `using` or `Imports` statements.</span></span>

    ```vb
    Imports System.Activities
    Imports NumberGuessWorkflowActivities
    ```

    ```csharp
    using System.Activities;
    using NumberGuessWorkflowActivities;
    ```

3. <span data-ttu-id="6b108-275">使用以下声明替换 `WorkflowVersionMap` 类声明。</span><span class="sxs-lookup"><span data-stu-id="6b108-275">Replace the `WorkflowVersionMap` class declaration with the following declaration.</span></span>

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

    <span data-ttu-id="6b108-276">`WorkflowVersionMap` 包含与此教程中的三个工作流定义对应的三个工作流标识，并在以下各节中工作流启动和恢复时使用。</span><span class="sxs-lookup"><span data-stu-id="6b108-276">`WorkflowVersionMap` contains three workflow identities that map to the three workflow definitions from this tutorial and is used in the following sections when workflows are started and resumed.</span></span>

## <a name="to-start-a-new-workflow"></a><span data-ttu-id="6b108-277">启动新工作流</span><span class="sxs-lookup"><span data-stu-id="6b108-277">To start a new workflow</span></span>

1. <span data-ttu-id="6b108-278">为 `Click` 添加 `NewGame` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-278">Add a `Click` handler for `NewGame`.</span></span> <span data-ttu-id="6b108-279">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span><span class="sxs-lookup"><span data-stu-id="6b108-279">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span></span> <span data-ttu-id="6b108-280">此时将添加 `NewGame_Click` 处理程序，视图将切换为窗体的代码视图。</span><span class="sxs-lookup"><span data-stu-id="6b108-280">A `NewGame_Click` handler is added and the view switches to code view for the form.</span></span> <span data-ttu-id="6b108-281">每当用户单击此按钮时，就会启动新工作流。</span><span class="sxs-lookup"><span data-stu-id="6b108-281">Whenever the user clicks this button a new workflow is started.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click

    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="6b108-282">将以下代码添加到 click 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-282">Add the following code to the click handler.</span></span> <span data-ttu-id="6b108-283">此代码创建工作流输入自变量的字典，以变量名称作为键。</span><span class="sxs-lookup"><span data-stu-id="6b108-283">This code creates a dictionary of input arguments for the workflow, keyed by argument name.</span></span> <span data-ttu-id="6b108-284">此字典有一个条目，其中包含从范围组合框检索到的随机生成的数字范围。</span><span class="sxs-lookup"><span data-stu-id="6b108-284">This dictionary has one entry that contains the range of the randomly generated number retrieved from the range combo box.</span></span>

    ```vb
    Dim inputs As New Dictionary(Of String, Object)()
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))
    ```

    ```csharp
    var inputs = new Dictionary<string, object>();
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));
    ```

3. <span data-ttu-id="6b108-285">接下来，添加以下用于启动工作流的代码。</span><span class="sxs-lookup"><span data-stu-id="6b108-285">Next, add the following code that starts the workflow.</span></span> <span data-ttu-id="6b108-286">对应于所选工作流类型的 `WorkflowIdentity` 和工作流定义通过 `WorkflowVersionMap` 帮助器类进行检索。</span><span class="sxs-lookup"><span data-stu-id="6b108-286">The `WorkflowIdentity` and workflow definition corresponding to the type of workflow selected are retrieved using the `WorkflowVersionMap` helper class.</span></span> <span data-ttu-id="6b108-287">接下来，将使用工作流定义、`WorkflowApplication` 和输入变量字典创建新的 `WorkflowIdentity` 实例。</span><span class="sxs-lookup"><span data-stu-id="6b108-287">Next, a new `WorkflowApplication` instance is created using the workflow definition, `WorkflowIdentity`, and dictionary of input arguments.</span></span>

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

4. <span data-ttu-id="6b108-288">接下来，添加以下代码，此代码将工作流添加到工作流列表中，并在窗体上显示工作流的版本信息。</span><span class="sxs-lookup"><span data-stu-id="6b108-288">Next, add the following code which adds the workflow to the workflow list and displays the workflow's version information on the form.</span></span>

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

5. <span data-ttu-id="6b108-289">调用 `ConfigureWorkflowApplication` 为此 `WorkflowApplication` 实例配置实例存储、扩展以及工作流生命周期处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-289">Call `ConfigureWorkflowApplication` to configure the instance store, extensions, and workflow lifecycle handlers for this `WorkflowApplication` instance.</span></span>

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

6. <span data-ttu-id="6b108-290">最后，调用 `Run`。</span><span class="sxs-lookup"><span data-stu-id="6b108-290">Finally, call `Run`.</span></span>

    ```vb
    ' Start the workflow.
    wfApp.Run()
    ```

    ```csharp
    // Start the workflow.
    wfApp.Run();
    ```

     <span data-ttu-id="6b108-291">以下示例是完成的 `NewGame_Click` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-291">The following example is the completed `NewGame_Click` handler.</span></span>

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

## <a name="to-resume-a-workflow"></a><span data-ttu-id="6b108-292">恢复工作流</span><span class="sxs-lookup"><span data-stu-id="6b108-292">To resume a workflow</span></span>

1. <span data-ttu-id="6b108-293">为 `Click` 添加 `EnterGuess` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-293">Add a `Click` handler for `EnterGuess`.</span></span> <span data-ttu-id="6b108-294">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span><span class="sxs-lookup"><span data-stu-id="6b108-294">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span></span> <span data-ttu-id="6b108-295">每当用户单击此按钮时，就会恢复工作流。</span><span class="sxs-lookup"><span data-stu-id="6b108-295">Whenever the user clicks this button a workflow is resumed.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click

    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="6b108-296">添加以下代码，以确保在工作流列表中选择了一个工作流，且用户的猜测有效。</span><span class="sxs-lookup"><span data-stu-id="6b108-296">Add the following code to ensure that a workflow is selected in the workflow list, and that the user's guess is valid.</span></span>

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

3. <span data-ttu-id="6b108-297">接下来，检索持久化工作流实例的 `WorkflowApplicationInstance`。</span><span class="sxs-lookup"><span data-stu-id="6b108-297">Next, retrieve the `WorkflowApplicationInstance` of the persisted workflow instance.</span></span> <span data-ttu-id="6b108-298">`WorkflowApplicationInstance` 表示尚未与工作流定义关联的持久化工作流实例。</span><span class="sxs-lookup"><span data-stu-id="6b108-298">A `WorkflowApplicationInstance` represents a persisted workflow instance that has not yet been associated with a workflow definition.</span></span> <span data-ttu-id="6b108-299">`DefinitionIdentity` 的 `WorkflowApplicationInstance` 包含持久化工作流实例的 `WorkflowIdentity`。</span><span class="sxs-lookup"><span data-stu-id="6b108-299">The `DefinitionIdentity` of the `WorkflowApplicationInstance` contains the `WorkflowIdentity` of the persisted workflow instance.</span></span> <span data-ttu-id="6b108-300">本教程中使用 `WorkflowVersionMap` 实用工具类，将 `WorkflowIdentity` 映射到正确的工作流定义。</span><span class="sxs-lookup"><span data-stu-id="6b108-300">In this tutorial, the `WorkflowVersionMap` utility class is used to map the `WorkflowIdentity` to the correct workflow definition.</span></span> <span data-ttu-id="6b108-301">检索工作流定义后，即使用正确的工作流定义创建 `WorkflowApplication`。</span><span class="sxs-lookup"><span data-stu-id="6b108-301">Once the workflow definition is retrieved, a `WorkflowApplication` is created, using the correct workflow definition.</span></span>

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

4. <span data-ttu-id="6b108-302">创建 `WorkflowApplication` 后，请调用 `ConfigureWorkflowApplication` 以配置实例存储、工作流生命周期处理程序以及扩展。</span><span class="sxs-lookup"><span data-stu-id="6b108-302">Once the `WorkflowApplication` is created, configure the instance store, workflow lifecycle handlers, and extensions by calling `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="6b108-303">每次创建新 `WorkflowApplication` 时都必须执行这些步骤，并且必须在将工作流实例加载到 `WorkflowApplication` 中之前完成。</span><span class="sxs-lookup"><span data-stu-id="6b108-303">These steps must be done every time a new `WorkflowApplication` is created, and they must be done before the workflow instance is loaded into the `WorkflowApplication`.</span></span> <span data-ttu-id="6b108-304">在加载工作流后，此工作流通过用户的猜测恢复执行。</span><span class="sxs-lookup"><span data-stu-id="6b108-304">After the workflow is loaded, it is resumed with the user's guess.</span></span>

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

5. <span data-ttu-id="6b108-305">最后，清除猜测文本框，并使窗体准备接受其他猜测。</span><span class="sxs-lookup"><span data-stu-id="6b108-305">Finally, clear the guess textbox and prepare the form to accept another guess.</span></span>

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

    <span data-ttu-id="6b108-306">以下示例是完成的 `EnterGuess_Click` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-306">The following example is the completed `EnterGuess_Click` handler.</span></span>

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

## <a name="to-terminate-a-workflow"></a><span data-ttu-id="6b108-307">终止工作流</span><span class="sxs-lookup"><span data-stu-id="6b108-307">To terminate a workflow</span></span>

1. <span data-ttu-id="6b108-308">为 `Click` 添加 `QuitGame` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-308">Add a `Click` handler for `QuitGame`.</span></span> <span data-ttu-id="6b108-309">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span><span class="sxs-lookup"><span data-stu-id="6b108-309">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span></span> <span data-ttu-id="6b108-310">每当用户单击此按钮，即终止当前选择的工作流。</span><span class="sxs-lookup"><span data-stu-id="6b108-310">Whenever the user clicks this button the currently selected workflow is terminated.</span></span>

    ```vb
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click

    End Sub
    ```

    ```csharp
    private void QuitGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="6b108-311">将以下代码添加到 `QuitGame_Click` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-311">Add the following code to the `QuitGame_Click` handler.</span></span> <span data-ttu-id="6b108-312">此代码首先进行检查，以确保在工作流列表中选择了一个工作流。</span><span class="sxs-lookup"><span data-stu-id="6b108-312">This code first checks to ensure that a workflow is selected in the workflow list.</span></span> <span data-ttu-id="6b108-313">然后，它将该持久化实例加载到 `WorkflowApplicationInstance` 中，使用 `DefinitionIdentity` 确定正确的工作流定义，然后初始化 `WorkflowApplication`。</span><span class="sxs-lookup"><span data-stu-id="6b108-313">Then it loads the persisted instance into a `WorkflowApplicationInstance`, uses the `DefinitionIdentity` to determine the correct workflow definition, and then initializes the `WorkflowApplication`.</span></span> <span data-ttu-id="6b108-314">接下来，通过调用 `ConfigureWorkflowApplication` 来配置扩展和工作流生命周期处理程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-314">Next the extensions and workflow lifecycle handlers are configured with a call to `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="6b108-315">`WorkflowApplication` 配置好后，将加载它，然后调用 `Terminate`。</span><span class="sxs-lookup"><span data-stu-id="6b108-315">Once the `WorkflowApplication` is configured, it is loaded, and then `Terminate` is called.</span></span>

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

## <a name="to-build-and-run-the-application"></a><span data-ttu-id="6b108-316">生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="6b108-316">To build and run the application</span></span>

1. <span data-ttu-id="6b108-317">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span><span class="sxs-lookup"><span data-stu-id="6b108-317">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span></span>

2. <span data-ttu-id="6b108-318">在包含其他 `using`（或 `Imports`）语句的文件的顶部添加以下 `using`（或 `Imports`）语句。</span><span class="sxs-lookup"><span data-stu-id="6b108-318">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="6b108-319">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span><span class="sxs-lookup"><span data-stu-id="6b108-319">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span></span>

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

4. <span data-ttu-id="6b108-320">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span><span class="sxs-lookup"><span data-stu-id="6b108-320">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span></span> <span data-ttu-id="6b108-321">In the **Application** tab, specify **Windows Application** for the **Output type**.</span><span class="sxs-lookup"><span data-stu-id="6b108-321">In the **Application** tab, specify **Windows Application** for the **Output type**.</span></span> <span data-ttu-id="6b108-322">此步骤是可选的，但如果不执行此步骤，则除了窗体之外还会显示控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="6b108-322">This step is optional, but if it is not followed the console window is displayed in addition to the form.</span></span>

5. <span data-ttu-id="6b108-323">按 Ctrl+Shift+B 生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b108-323">Press Ctrl+Shift+B to build the application.</span></span>

6. <span data-ttu-id="6b108-324">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span><span class="sxs-lookup"><span data-stu-id="6b108-324">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span></span>

7. <span data-ttu-id="6b108-325">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span><span class="sxs-lookup"><span data-stu-id="6b108-325">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="6b108-326">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span><span class="sxs-lookup"><span data-stu-id="6b108-326">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="6b108-327">请注意，`WriteLine` 活动的输出将显示在窗体上。</span><span class="sxs-lookup"><span data-stu-id="6b108-327">Note that the output from the `WriteLine` activities is displayed on the form.</span></span>

8. <span data-ttu-id="6b108-328">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span><span class="sxs-lookup"><span data-stu-id="6b108-328">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span></span>

    <span data-ttu-id="6b108-329">请注意，当切换到新工作流时，状态窗口中不会显示以前的猜测值和工作流进度。</span><span class="sxs-lookup"><span data-stu-id="6b108-329">Note that when you switch to a new workflow, the previous guesses and progress of the workflow are not displayed in the status window.</span></span> <span data-ttu-id="6b108-330">状态不可用的原因是未将它捕获并保存在任何位置。</span><span class="sxs-lookup"><span data-stu-id="6b108-330">The reason the status is not available is because it is not captured and saved anywhere.</span></span> <span data-ttu-id="6b108-331">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span><span class="sxs-lookup"><span data-stu-id="6b108-331">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span></span>
