---
title: 任务 2：承载工作流设计器
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 8e4c17ed182cec7748b9a1f11f76ff90aa60c39e
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715781"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="d1700-102">任务 2：承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="d1700-102">Task 2: Host the Workflow Designer</span></span>

<span data-ttu-id="d1700-103">本主题介绍在 Windows Presentation Foundation （WPF）应用程序中承载 Windows 工作流设计器的实例的过程。</span><span class="sxs-lookup"><span data-stu-id="d1700-103">This topic describes the procedure for hosting an instance of the Windows Workflow Designer in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="d1700-104">此过程配置包含设计器的**网格**控件，以编程方式创建 <xref:System.Activities.Presentation.WorkflowDesigner> 的实例，该实例包含默认的 <xref:System.Activities.Statements.Sequence> 活动，注册设计器元数据以为所有内置活动提供设计器支持，并在 WPF 应用程序中承载工作流设计器。</span><span class="sxs-lookup"><span data-stu-id="d1700-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the Workflow Designer in the WPF application.</span></span>

## <a name="to-host-the-workflow-designer"></a><span data-ttu-id="d1700-105">承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="d1700-105">To host the workflow designer</span></span>

1. <span data-ttu-id="d1700-106">打开你在[任务1：创建新的 Windows Presentation Foundation 应用程序](task-1-create-a-new-wpf-app.md)中创建的 HostingApplication 项目。</span><span class="sxs-lookup"><span data-stu-id="d1700-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>

2. <span data-ttu-id="d1700-107">调整窗口的大小，使其更易于使用工作流设计器。</span><span class="sxs-lookup"><span data-stu-id="d1700-107">Adjust the size of the window to make it easier to use the Workflow Designer.</span></span> <span data-ttu-id="d1700-108">为此，请在设计器中选择 " **mainwindow.xaml** "，按 F4 以显示 "**属性**" 窗口，并在 "**布局**" 部分中，将 "**宽度**" 设置为600，将 "**高度**" 设置为值350。</span><span class="sxs-lookup"><span data-stu-id="d1700-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>

3. <span data-ttu-id="d1700-109">设置网格名称，方法是在设计器中选择 "**网格**" 面板（单击**mainwindow.xaml**中的框），然后将 "**属性**" 窗口顶部的 "**名称**" 属性设置为 "grid1"。</span><span class="sxs-lookup"><span data-stu-id="d1700-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>

4. <span data-ttu-id="d1700-110">在 "**属性**" 窗口中，单击 "`ColumnDefinitions`" 属性旁边的省略号（ **...** ）以打开 "**集合编辑器**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="d1700-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>

5. <span data-ttu-id="d1700-111">在 "**集合编辑器**" 对话框中，单击 "**添加**" 按钮三次，以便在布局中插入三列。</span><span class="sxs-lookup"><span data-stu-id="d1700-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="d1700-112">第一列将包含 "**工具箱**"，第二列将承载工作流设计器，第三列将用于属性检查器。</span><span class="sxs-lookup"><span data-stu-id="d1700-112">The first column will contain the **Toolbox**, the second column will host the Workflow Designer, and the third column will be used for the property inspector.</span></span>

6. <span data-ttu-id="d1700-113">将中间列的 `Width` 属性设置为值 "4 \*"。</span><span class="sxs-lookup"><span data-stu-id="d1700-113">Set the `Width` property of the middle column to the value "4\*".</span></span>

