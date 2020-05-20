---
title: 如何：创建活动
description: 本文介绍如何在 Workflow Foundation 中创建两个活动：一个使用代码实现其逻辑，另一个使用其他活动定义。
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: dae099d102b0c85d09a1ef8bcce56e8a9096bd20
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419585"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="0cb83-103">如何：创建活动</span><span class="sxs-lookup"><span data-stu-id="0cb83-103">How to: Create an Activity</span></span>

<span data-ttu-id="0cb83-104">活动是 [!INCLUDE[wf1](../../../includes/wf1-md.md)] 中的核心行为单元。</span><span class="sxs-lookup"><span data-stu-id="0cb83-104">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="0cb83-105">活动的执行逻辑可以使用托管代码实现，也可以使用其他活动实现。</span><span class="sxs-lookup"><span data-stu-id="0cb83-105">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="0cb83-106">本主题演示如何创建两个活动。</span><span class="sxs-lookup"><span data-stu-id="0cb83-106">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="0cb83-107">第一个活动是简单活动，它使用代码来实现其执行逻辑。</span><span class="sxs-lookup"><span data-stu-id="0cb83-107">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="0cb83-108">第二个活动的实现是用其他活动定义的。</span><span class="sxs-lookup"><span data-stu-id="0cb83-108">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="0cb83-109">后续教程步骤会使用这些活动。</span><span class="sxs-lookup"><span data-stu-id="0cb83-109">These activities are used in following steps in the tutorial.</span></span>

> [!NOTE]
> <span data-ttu-id="0cb83-110">若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="0cb83-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="0cb83-111">创建活动库项目</span><span class="sxs-lookup"><span data-stu-id="0cb83-111">Create the activity library project</span></span>

1. <span data-ttu-id="0cb83-112">打开 Visual Studio，然后**New**  >  从 "**文件**" 菜单中选择 "新建**项目**"。</span><span class="sxs-lookup"><span data-stu-id="0cb83-112">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="0cb83-113">在 "**新建项目**" 对话框中的 "**已安装**" 类别下，选择 " **Visual c #**  >  **工作流**" （或**Visual Basic**  >  **工作流**） "。</span><span class="sxs-lookup"><span data-stu-id="0cb83-113">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="0cb83-114">如果看不到**工作流**模板类别，可能需要安装 Visual Studio 的**Windows Workflow Foundation**组件。</span><span class="sxs-lookup"><span data-stu-id="0cb83-114">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="0cb83-115">选择 "**新建项目**" 对话框左侧的 "**打开 Visual Studio 安装程序**" 链接。</span><span class="sxs-lookup"><span data-stu-id="0cb83-115">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="0cb83-116">在 Visual Studio 安装程序中，选择 "**单个组件**" 选项卡。然后，在 "**开发活动**" 类别下，选择 " **Windows Workflow Foundation** " 组件。</span><span class="sxs-lookup"><span data-stu-id="0cb83-116">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="0cb83-117">选择 "**修改**" 以安装组件。</span><span class="sxs-lookup"><span data-stu-id="0cb83-117">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="0cb83-118">选择 "**活动库**" 项目模板。</span><span class="sxs-lookup"><span data-stu-id="0cb83-118">Select the **Activity Library** project template.</span></span> <span data-ttu-id="0cb83-119">在“**名称**”框中键入 `NumberGuessWorkflowActivities`，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="0cb83-119">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="0cb83-120">在 **“解决方案资源管理器”** 中右键单击 **“Activity1.xaml”**，然后选择 **“删除”**。</span><span class="sxs-lookup"><span data-stu-id="0cb83-120">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="0cb83-121">单击 **“确定”** 进行确认。</span><span class="sxs-lookup"><span data-stu-id="0cb83-121">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="0cb83-122">创建 ReadInt 活动</span><span class="sxs-lookup"><span data-stu-id="0cb83-122">Create the ReadInt activity</span></span>

