---
title: 在 .NET Framework 4 工作流中使用 Interop 活动
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ebef74097d22c9624a29470f4cda231bbb32fe90
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a>在 .NET Framework 4 工作流中使用 Interop 活动
通过使用 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 活动，可在 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 工作流中使用通过 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 或 <xref:System.Activities.Statements.Interop> 创建的活动。 本主题概述如何使用 <xref:System.Activities.Statements.Interop> 活动。  
  
> [!NOTE]
>  <xref:System.Activities.Statements.Interop>活动在工作流的项目具有除非未出现在工作流设计器工具箱其**目标框架**设置设为 **.Net Framework 4**或更高版本。  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a>在 .NET Framework 4.5 工作流中使用 Interop 活动  
 在本主题中，将要创建一个包含 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 活动的 `DiscountCalculator` 活动库。 `DiscountCalculator` 基于购买量计算折扣，它由包含一个 <xref:System.Workflow.Activities.SequenceActivity> 的 <xref:System.Workflow.Activities.PolicyActivity> 组成。  
  
> [!NOTE]
>  本主题中创建的 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 活动使用 <xref:System.Workflow.Activities.PolicyActivity> 来实现该活动的逻辑。 不必使用自定义 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 活动或 <xref:System.Activities.Statements.Interop> 活动也能在 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 工作流中使用规则。 有关使用中的规则的示例[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]流，并且不使用<xref:System.Activities.Statements.Interop>活动，请参阅[.NET Framework 4.5 中的策略活动](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md)示例。  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a>创建 .NET Framework 3.5 活动库项目  
  
1.  打开[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]和选择**新建**然后**项目...** 从**文件**菜单。  
  
2.  展开**其他项目类型**中的节点**已安装的模板**窗格中，然后选择**Visual Studio 解决方案**。  
  
3.  选择**空白解决方案**从**Visual Studio 解决方案**列表。 类型`PolicyInteropDemo`中**名称**框中，单击**确定**。  
  
4.  右键单击**PolicyInteropDemo**中**解决方案资源管理器**和选择**添加**然后**新项目...**.  
  
    > [!TIP]
    >  如果**解决方案资源管理器**窗口不可见，则选择**解决方案资源管理器**从**视图**菜单。  
  
5.  在**已安装的模板**列表中，选择**Visual C#** 然后**工作流**。 选择 **.NET Framework 3.5**从.NET Framework 版本下拉列表，，然后选择**工作流活动库**从**模板**列表。  
  
6.  类型`PolicyActivityLibrary`中**名称**框中，单击**确定**。  
  
7.  右键单击**Activity1.cs**中**解决方案资源管理器**和选择**删除**。 单击 **“确定”** 以确认。  
  
#### <a name="to-create-the-discountcalculator-activity"></a>创建 DiscountCalculator 活动  
  
1.  右键单击**PolicyActivityLibrary**中**解决方案资源管理器**和选择**添加**然后**活动...**.  
  
2.  选择**Activity （具有单独的代码）**从**Visual C# 项**列表。 类型`DiscountCalculator`中**名称**框中，单击**确定**。  
  
3.  右键单击**DiscountCalculator.xoml**中**解决方案资源管理器**和选择**查看代码**。  
  
4.  将以下三个属性添加到 `DiscountCalculator` 类中。  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  右键单击**DiscountCalculator.xoml**中**解决方案资源管理器**和选择**视图设计器**。  
  
6.  拖动**策略**活动从**Windows Workflow v3.0**部分**工具箱**拖放**DiscountCalculator**活动.  
  
    > [!TIP]
    >  如果**工具箱**窗口不可见，则选择**工具箱**从**视图**菜单。  
  
#### <a name="to-configure-the-rules"></a>配置规则  
  
1.  单击新添加**策略**活动以选择它，如果尚未选择。  
  
2.  单击**rulesetreference**中的属性**属性**窗口选择它，然后单击属性右侧的省略号按钮。  
  
    > [!TIP]
    >  如果**属性**窗口不可见，请选择**属性窗口**从**视图**菜单。  
  
3.  选择**新单击...**.  
  
4.  单击**添加规则**。  
  
5.  以下表达式键入**条件**框。  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  以下表达式键入**Then 操作**框。  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  单击**添加规则**。  
  
8.  以下表达式键入**条件**框。  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. 以下表达式键入**Then 操作**框。  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. 单击**添加规则**。  
  
11. 以下表达式键入**条件**框。  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. 以下表达式键入**Then 操作**框。  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. 以下表达式键入**Else 操作**框。  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. 单击**确定**关闭**规则集编辑器**对话框。  
  
15. 确保新创建<xref:System.Workflow.Activities.Rules.RuleSet>中选择**名称**列表，然后单击**确定**。  
  
