---
title: "在 .NET Framework 4 工作流中使用 Interop 活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a02d6dbc7c6f6583a174bd10853d8c8070ac273
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a><span data-ttu-id="b622c-102">在 .NET Framework 4 工作流中使用 Interop 活动</span><span class="sxs-lookup"><span data-stu-id="b622c-102">Using the Interop Activity in a .NET Framework 4 Workflow</span></span>
<span data-ttu-id="b622c-103">通过使用 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 活动，可在 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 工作流中使用通过 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 或 <xref:System.Activities.Statements.Interop> 创建的活动。</span><span class="sxs-lookup"><span data-stu-id="b622c-103">Activities created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] or [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] can be used in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow by using the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="b622c-104">本主题概述如何使用 <xref:System.Activities.Statements.Interop> 活动。</span><span class="sxs-lookup"><span data-stu-id="b622c-104">This topic provides an overview of using the <xref:System.Activities.Statements.Interop> activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b622c-105"><xref:System.Activities.Statements.Interop>活动在工作流的项目具有除非未出现在工作流设计器工具箱其**目标框架**设置设为**.Net Framework 4**或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b622c-105">The <xref:System.Activities.Statements.Interop> activity does not appear in the workflow designer toolbox unless the workflow's project has its **Target Framework** setting set to **.Net Framework 4** or later.</span></span>  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a><span data-ttu-id="b622c-106">在 .NET Framework 4.5 工作流中使用 Interop 活动</span><span class="sxs-lookup"><span data-stu-id="b622c-106">Using the Interop Activity in .NET Framework 4.5 Workflows</span></span>  
 <span data-ttu-id="b622c-107">在本主题中，将要创建一个包含 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 活动的 `DiscountCalculator` 活动库。</span><span class="sxs-lookup"><span data-stu-id="b622c-107">In this topic, a [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity library is created that contains a `DiscountCalculator` activity.</span></span> <span data-ttu-id="b622c-108">`DiscountCalculator` 基于购买量计算折扣，它由包含一个 <xref:System.Workflow.Activities.SequenceActivity> 的 <xref:System.Workflow.Activities.PolicyActivity> 组成。</span><span class="sxs-lookup"><span data-stu-id="b622c-108">The `DiscountCalculator` calculates a discount based on a purchase amount and consists of a <xref:System.Workflow.Activities.SequenceActivity> that contains a <xref:System.Workflow.Activities.PolicyActivity>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b622c-109">本主题中创建的 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 活动使用 <xref:System.Workflow.Activities.PolicyActivity> 来实现该活动的逻辑。</span><span class="sxs-lookup"><span data-stu-id="b622c-109">The [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity created in this topic uses a <xref:System.Workflow.Activities.PolicyActivity> to implement the logic of the activity.</span></span> <span data-ttu-id="b622c-110">不必使用自定义 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 活动或 <xref:System.Activities.Statements.Interop> 活动也能在 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 工作流中使用规则。</span><span class="sxs-lookup"><span data-stu-id="b622c-110">It is not required to use a custom [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity or the <xref:System.Activities.Statements.Interop> activity in order to use rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="b622c-111">有关使用中的规则的示例[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]流，并且不使用<xref:System.Activities.Statements.Interop>活动，请参阅[.NET Framework 4.5 中的策略活动](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md)示例。</span><span class="sxs-lookup"><span data-stu-id="b622c-111">For an example of using rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow without using the <xref:System.Activities.Statements.Interop> activity, see the [Policy Activity in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) sample.</span></span>  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a><span data-ttu-id="b622c-112">创建 .NET Framework 3.5 活动库项目</span><span class="sxs-lookup"><span data-stu-id="b622c-112">To create the .NET Framework 3.5 activity library project</span></span>  
  
1.  <span data-ttu-id="b622c-113">打开[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]和选择**新建**然后**项目...**</span><span class="sxs-lookup"><span data-stu-id="b622c-113">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New** and then **Project…**</span></span> <span data-ttu-id="b622c-114">从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="b622c-114">from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="b622c-115">展开**其他项目类型**中的节点**已安装的模板**窗格中，然后选择**Visual Studio 解决方案**。</span><span class="sxs-lookup"><span data-stu-id="b622c-115">Expand the **Other Project Types** node in the **Installed Templates** pane and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="b622c-116">选择**空白解决方案**从**Visual Studio 解决方案**列表。</span><span class="sxs-lookup"><span data-stu-id="b622c-116">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="b622c-117">类型`PolicyInteropDemo`中**名称**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-117">Type `PolicyInteropDemo` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="b622c-118">右键单击**PolicyInteropDemo**中**解决方案资源管理器**和选择**添加**然后**新项目...**.</span><span class="sxs-lookup"><span data-stu-id="b622c-118">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add** and then **New Project…**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b622c-119">如果**解决方案资源管理器**窗口不可见，则选择**解决方案资源管理器**从**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="b622c-119">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="b622c-120">在**已安装的模板**列表中，选择**Visual C#**然后**工作流**。</span><span class="sxs-lookup"><span data-stu-id="b622c-120">In the **Installed Templates** list, select **Visual C#** and then **Workflow**.</span></span> <span data-ttu-id="b622c-121">选择**.NET Framework 3.5**从.NET Framework 版本下拉列表，，然后选择**工作流活动库**从**模板**列表。</span><span class="sxs-lookup"><span data-stu-id="b622c-121">Select **.NET Framework 3.5** from the .NET Framework version drop-down list, and then select **Workflow Activity Library** from the **Templates** list.</span></span>  
  
6.  <span data-ttu-id="b622c-122">类型`PolicyActivityLibrary`中**名称**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-122">Type `PolicyActivityLibrary` in the **Name** box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="b622c-123">右键单击**Activity1.cs**中**解决方案资源管理器**和选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="b622c-123">Right-click **Activity1.cs** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="b622c-124">单击 **“确定”** 以确认。</span><span class="sxs-lookup"><span data-stu-id="b622c-124">Click **OK** to confirm.</span></span>  
  
#### <a name="to-create-the-discountcalculator-activity"></a><span data-ttu-id="b622c-125">创建 DiscountCalculator 活动</span><span class="sxs-lookup"><span data-stu-id="b622c-125">To create the DiscountCalculator activity</span></span>  
  
1.  <span data-ttu-id="b622c-126">右键单击**PolicyActivityLibrary**中**解决方案资源管理器**和选择**添加**然后**活动...**.</span><span class="sxs-lookup"><span data-stu-id="b622c-126">Right-click **PolicyActivityLibrary** in **Solution Explorer** and select **Add** and then **Activity…**.</span></span>  
  
2.  <span data-ttu-id="b622c-127">选择**Activity （具有单独的代码）**从**Visual C# 项**列表。</span><span class="sxs-lookup"><span data-stu-id="b622c-127">Select **Activity (with code separation)** from the **Visual C# Items** list.</span></span> <span data-ttu-id="b622c-128">类型`DiscountCalculator`中**名称**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-128">Type `DiscountCalculator` in the **Name** box and click **OK**.</span></span>  
  
3.  <span data-ttu-id="b622c-129">右键单击**DiscountCalculator.xoml**中**解决方案资源管理器**和选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="b622c-129">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Code**.</span></span>  
  
4.  <span data-ttu-id="b622c-130">将以下三个属性添加到 `DiscountCalculator` 类中。</span><span class="sxs-lookup"><span data-stu-id="b622c-130">Add the following three properties to the `DiscountCalculator` class.</span></span>  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  <span data-ttu-id="b622c-131">右键单击**DiscountCalculator.xoml**中**解决方案资源管理器**和选择**视图设计器**。</span><span class="sxs-lookup"><span data-stu-id="b622c-131">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Designer**.</span></span>  
  
6.  <span data-ttu-id="b622c-132">拖动**策略**活动从**Windows Workflow v3.0**部分**工具箱**拖放**DiscountCalculator**活动.</span><span class="sxs-lookup"><span data-stu-id="b622c-132">Drag a **Policy** activity from the **Windows Workflow v3.0** section of the **Toolbox** and drop it in the **DiscountCalculator** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b622c-133">如果**工具箱**窗口不可见，则选择**工具箱**从**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="b622c-133">If the **Toolbox** window is not visible, select **Toolbox** from the **View** menu.</span></span>  
  
#### <a name="to-configure-the-rules"></a><span data-ttu-id="b622c-134">配置规则</span><span class="sxs-lookup"><span data-stu-id="b622c-134">To configure the rules</span></span>  
  
1.  <span data-ttu-id="b622c-135">单击新添加**策略**活动以选择它，如果尚未选择。</span><span class="sxs-lookup"><span data-stu-id="b622c-135">Click the newly added **Policy** activity to select it, if it is not already selected.</span></span>  
  
2.  <span data-ttu-id="b622c-136">单击**rulesetreference**中的属性**属性**窗口选择它，然后单击属性右侧的省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="b622c-136">Click the **RuleSetReference** property in the **Properties** window to select it, and click the ellipsis button to the right of the property.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b622c-137">如果**属性**窗口不可见，请选择**属性窗口**从**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="b622c-137">If the **Properties** window is not visible, choose **Properties Window** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="b622c-138">选择**新单击...**.</span><span class="sxs-lookup"><span data-stu-id="b622c-138">Select **Click New…**.</span></span>  
  
4.  <span data-ttu-id="b622c-139">单击**添加规则**。</span><span class="sxs-lookup"><span data-stu-id="b622c-139">Click **Add Rule**.</span></span>  
  
5.  <span data-ttu-id="b622c-140">以下表达式键入**条件**框。</span><span class="sxs-lookup"><span data-stu-id="b622c-140">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  <span data-ttu-id="b622c-141">以下表达式键入**Then 操作**框。</span><span class="sxs-lookup"><span data-stu-id="b622c-141">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  <span data-ttu-id="b622c-142">单击**添加规则**。</span><span class="sxs-lookup"><span data-stu-id="b622c-142">Click **Add Rule**.</span></span>  
  
8.  <span data-ttu-id="b622c-143">以下表达式键入**条件**框。</span><span class="sxs-lookup"><span data-stu-id="b622c-143">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. <span data-ttu-id="b622c-144">以下表达式键入**Then 操作**框。</span><span class="sxs-lookup"><span data-stu-id="b622c-144">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. <span data-ttu-id="b622c-145">单击**添加规则**。</span><span class="sxs-lookup"><span data-stu-id="b622c-145">Click **Add Rule**.</span></span>  
  
11. <span data-ttu-id="b622c-146">以下表达式键入**条件**框。</span><span class="sxs-lookup"><span data-stu-id="b622c-146">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. <span data-ttu-id="b622c-147">以下表达式键入**Then 操作**框。</span><span class="sxs-lookup"><span data-stu-id="b622c-147">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. <span data-ttu-id="b622c-148">以下表达式键入**Else 操作**框。</span><span class="sxs-lookup"><span data-stu-id="b622c-148">Type the following expression into the **Else Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. <span data-ttu-id="b622c-149">单击**确定**关闭**规则集编辑器**对话框。</span><span class="sxs-lookup"><span data-stu-id="b622c-149">Click **OK** to close the **Rule Set Editor** dialog box.</span></span>  
  
15. <span data-ttu-id="b622c-150">确保新创建<xref:System.Workflow.Activities.Rules.RuleSet>中选择**名称**列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-150">Ensure that the newly-created <xref:System.Workflow.Activities.Rules.RuleSet> is selected in the **Name** list, and click **OK**.</span></span>  
  
16. <span data-ttu-id="b622c-151">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="b622c-151">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
 <span data-ttu-id="b622c-152">在此过程中添加到 `DiscountCalculator` 活动中的规则如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="b622c-152">The rules added to the `DiscountCalculator` activity in this procedure are shown in the following code example.</span></span>  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 <span data-ttu-id="b622c-153">当 <xref:System.Workflow.Activities.PolicyActivity> 执行时，这三个规则会计算和修改 `Subtotal` 活动的 `DiscountPercent`、`Total` 和 `DiscountCalculator` 属性值来计算所需折扣。</span><span class="sxs-lookup"><span data-stu-id="b622c-153">When the <xref:System.Workflow.Activities.PolicyActivity> executes, these three rules evaluate and modify the `Subtotal`, `DiscountPercent`, and `Total` property values of the `DiscountCalculator` activity to calculate the desired discount.</span></span>  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a><span data-ttu-id="b622c-154">将 DiscountCalculator 活动与 Interop 活动一起使用</span><span class="sxs-lookup"><span data-stu-id="b622c-154">Using the DiscountCalculator Activity with the Interop Activity</span></span>  
 <span data-ttu-id="b622c-155">为了在 `DiscountCalculator` 工作流内使用 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 活动，要使用 <xref:System.Activities.Statements.Interop> 活动。</span><span class="sxs-lookup"><span data-stu-id="b622c-155">To use the `DiscountCalculator` activity inside a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow, the <xref:System.Activities.Statements.Interop> activity is used.</span></span> <span data-ttu-id="b622c-156">在本节中创建了两个工作流，一个工作流是使用代码创建的而另一个工作流是使用工作流设计器创建的，它们演示如何将 <xref:System.Activities.Statements.Interop> 活动与 `DiscountCalculator` 活动一起使用。</span><span class="sxs-lookup"><span data-stu-id="b622c-156">In this section two workflows are created, one using code and one using the workflow designer, which show how to use the <xref:System.Activities.Statements.Interop> activity with the `DiscountCalculator` activity.</span></span> <span data-ttu-id="b622c-157">这两个工作流使用同一宿主应用程序。</span><span class="sxs-lookup"><span data-stu-id="b622c-157">The same host application is used for both workflows.</span></span>  
  
#### <a name="to-create-the-host-application"></a><span data-ttu-id="b622c-158">创建主机应用程序</span><span class="sxs-lookup"><span data-stu-id="b622c-158">To create the host application</span></span>  
  
1.  <span data-ttu-id="b622c-159">右键单击**PolicyInteropDemo**中**解决方案资源管理器**和选择**添加**，，然后**新项目...**.</span><span class="sxs-lookup"><span data-stu-id="b622c-159">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add**, and then **New Project…**.</span></span>  
  
2.  <span data-ttu-id="b622c-160">确保**.NET Framework 4.5**已选中在.NET Framework 版本下拉列表中，然后选中**工作流控制台应用程序**从**Visual C# 项**列表。</span><span class="sxs-lookup"><span data-stu-id="b622c-160">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list, and select  **Workflow Console Application** from the **Visual C# Items** list.</span></span>  
  
3.  <span data-ttu-id="b622c-161">类型`PolicyInteropHost`到**名称**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-161">Type `PolicyInteropHost` into the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="b622c-162">右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="b622c-162">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="b622c-163">在**目标框架**下拉列表中，更改从选择**.NET Framework 4 Client Profile**到**.NET Framework 4.5**。</span><span class="sxs-lookup"><span data-stu-id="b622c-163">In the **Target framework** drop-down list, change the selection from **.NET Framework 4 Client Profile** to **.NET Framework 4.5**.</span></span> <span data-ttu-id="b622c-164">单击**是**以确认。</span><span class="sxs-lookup"><span data-stu-id="b622c-164">Click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="b622c-165">右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**添加引用...**.</span><span class="sxs-lookup"><span data-stu-id="b622c-165">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
7.  <span data-ttu-id="b622c-166">选择**PolicyActivityLibrary**从**项目**选项卡，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-166">Select **PolicyActivityLibrary** from the **Projects** tab and click **OK**.</span></span>  
  
8.  <span data-ttu-id="b622c-167">右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**添加引用...**.</span><span class="sxs-lookup"><span data-stu-id="b622c-167">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
9. <span data-ttu-id="b622c-168">选择**System.Workflow.Activities**， **System.Workflow.ComponentModel**，，然后**System.Workflow.Runtime**从**.NET**选项卡，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-168">Select **System.Workflow.Activities**, **System.Workflow.ComponentModel**, and then **System.Workflow.Runtime** from the **.NET** tab and click **OK**.</span></span>  
  
10. <span data-ttu-id="b622c-169">右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="b622c-169">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>  
  
11. <span data-ttu-id="b622c-170">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="b622c-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="using-the-interop-activity-in-code"></a><span data-ttu-id="b622c-171">在代码中使用 Interop 活动</span><span class="sxs-lookup"><span data-stu-id="b622c-171">Using the Interop Activity in Code</span></span>  
 <span data-ttu-id="b622c-172">在本示例中，工作流定义是使用包含 <xref:System.Activities.Statements.Interop> 活动和 `DiscountCalculator` 活动的代码创建的。</span><span class="sxs-lookup"><span data-stu-id="b622c-172">In this example, a workflow definition is created using code that contains the <xref:System.Activities.Statements.Interop> activity and the `DiscountCalculator` activity.</span></span> <span data-ttu-id="b622c-173">此工作流使用 <xref:System.Activities.WorkflowInvoker> 进行调用，并且使用 <xref:System.Activities.Statements.WriteLine> 活动将规则计算的结果写入控制台。</span><span class="sxs-lookup"><span data-stu-id="b622c-173">This workflow is invoked using <xref:System.Activities.WorkflowInvoker> and the results of the rule evaluation are written to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
##### <a name="to-use-the-interop-activity-in-code"></a><span data-ttu-id="b622c-174">在代码中使用 Interop 活动</span><span class="sxs-lookup"><span data-stu-id="b622c-174">To use the Interop activity in code</span></span>  
  
1.  <span data-ttu-id="b622c-175">右键单击**Program.cs**中**解决方案资源管理器**和选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="b622c-175">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="b622c-176">将下面的 `using` 语句添加到文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="b622c-176">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  <span data-ttu-id="b622c-177">移除 `Main` 方法的内容并替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="b622c-177">Remove the contents of the `Main` method and replace with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  <span data-ttu-id="b622c-178">在 `Program` 类中创建一个名为 `CalculateDiscountUsingCodeWorkflow` 的新方法，此方法包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="b622c-178">Create a new method in the `Program` class called `CalculateDiscountUsingCodeWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b622c-179">`Subtotal` 活动的 `DiscountPercent`、`Total` 和 `DiscountCalculator` 属性作为 <xref:System.Activities.Statements.Interop> 活动的参数，并且绑定到 <xref:System.Activities.Statements.Interop> 活动的 <xref:System.Activities.Statements.Interop.ActivityProperties%2A> 集合中的局部工作流变量。</span><span class="sxs-lookup"><span data-stu-id="b622c-179">The `Subtotal`, `DiscountPercent`, and `Total` properties of the `DiscountCalculator` activity are surfaced as arguments of the <xref:System.Activities.Statements.Interop> activity, and bound to local workflow variables in the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityProperties%2A> collection.</span></span> <span data-ttu-id="b622c-180">由于 `Subtotal` 数据流入 <xref:System.Activities.ArgumentDirection.In> 活动中，因此 `Subtotal` 作为 <xref:System.Activities.Statements.Interop> 参数添加，由于 `DiscountPercent` 和 `Total` 的数据流出 <xref:System.Activities.ArgumentDirection.Out> 活动，因此它们作为 <xref:System.Activities.Statements.Interop> 参数添加。</span><span class="sxs-lookup"><span data-stu-id="b622c-180">`Subtotal` is added as an <xref:System.Activities.ArgumentDirection.In> argument because the `Subtotal` data flows into the <xref:System.Activities.Statements.Interop> activity, and `DiscountPercent` and `Total` are added as <xref:System.Activities.ArgumentDirection.Out> arguments because their data flows out of the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="b622c-181">请注意，这两个 <xref:System.Activities.ArgumentDirection.Out> 参数以名称 `DiscountPercentOut` 和 `TotalOut` 添加，以指示它们表示 <xref:System.Activities.ArgumentDirection.Out> 参数。</span><span class="sxs-lookup"><span data-stu-id="b622c-181">Note that the two <xref:System.Activities.ArgumentDirection.Out> arguments are added with the names `DiscountPercentOut` and `TotalOut` to indicate that they represent <xref:System.Activities.ArgumentDirection.Out> arguments.</span></span> <span data-ttu-id="b622c-182">`DiscountCalculator` 类型指定为 <xref:System.Activities.Statements.Interop> 活动的 <xref:System.Activities.Statements.Interop.ActivityType%2A>。</span><span class="sxs-lookup"><span data-stu-id="b622c-182">The `DiscountCalculator` type is specified as the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span></span>  
  
5.  <span data-ttu-id="b622c-183">按 Ctrl+F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b622c-183">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="b622c-184">将 `Subtotal` 值替换为不同值以测试由 `DiscountCalculator` 活动提供的不同折扣级别。</span><span class="sxs-lookup"><span data-stu-id="b622c-184">Substitute different values for the `Subtotal` value to test out the different discount levels provided by the `DiscountCalculator` activity.</span></span>  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a><span data-ttu-id="b622c-185">在工作流设计器中使用 Interop 活动</span><span class="sxs-lookup"><span data-stu-id="b622c-185">Using the Interop Activity in the Workflow Designer</span></span>  
 <span data-ttu-id="b622c-186">在本示例中，工作流是使用工作流设计器创建的。</span><span class="sxs-lookup"><span data-stu-id="b622c-186">In this example, a workflow is created using the workflow designer.</span></span> <span data-ttu-id="b622c-187">此工作流与上一个示例的功能相同，但有一点除外，即当工作流完成时不是使用 <xref:System.Activities.Statements.WriteLine> 活动来显示折扣，而是由宿主应用程序检索并显示折扣信息。</span><span class="sxs-lookup"><span data-stu-id="b622c-187">This workflow has the same functionality as the previous example, except than instead of using a <xref:System.Activities.Statements.WriteLine> activity to display the discount, the host application retrieves and displays the discount information when the workflow completes.</span></span> <span data-ttu-id="b622c-188">此外，调用该工作流时，参数在工作流设计器中创建并且从宿主传入值，而不是使用局部工作流变量来包含数据。</span><span class="sxs-lookup"><span data-stu-id="b622c-188">Also, instead of using local workflow variables to contain the data, arguments are created in the workflow designer and the values are passed in from the host when the workflow is invoked.</span></span>  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a><span data-ttu-id="b622c-189">使用工作流设计器创建的工作流承载 PolicyActivity</span><span class="sxs-lookup"><span data-stu-id="b622c-189">To host the PolicyActivity using a Workflow Designer-created workflow</span></span>  
  
1.  <span data-ttu-id="b622c-190">右键单击**Workflow1.xaml**中**解决方案资源管理器**和选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="b622c-190">Right-click **Workflow1.xaml** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="b622c-191">单击 **“确定”** 以确认。</span><span class="sxs-lookup"><span data-stu-id="b622c-191">Click **OK** to confirm.</span></span>  
  
2.  <span data-ttu-id="b622c-192">右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**添加**，**新建项...**.</span><span class="sxs-lookup"><span data-stu-id="b622c-192">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add**, **New Item…**.</span></span>  
  
3.  <span data-ttu-id="b622c-193">展开**Visual C# 项**节点，然后选择**工作流**。</span><span class="sxs-lookup"><span data-stu-id="b622c-193">Expand the **Visual C# Items** node and select **Workflow**.</span></span> <span data-ttu-id="b622c-194">选择**活动**从**Visual C# 项**列表。</span><span class="sxs-lookup"><span data-stu-id="b622c-194">Select **Activity** from the **Visual C# Items** list.</span></span>  
  
4.  <span data-ttu-id="b622c-195">类型`DiscountWorkflow`到**名称**框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b622c-195">Type `DiscountWorkflow` into the **Name** box and click **Add**.</span></span>  
  
5.  <span data-ttu-id="b622c-196">单击**参数**上要显示的工作流设计器左下方按钮**参数**窗格。</span><span class="sxs-lookup"><span data-stu-id="b622c-196">Click the **Arguments** button on the lower left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
6.  <span data-ttu-id="b622c-197">单击**创建自变量**。</span><span class="sxs-lookup"><span data-stu-id="b622c-197">Click **Create Argument**.</span></span>  
  
7.  <span data-ttu-id="b622c-198">类型`Subtotal`到**名称**框中，选择**中**从**方向**下拉列表中，选择**Double**从**自变量类型**下拉列表中，然后按 enter 键保存该自变量。</span><span class="sxs-lookup"><span data-stu-id="b622c-198">Type `Subtotal` into the **Name** box, select **In** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b622c-199">如果**Double**不在**自变量类型**下拉列表中，选择**浏览类型...**，类型`System.Double`中**类型名称**框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-199">If **Double** is not in the **Argument type** drop-down list, select **Browse for Types …**, type `System.Double` in the **Type Name** box, and click **OK**.</span></span>  
  
8.  <span data-ttu-id="b622c-200">单击**创建自变量**。</span><span class="sxs-lookup"><span data-stu-id="b622c-200">Click **Create Argument**.</span></span>  
  
9. <span data-ttu-id="b622c-201">类型`DiscountPercent`到**名称**框中，选择**出**从**方向**下拉列表中，选择**Double**从**自变量类型**下拉列表中，然后按 enter 键保存该自变量。</span><span class="sxs-lookup"><span data-stu-id="b622c-201">Type `DiscountPercent` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
10. <span data-ttu-id="b622c-202">单击**创建自变量**。</span><span class="sxs-lookup"><span data-stu-id="b622c-202">Click **Create Argument**.</span></span>  
  
11. <span data-ttu-id="b622c-203">类型`Total`到**名称**框中，选择**出**从**方向**下拉列表中，选择**Double**从**自变量类型**下拉列表中，然后按 enter 键保存该自变量。</span><span class="sxs-lookup"><span data-stu-id="b622c-203">Type `Total` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
12. <span data-ttu-id="b622c-204">单击**参数**上要关闭的工作流设计器左下方按钮**参数**窗格。</span><span class="sxs-lookup"><span data-stu-id="b622c-204">Click the **Arguments** button on the lower left side of the workflow designer to close the **Arguments** pane.</span></span>  
  
13. <span data-ttu-id="b622c-205">拖动**序列**活动从**控制流**部分**工具箱**并将其放到工作流设计器图面上。</span><span class="sxs-lookup"><span data-stu-id="b622c-205">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the workflow designer surface.</span></span>  
  
14. <span data-ttu-id="b622c-206">拖动**互操作**活动从**迁移**部分**工具箱**拖放**序列**活动。</span><span class="sxs-lookup"><span data-stu-id="b622c-206">Drag an **Interop** activity from the **Migration** section of the **Toolbox** and drop it in the **Sequence** activity.</span></span>  
  
15. <span data-ttu-id="b622c-207">单击**互操作**上的活动**单击此项可浏览...**</span><span class="sxs-lookup"><span data-stu-id="b622c-207">Click the **Interop** activity on the **Click to browse…**</span></span> <span data-ttu-id="b622c-208">标记中，键入**DiscountCalculator**中**类型名称**框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b622c-208">label, type **DiscountCalculator** in the **Type Name** box, and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b622c-209">当 <xref:System.Activities.Statements.Interop> 活动添加到工作流并且 `DiscountCalculator` 类型指定为该活动的 <xref:System.Activities.Statements.Interop.ActivityType%2A> 时，<xref:System.Activities.Statements.Interop> 活动会公开三个 <xref:System.Activities.ArgumentDirection.In> 参数和三个 <xref:System.Activities.ArgumentDirection.Out> 参数，它们表示 `DiscountCalculator` 活动的三个公共属性。</span><span class="sxs-lookup"><span data-stu-id="b622c-209">When the <xref:System.Activities.Statements.Interop> activity is added to the workflow and the `DiscountCalculator` type is specified as its <xref:System.Activities.Statements.Interop.ActivityType%2A>, the <xref:System.Activities.Statements.Interop> activity exposes three <xref:System.Activities.ArgumentDirection.In> arguments and three <xref:System.Activities.ArgumentDirection.Out> arguments that represent the three public properties of the `DiscountCalculator` activity.</span></span> <span data-ttu-id="b622c-210"><xref:System.Activities.ArgumentDirection.In>自变量具有相同的名称为三个公共属性，而三个<xref:System.Activities.ArgumentDirection.Out>自变量具有相同名称的与**出**追加到属性名称。</span><span class="sxs-lookup"><span data-stu-id="b622c-210">The <xref:System.Activities.ArgumentDirection.In> arguments have the same name as the three public properties, and the three <xref:System.Activities.ArgumentDirection.Out> arguments have the same names with **Out** appended to the property name.</span></span> <span data-ttu-id="b622c-211">在以下步骤中，之前步骤中创建的工作流参数将绑定到 <xref:System.Activities.Statements.Interop> 活动的参数。</span><span class="sxs-lookup"><span data-stu-id="b622c-211">In the following steps, the workflow arguments created in the previous steps are bound to the <xref:System.Activities.Statements.Interop> activity’s arguments.</span></span>  
  
16. <span data-ttu-id="b622c-212">类型`DiscountPercent`到**输入 VB 表达式**右侧的框中**DiscountPercentOut**属性然后按 tab 键。</span><span class="sxs-lookup"><span data-stu-id="b622c-212">Type `DiscountPercent` into the **Enter a VB expression** box to the right of the **DiscountPercentOut** property and press TAB.</span></span>  
  
17. <span data-ttu-id="b622c-213">类型`Subtotal`到**输入 VB 表达式**右侧的框中**Subtotal**属性然后按 tab 键。</span><span class="sxs-lookup"><span data-stu-id="b622c-213">Type `Subtotal` into the **Enter a VB expression** box to the right of the **Subtotal** property and press TAB.</span></span>  
  
18. <span data-ttu-id="b622c-214">类型`Total`到**输入 VB 表达式**右侧的框中**TotalOut**属性然后按 tab 键。</span><span class="sxs-lookup"><span data-stu-id="b622c-214">Type `Total` into the **Enter a VB expression** box to the right of the **TotalOut** property and press TAB.</span></span>  
  
19. <span data-ttu-id="b622c-215">右键单击**Program.cs**中**解决方案资源管理器**和选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="b622c-215">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
20. <span data-ttu-id="b622c-216">将下面的 `using` 语句添加到文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="b622c-216">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. <span data-ttu-id="b622c-217">注释掉 `CalculateDiscountInCode` 方法中对 `Main` 方法的调用，然后添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="b622c-217">Comment out the call to the `CalculateDiscountInCode` method in the `Main` method and add the following code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b622c-218">如果您没有按照前面的过程操作且存在默认 `Main` 代码，请将 `Main` 的内容替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="b622c-218">If you did not follow the previous procedure and the default `Main` code is present, replace the contents of `Main` with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. <span data-ttu-id="b622c-219">在 `Program` 类中创建一个名为 `CalculateDiscountUsingDesignerWorkflow` 的新方法，此方法包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="b622c-219">Create a new method in the `Program` class called `CalculateDiscountUsingDesignerWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. <span data-ttu-id="b622c-220">按 Ctrl+F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b622c-220">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="b622c-221">若要指定其他 `Subtotal` 量，请在以下代码中更改 `SubtotalValue` 的值。</span><span class="sxs-lookup"><span data-stu-id="b622c-221">To specify a different `Subtotal` amount, change the value of `SubtotalValue` in the following code.</span></span>  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a><span data-ttu-id="b622c-222">规则功能概述</span><span class="sxs-lookup"><span data-stu-id="b622c-222">Rules Features Overview</span></span>  
 <span data-ttu-id="b622c-223">[!INCLUDE[wf1](../../../includes/wf1-md.md)] 规则引擎为以基于优先级别的方式处理规则提供支持，并且支持正向链接。</span><span class="sxs-lookup"><span data-stu-id="b622c-223">The [!INCLUDE[wf1](../../../includes/wf1-md.md)] rules engine provides support for processing rules in a priority-based manner with support for forward chaining.</span></span> <span data-ttu-id="b622c-224">可为单个项或集合中的多个项计算规则。</span><span class="sxs-lookup"><span data-stu-id="b622c-224">Rules can be evaluated for a single item or for items in a collection.</span></span> <span data-ttu-id="b622c-225">有关规则的概述以及特定规则功能的信息，请参考下表。</span><span class="sxs-lookup"><span data-stu-id="b622c-225">For an overview of rules and information on specific rules functionality, please refer to the following table.</span></span>  
  
|<span data-ttu-id="b622c-226">规则功能</span><span class="sxs-lookup"><span data-stu-id="b622c-226">Rules Feature</span></span>|<span data-ttu-id="b622c-227">文档</span><span class="sxs-lookup"><span data-stu-id="b622c-227">Documentation</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="b622c-228">规则概述</span><span class="sxs-lookup"><span data-stu-id="b622c-228">Rules Overview</span></span>|[<span data-ttu-id="b622c-229">Windows Workflow Foundation 规则引擎简介</span><span class="sxs-lookup"><span data-stu-id="b622c-229">Introduction to the Windows Workflow Foundation Rules Engine</span></span>](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|<span data-ttu-id="b622c-230">RuleSet</span><span class="sxs-lookup"><span data-stu-id="b622c-230">RuleSet</span></span>|<span data-ttu-id="b622c-231">[工作流中使用 Ruleset](http://go.microsoft.com/fwlink/?LinkId=178516)和<xref:System.Workflow.Activities.Rules.RuleSet></span><span class="sxs-lookup"><span data-stu-id="b622c-231">[Using RuleSets in Workflows](http://go.microsoft.com/fwlink/?LinkId=178516) and <xref:System.Workflow.Activities.Rules.RuleSet></span></span>|  
|<span data-ttu-id="b622c-232">规则计算</span><span class="sxs-lookup"><span data-stu-id="b622c-232">Evaluation of Rules</span></span>|[<span data-ttu-id="b622c-233">Ruleset 中的规则评估</span><span class="sxs-lookup"><span data-stu-id="b622c-233">Rules Evaluation in RuleSets</span></span>](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|<span data-ttu-id="b622c-234">规则链接</span><span class="sxs-lookup"><span data-stu-id="b622c-234">Rules Chaining</span></span>|<span data-ttu-id="b622c-235">[正向链接控制](http://go.microsoft.com/fwlink/?LinkId=178518)和[正向链接的规则](http://go.microsoft.com/fwlink/?LinkId=178519)</span><span class="sxs-lookup"><span data-stu-id="b622c-235">[Forward Chaining Control](http://go.microsoft.com/fwlink/?LinkId=178518) and [Forward Chaining of Rules](http://go.microsoft.com/fwlink/?LinkId=178519)</span></span>|  
|<span data-ttu-id="b622c-236">处理规则中的集合</span><span class="sxs-lookup"><span data-stu-id="b622c-236">Processing Collections in Rules</span></span>|[<span data-ttu-id="b622c-237">处理规则中的集合</span><span class="sxs-lookup"><span data-stu-id="b622c-237">Processing Collections in Rules</span></span>](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|<span data-ttu-id="b622c-238">使用 PolicyActivity</span><span class="sxs-lookup"><span data-stu-id="b622c-238">Using the PolicyActivity</span></span>|<span data-ttu-id="b622c-239">[使用 PolicyActivity 活动](http://go.microsoft.com/fwlink/?LinkId=178521)和<xref:System.Workflow.Activities.PolicyActivity></span><span class="sxs-lookup"><span data-stu-id="b622c-239">[Using the PolicyActivity Activity](http://go.microsoft.com/fwlink/?LinkId=178521) and <xref:System.Workflow.Activities.PolicyActivity></span></span>|  
  
 <span data-ttu-id="b622c-240">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 中创建的工作流不使用 [!INCLUDE[wf1](../../../includes/wf1-md.md)] 提供的所有规则功能，例如声明性活动条件以及诸如 <xref:System.Workflow.Activities.ConditionedActivityGroup> 和 <xref:System.Workflow.Activities.ReplicatorActivity> 等条件活动。</span><span class="sxs-lookup"><span data-stu-id="b622c-240">Workflows created in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] do not use all of the rules features provided by [!INCLUDE[wf1](../../../includes/wf1-md.md)], such as declarative activity conditions and conditional activities such as the <xref:System.Workflow.Activities.ConditionedActivityGroup> and <xref:System.Workflow.Activities.ReplicatorActivity>.</span></span> <span data-ttu-id="b622c-241">如果需要，此功能可用于使用 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 和 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 创建的工作流。</span><span class="sxs-lookup"><span data-stu-id="b622c-241">If required, this functionality is available for workflows created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="b622c-242">[迁移指南](../../../docs/framework/windows-workflow-foundation/migration-guidance.md)。</span><span class="sxs-lookup"><span data-stu-id="b622c-242"> [Migration Guidance](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>