1. <span data-ttu-id="0cb83-123">从 "**项目**" 菜单中选择 "**添加新项**"。</span><span class="sxs-lookup"><span data-stu-id="0cb83-123">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="0cb83-124">在 "**已安装**的  >  **常见项**" 节点中，选择 "**工作流**"。</span><span class="sxs-lookup"><span data-stu-id="0cb83-124">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="0cb83-125">从 "**工作流**" 列表中选择 "**代码活动**"。</span><span class="sxs-lookup"><span data-stu-id="0cb83-125">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="0cb83-126">在“**名称**”框中键入 `ReadInt`，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="0cb83-126">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="0cb83-127">将现有的 `ReadInt` 定义替换为下面的定义。</span><span class="sxs-lookup"><span data-stu-id="0cb83-127">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="0cb83-128">`ReadInt` 活动派生自 <xref:System.Activities.NativeActivity%601> 而不是 <xref:System.Activities.CodeActivity>，这是默认的代码活动模板。</span><span class="sxs-lookup"><span data-stu-id="0cb83-128">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="0cb83-129">如果活动提供单个结果，可以使用 <xref:System.Activities.CodeActivity%601>，它是通过 <xref:System.Activities.Activity%601.Result%2A> 自变量公开的，但是 <xref:System.Activities.CodeActivity%601> 不支持使用书签，因此使用 <xref:System.Activities.NativeActivity%601>。</span><span class="sxs-lookup"><span data-stu-id="0cb83-129"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="0cb83-130">创建 Prompt 活动</span><span class="sxs-lookup"><span data-stu-id="0cb83-130">Create the Prompt activity</span></span>

1. <span data-ttu-id="0cb83-131">按**Ctrl** + **Shift** + **B**生成项目。</span><span class="sxs-lookup"><span data-stu-id="0cb83-131">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="0cb83-132">通过生成项目，可以使用此项目中的 `ReadInt` 活动生成此步骤中的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="0cb83-132">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="0cb83-133">从 "**项目**" 菜单中选择 "**添加新项**"。</span><span class="sxs-lookup"><span data-stu-id="0cb83-133">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="0cb83-134">在 "**已安装**的  >  **常见项**" 节点中，选择 "**工作流**"。</span><span class="sxs-lookup"><span data-stu-id="0cb83-134">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="0cb83-135">从 **“工作流”** 列表中选择 **“活动”**。</span><span class="sxs-lookup"><span data-stu-id="0cb83-135">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="0cb83-136">在“**名称**”框中键入 `Prompt`，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="0cb83-136">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="0cb83-137">双击 "**解决方案资源管理器**中的" **Prompt** "以在设计器中显示它（如果尚未显示）。</span><span class="sxs-lookup"><span data-stu-id="0cb83-137">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="0cb83-138">单击活动设计器左下角的 **“参数”**，显示 **“参数”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="0cb83-138">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="0cb83-139">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="0cb83-139">Click **Create Argument**.</span></span>

8. <span data-ttu-id="0cb83-140">在 `BookmarkName` "**名称**" 框中键入，从 "**方向**" 下拉列表**中**选择 "输入"，从 "**参数类型**" 下拉列表中选择 "**字符串**"，然后按**enter**保存该参数。</span><span class="sxs-lookup"><span data-stu-id="0cb83-140">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="0cb83-141">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="0cb83-141">Click **Create Argument**.</span></span>

10. <span data-ttu-id="0cb83-142">在 `Result` 新添加的参数下方的 "**名称**" 框中键入 `BookmarkName` ，从 "**方向**" 下拉列表中选择 "向**外**"，从 "**参数类型**" 下拉列表中选择 " **Int32** "，然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="0cb83-142">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="0cb83-143">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="0cb83-143">Click **Create Argument**.</span></span>