16. 按 Ctrl+Shift+B 生成解决方案。  
  
 在此过程中添加到 `DiscountCalculator` 活动中的规则如下面的代码示例所示。  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 当 <xref:System.Workflow.Activities.PolicyActivity> 执行时，这三个规则会计算和修改 `Subtotal` 活动的 `DiscountPercent`、`Total` 和 `DiscountCalculator` 属性值来计算所需折扣。  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a>将 DiscountCalculator 活动与 Interop 活动一起使用  
 为了在 `DiscountCalculator` 工作流内使用 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 活动，要使用 <xref:System.Activities.Statements.Interop> 活动。 在本节中创建了两个工作流，一个工作流是使用代码创建的而另一个工作流是使用工作流设计器创建的，它们演示如何将 <xref:System.Activities.Statements.Interop> 活动与 `DiscountCalculator` 活动一起使用。 这两个工作流使用同一宿主应用程序。  
  
#### <a name="to-create-the-host-application"></a>创建主机应用程序  
  
1.  右键单击**PolicyInteropDemo**中**解决方案资源管理器**和选择**添加**，，然后**新项目...**.  
  
2.  确保 **.NET Framework 4.5**已选中在.NET Framework 版本下拉列表中，然后选中**工作流控制台应用程序**从**Visual C# 项**列表。  
  
3.  类型`PolicyInteropHost`到**名称**框中，单击**确定**。  
  
4.  右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**属性**。  
  
5.  在**目标框架**下拉列表中，更改从选择 **.NET Framework 4 Client Profile**到 **.NET Framework 4.5**。 单击**是**以确认。  
  
6.  右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**添加引用...**.  
  
7.  选择**PolicyActivityLibrary**从**项目**选项卡，单击**确定**。  
  
8.  右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**添加引用...**.  
  
9. 选择**System.Workflow.Activities**， **System.Workflow.ComponentModel**，，然后**System.Workflow.Runtime**从 **.NET**选项卡，单击**确定**。  
  
10. 右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**设为启动项目**。  
  
11. 按 Ctrl+Shift+B 生成解决方案。  
  
### <a name="using-the-interop-activity-in-code"></a>在代码中使用 Interop 活动  
 在本示例中，工作流定义是使用包含 <xref:System.Activities.Statements.Interop> 活动和 `DiscountCalculator` 活动的代码创建的。 此工作流使用 <xref:System.Activities.WorkflowInvoker> 进行调用，并且使用 <xref:System.Activities.Statements.WriteLine> 活动将规则计算的结果写入控制台。  
  
##### <a name="to-use-the-interop-activity-in-code"></a>在代码中使用 Interop 活动  
  
1.  右键单击**Program.cs**中**解决方案资源管理器**和选择**查看代码**。  
  
2.  将下面的 `using` 语句添加到文件的顶部。  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  移除 `Main` 方法的内容并替换为以下代码。  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  在 `Program` 类中创建一个名为 `CalculateDiscountUsingCodeWorkflow` 的新方法，此方法包含以下代码。  
  
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
    >  `Subtotal` 活动的 `DiscountPercent`、`Total` 和 `DiscountCalculator` 属性作为 <xref:System.Activities.Statements.Interop> 活动的参数，并且绑定到 <xref:System.Activities.Statements.Interop> 活动的 <xref:System.Activities.Statements.Interop.ActivityProperties%2A> 集合中的局部工作流变量。 由于 `Subtotal` 数据流入 <xref:System.Activities.ArgumentDirection.In> 活动中，因此 `Subtotal` 作为 <xref:System.Activities.Statements.Interop> 参数添加，由于 `DiscountPercent` 和 `Total` 的数据流出 <xref:System.Activities.ArgumentDirection.Out> 活动，因此它们作为 <xref:System.Activities.Statements.Interop> 参数添加。 请注意，这两个 <xref:System.Activities.ArgumentDirection.Out> 参数以名称 `DiscountPercentOut` 和 `TotalOut` 添加，以指示它们表示 <xref:System.Activities.ArgumentDirection.Out> 参数。 `DiscountCalculator` 类型指定为 <xref:System.Activities.Statements.Interop> 活动的 <xref:System.Activities.Statements.Interop.ActivityType%2A>。  
  
5.  按 Ctrl+F5 生成并运行应用程序。 将 `Subtotal` 值替换为不同值以测试由 `DiscountCalculator` 活动提供的不同折扣级别。  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a>在工作流设计器中使用 Interop 活动  
 在本示例中，工作流是使用工作流设计器创建的。 此工作流与上一个示例的功能相同，但有一点除外，即当工作流完成时不是使用 <xref:System.Activities.Statements.WriteLine> 活动来显示折扣，而是由宿主应用程序检索并显示折扣信息。 此外，调用该工作流时，参数在工作流设计器中创建并且从宿主传入值，而不是使用局部工作流变量来包含数据。  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a>使用工作流设计器创建的工作流承载 PolicyActivity  
  
1.  右键单击**Workflow1.xaml**中**解决方案资源管理器**和选择**删除**。 单击 **“确定”** 以确认。  
  
2.  右键单击**PolicyInteropHost**中**解决方案资源管理器**和选择**添加**，**新建项...**.  
  
3.  展开**Visual C# 项**节点，然后选择**工作流**。 选择**活动**从**Visual C# 项**列表。  
  
4.  类型`DiscountWorkflow`到**名称**框中，单击**添加**。  
  
5.  单击**参数**上要显示的工作流设计器左下方按钮**参数**窗格。  
  