7. <span data-ttu-id="d1700-114">单击“确定” 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="d1700-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="d1700-115">以下 XAML 将添加到*mainwindow.xaml*文件中：</span><span class="sxs-lookup"><span data-stu-id="d1700-115">The following XAML is added to your *MainWindow.xaml* file:</span></span>

    ```xaml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. <span data-ttu-id="d1700-116">在**解决方案资源管理器**中，右键单击*mainwindow.xaml* ，然后选择 "**查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="d1700-116">In **Solution Explorer**, right-click *MainWindow.xaml* and select **View Code**.</span></span> <span data-ttu-id="d1700-117">按照以下这些步骤修改代码：</span><span class="sxs-lookup"><span data-stu-id="d1700-117">Modify the code by following these steps:</span></span>

    1. <span data-ttu-id="d1700-118">添加下列命名空间：</span><span class="sxs-lookup"><span data-stu-id="d1700-118">Add the following namespaces:</span></span>

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. <span data-ttu-id="d1700-119">若要声明一个私有成员字段以保存 <xref:System.Activities.Presentation.WorkflowDesigner>的实例，请将以下代码添加到 `MainWindow` 类：</span><span class="sxs-lookup"><span data-stu-id="d1700-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class:</span></span>

        ```csharp
        public partial class MainWindow : Window
        {
            private WorkflowDesigner wd;

            public MainWindow()
            {
                InitializeComponent();
            }
        }
        ```

    3. <span data-ttu-id="d1700-120">将下面的 `AddDesigner` 方法添加到 `MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="d1700-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="d1700-121">实现创建 <xref:System.Activities.Presentation.WorkflowDesigner>的实例，向其中添加 <xref:System.Activities.Statements.Sequence> 活动，并将其放在 grid1**网格**的中间列中。</span><span class="sxs-lookup"><span data-stu-id="d1700-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>

        ```csharp
        private void AddDesigner()
        {
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }
        ```

    4. <span data-ttu-id="d1700-122">注册设计器元数据，为所有内置活动添加设计器支持。</span><span class="sxs-lookup"><span data-stu-id="d1700-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="d1700-123">这使您可以将活动从 "工具箱" 拖放到工作流设计器中的原始 <xref:System.Activities.Statements.Sequence> 活动。</span><span class="sxs-lookup"><span data-stu-id="d1700-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the Workflow Designer.</span></span> <span data-ttu-id="d1700-124">为此，请将 `RegisterMetadata` 方法添加到 `MainWindow` 类：</span><span class="sxs-lookup"><span data-stu-id="d1700-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class:</span></span>

        ```csharp
        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        <span data-ttu-id="d1700-125">有关注册活动设计器的详细信息，请参阅[如何：创建自定义活动设计器](how-to-create-a-custom-activity-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="d1700-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>

    5. <span data-ttu-id="d1700-126">在 `MainWindow` 类构造函数中，添加对上文声明的方法的调用，以便注册设计器支持元数据，并创建 <xref:System.Activities.Presentation.WorkflowDesigner>。</span><span class="sxs-lookup"><span data-stu-id="d1700-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>

        ```csharp
        public MainWindow()
        {
            InitializeComponent();

            // Register the metadata.
            RegisterMetadata();

            // Add the WFF Designer.
            AddDesigner();
        }
        ```

        > [!NOTE]
        > <span data-ttu-id="d1700-127">`RegisterMetadata` 方法注册包含 <xref:System.Activities.Statements.Sequence> 活动的内置活动的设计器元数据。</span><span class="sxs-lookup"><span data-stu-id="d1700-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="d1700-128">由于 `AddDesigner` 方法使用 <xref:System.Activities.Statements.Sequence> 活动，因此必须先调用 `RegisterMetadata` 方法。</span><span class="sxs-lookup"><span data-stu-id="d1700-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>

9. <span data-ttu-id="d1700-129">按<kbd>F5</kbd>生成并运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="d1700-129">Press <kbd>F5</kbd> to build and run the solution.</span></span>

10. <span data-ttu-id="d1700-130">请参阅[任务3：创建 "工具箱" 和 "PropertyGrid" 窗格](task-3-create-the-toolbox-and-propertygrid-panes.md)，了解如何向重新承载工作流设计器添加 **"工具箱" 和 "** **PropertyGrid** " 支持。</span><span class="sxs-lookup"><span data-stu-id="d1700-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1700-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1700-131">See also</span></span>

- [<span data-ttu-id="d1700-132">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="d1700-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="d1700-133">任务 1：新建 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="d1700-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="d1700-134">任务 3：创建“工具箱”和“属性网格”窗格</span><span class="sxs-lookup"><span data-stu-id="d1700-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