12. <span data-ttu-id="0cb83-144">在 `Text` "**名称**" 框中键入，从 "**方向**" 下拉列表**中**选择 "输入"，从 "**参数类型**" 下拉列表中选择 "**字符串**"，然后按**enter**保存该参数。</span><span class="sxs-lookup"><span data-stu-id="0cb83-144">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="0cb83-145">在以下步骤中，这三个参数将绑定到添加到 <xref:System.Activities.Statements.WriteLine> 活动中的 `ReadInt` 和 `Prompt` 活动的相应参数。</span><span class="sxs-lookup"><span data-stu-id="0cb83-145">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="0cb83-146">单击活动设计器左下角的 **“参数”**，关闭 **“参数”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="0cb83-146">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="0cb83-147">将 "**序列**" 活动从 "**工具箱**" 的 "**控制流**" 部分拖放到**Prompt**活动设计器的 "在**此处放置活动**" 标签上。</span><span class="sxs-lookup"><span data-stu-id="0cb83-147">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="0cb83-148">如果未显示 **“工具箱”** 窗口，请从 **“视图”** 菜单中选择 **“工具箱”**。</span><span class="sxs-lookup"><span data-stu-id="0cb83-148">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="0cb83-149">将 " **WriteLine** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 "**序列**" 活动的 "**放置活动位置**" 标签上。</span><span class="sxs-lookup"><span data-stu-id="0cb83-149">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="0cb83-150">将**WriteLine**活动的**text**参数绑定到**Prompt**活动的**Text**参数，方法是 `Text` 在 "**属性**" 窗口中键入 "**输入 c # 表达式**" 或 "**输入 VB 表达式**" 框，然后按**tab**键两次。</span><span class="sxs-lookup"><span data-stu-id="0cb83-150">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="0cb83-151">这会关闭 IntelliSense 列表成员窗口，并通过将选择范围移离属性保存属性值。</span><span class="sxs-lookup"><span data-stu-id="0cb83-151">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="0cb83-152">还可以通过在 `Text` 活动本身的 "**输入 c # 表达式**" 或 "**输入 VB 表达式**" 框中键入来设置此属性。</span><span class="sxs-lookup"><span data-stu-id="0cb83-152">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="0cb83-153">如果未显示 "**属性" 窗口**，请从 "**视图**" 菜单中选择 "**属性窗口**"。</span><span class="sxs-lookup"><span data-stu-id="0cb83-153">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="0cb83-154">将 " **ReadInt** " 活动从 "**工具箱**" 的 " **NumberGuessWorkflowActivities** " 部分拖放到 " **Sequence** " 活动中，使其位于 " **WriteLine** " 活动之后。</span><span class="sxs-lookup"><span data-stu-id="0cb83-154">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="0cb83-155">通过**BookmarkName**在**BookmarkName** "属性" **Prompt** **ReadInt** `BookmarkName` **窗口**中**BookmarkName**参数右侧的 "**输入 VB 表达式**" 框中键入，然后按**tab**键两次以关闭 "IntelliSense 列表成员" 窗口并保存属性，将 ReadInt 活动的 BookmarkName 参数绑定到 Prompt 活动的 BookmarkName 参数。</span><span class="sxs-lookup"><span data-stu-id="0cb83-155">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="0cb83-156">将**ReadInt**活动的**result**参数绑定到**Prompt**活动的**Result**参数，方法是 `Result` 在 "**属性" 窗口**中的**result**参数右侧的 "**输入 VB 表达式**" 框中键入，然后按**tab**键两次。</span><span class="sxs-lookup"><span data-stu-id="0cb83-156">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="0cb83-157">按**Ctrl** + **Shift** + **B**生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="0cb83-157">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0cb83-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0cb83-158">Next steps</span></span>

<span data-ttu-id="0cb83-159">有关如何使用这些活动创建工作流的说明，请参阅本教程中的 "[如何：创建工作流](how-to-create-a-workflow.md)" 教程中的下一步。</span><span class="sxs-lookup"><span data-stu-id="0cb83-159">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0cb83-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cb83-160">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="0cb83-161">设计和实现自定义活动</span><span class="sxs-lookup"><span data-stu-id="0cb83-161">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="0cb83-162">入门教程</span><span class="sxs-lookup"><span data-stu-id="0cb83-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="0cb83-163">如何：创建工作流</span><span class="sxs-lookup"><span data-stu-id="0cb83-163">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="0cb83-164">在自定义设计器中使用 ExpressionTextBox</span><span class="sxs-lookup"><span data-stu-id="0cb83-164">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