6.  单击**创建自变量**。  
  
7.  类型`Subtotal`到**名称**框中，选择**中**从**方向**下拉列表中，选择**Double**从**自变量类型**下拉列表中，然后按 enter 键保存该自变量。  
  
    > [!NOTE]
    >  如果**Double**不在**自变量类型**下拉列表中，选择**浏览类型...**，类型`System.Double`中**类型名称**框中，然后单击**确定**。  
  
8.  单击**创建自变量**。  
  
9. 类型`DiscountPercent`到**名称**框中，选择**出**从**方向**下拉列表中，选择**Double**从**自变量类型**下拉列表中，然后按 enter 键保存该自变量。  
  
10. 单击**创建自变量**。  
  
11. 类型`Total`到**名称**框中，选择**出**从**方向**下拉列表中，选择**Double**从**自变量类型**下拉列表中，然后按 enter 键保存该自变量。  
  
12. 单击**参数**上要关闭的工作流设计器左下方按钮**参数**窗格。  
  
13. 拖动**序列**活动从**控制流**部分**工具箱**并将其放到工作流设计器图面上。  
  
14. 拖动**互操作**活动从**迁移**部分**工具箱**拖放**序列**活动。  
  
15. 单击**互操作**上的活动**单击此项可浏览...** 标记中，键入**DiscountCalculator**中**类型名称**框中，然后单击**确定**。  
  
    > [!NOTE]
    >  当 <xref:System.Activities.Statements.Interop> 活动添加到工作流并且 `DiscountCalculator` 类型指定为该活动的 <xref:System.Activities.Statements.Interop.ActivityType%2A> 时，<xref:System.Activities.Statements.Interop> 活动会公开三个 <xref:System.Activities.ArgumentDirection.In> 参数和三个 <xref:System.Activities.ArgumentDirection.Out> 参数，它们表示 `DiscountCalculator` 活动的三个公共属性。 <xref:System.Activities.ArgumentDirection.In>自变量具有相同的名称为三个公共属性，而三个<xref:System.Activities.ArgumentDirection.Out>自变量具有相同名称的与**出**追加到属性名称。 在以下步骤中，之前步骤中创建的工作流参数将绑定到 <xref:System.Activities.Statements.Interop> 活动的参数。  
  
16. 类型`DiscountPercent`到**输入 VB 表达式**右侧的框中**DiscountPercentOut**属性然后按 tab 键。  
  
17. 类型`Subtotal`到**输入 VB 表达式**右侧的框中**Subtotal**属性然后按 tab 键。  
  
18. 类型`Total`到**输入 VB 表达式**右侧的框中**TotalOut**属性然后按 tab 键。  
  
19. 右键单击**Program.cs**中**解决方案资源管理器**和选择**查看代码**。  
  
20. 将下面的 `using` 语句添加到文件的顶部。  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. 注释掉 `CalculateDiscountInCode` 方法中对 `Main` 方法的调用，然后添加以下代码。  
  
    > [!NOTE]
    >  如果您没有按照前面的过程操作且存在默认 `Main` 代码，请将 `Main` 的内容替换为以下代码。  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. 在 `Program` 类中创建一个名为 `CalculateDiscountUsingDesignerWorkflow` 的新方法，此方法包含以下代码。  
  
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
  
23. 按 Ctrl+F5 生成并运行应用程序。 若要指定其他 `Subtotal` 量，请在以下代码中更改 `SubtotalValue` 的值。  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a>规则功能概述  
 [!INCLUDE[wf1](../../../includes/wf1-md.md)] 规则引擎为以基于优先级别的方式处理规则提供支持，并且支持正向链接。 可为单个项或集合中的多个项计算规则。 有关规则的概述以及特定规则功能的信息，请参考下表。  
  
|规则功能|文档|  
|-------------------|-------------------|  
|规则概述|[Windows Workflow Foundation 规则引擎简介](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|RuleSet|[工作流中使用 Ruleset](http://go.microsoft.com/fwlink/?LinkId=178516)和 <xref:System.Workflow.Activities.Rules.RuleSet>|  
|规则计算|[Ruleset 中的规则评估](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|规则链接|[正向链接控制](http://go.microsoft.com/fwlink/?LinkId=178518)和[正向链接的规则](http://go.microsoft.com/fwlink/?LinkId=178519)|  
|处理规则中的集合|[处理规则中的集合](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|使用 PolicyActivity|[使用 PolicyActivity 活动](http://go.microsoft.com/fwlink/?LinkId=178521)和 <xref:System.Workflow.Activities.PolicyActivity>|  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 中创建的工作流不使用 [!INCLUDE[wf1](../../../includes/wf1-md.md)] 提供的所有规则功能，例如声明性活动条件以及诸如 <xref:System.Workflow.Activities.ConditionedActivityGroup> 和 <xref:System.Workflow.Activities.ReplicatorActivity> 等条件活动。 如果需要，此功能可用于使用 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 和 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 创建的工作流。 有关详细信息，请参阅[迁移指南](../../../docs/framework/windows-workflow-foundation/migration-guidance.md)。
