---
title: 任务 2：承载工作流设计器
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 15657ad79632812d3802e4da22b9ef297d08f932
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180252"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="0cf1d-102">任务 2：承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="0cf1d-102">Task 2: Host the Workflow Designer</span></span>

<span data-ttu-id="0cf1d-103">本主题介绍在 Windows Presentation Foundation （WPF）应用程序中承载 @no__t 的实例的过程。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="0cf1d-104">此过程配置包含设计器的**网格**控件，以编程方式创建包含默认 @no__t 2 活动的 @no__t 的实例，注册设计器元数据以提供对所有内置的设计器支持活动，并承载 WPF 应用程序中的 @no__t。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the WPF application.</span></span>

## <a name="to-host-the-workflow-designer"></a><span data-ttu-id="0cf1d-105">承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="0cf1d-105">To host the workflow designer</span></span>

1. <span data-ttu-id="0cf1d-106">打开在 [Task 1 中创建的 HostingApplication 项目：创建新的 Windows Presentation Foundation 应用程序 @ no__t-0。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>

2. <span data-ttu-id="0cf1d-107">调整窗口的大小，以便更轻松地使用 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="0cf1d-108">为此，请在设计器中选择 " **mainwindow.xaml** "，按 F4 以显示 "**属性**" 窗口，并在 "**布局**" 部分中，将 "**宽度**" 设置为600，将 "**高度**" 设置为值350。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>

3. <span data-ttu-id="0cf1d-109">设置网格名称，方法是在设计器中选择 "**网格**" 面板（单击**mainwindow.xaml**中的框），然后将 "**属性**" 窗口顶部的 "**名称**" 属性设置为 "grid1"。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>

4. <span data-ttu-id="0cf1d-110">在 "**属性**" 窗口中，单击 "@no__t" 属性旁边的省略号（ **...** ）以打开 "**集合编辑器**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>

5. <span data-ttu-id="0cf1d-111">在 "**集合编辑器**" 对话框中，单击 "**添加**" 按钮三次，以便在布局中插入三列。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="0cf1d-112">第一列将包含 "**工具箱**"，第二列将承载 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]，第三列将用于属性检查器。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>

6. <span data-ttu-id="0cf1d-113">将中间列的 @no__t 0 属性设置为值 "4 \*"。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-113">Set the `Width` property of the middle column to the value "4\*".</span></span>

7. <span data-ttu-id="0cf1d-114">单击“确定” 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="0cf1d-115">以下 XAML 将添加到*mainwindow.xaml*文件中：</span><span class="sxs-lookup"><span data-stu-id="0cf1d-115">The following XAML is added to your *MainWindow.xaml* file:</span></span>

    ```xaml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. <span data-ttu-id="0cf1d-116">在**解决方案资源管理器**中，右键单击*mainwindow.xaml* ，然后选择 "**查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-116">In **Solution Explorer**, right-click *MainWindow.xaml* and select **View Code**.</span></span> <span data-ttu-id="0cf1d-117">按照以下这些步骤修改代码：</span><span class="sxs-lookup"><span data-stu-id="0cf1d-117">Modify the code by following these steps:</span></span>

    1. <span data-ttu-id="0cf1d-118">添加下列命名空间：</span><span class="sxs-lookup"><span data-stu-id="0cf1d-118">Add the following namespaces:</span></span>

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. <span data-ttu-id="0cf1d-119">若要声明一个私有成员字段以保存 <xref:System.Activities.Presentation.WorkflowDesigner> 的实例，请将以下代码添加到 @no__t 1 类：</span><span class="sxs-lookup"><span data-stu-id="0cf1d-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class:</span></span>

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

    3. <span data-ttu-id="0cf1d-120">将下面的 `AddDesigner` 方法添加到 `MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="0cf1d-121">实现创建 @no__t 的实例，并向其添加一个 @no__t 活动，并将其放在 grid1**网格**的中间列中。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>

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

    4. <span data-ttu-id="0cf1d-122">注册设计器元数据，为所有内置活动添加设计器支持。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="0cf1d-123">通过此方法可以将活动从工具箱拖放到 <xref:System.Activities.Statements.Sequence> 中的原始 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 活动上。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="0cf1d-124">为此，请将 `RegisterMetadata` 方法添加到 @no__t 类：</span><span class="sxs-lookup"><span data-stu-id="0cf1d-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class:</span></span>

        ```csharp
        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        <span data-ttu-id="0cf1d-125">有关注册活动设计器的详细信息，请参阅 [How to：创建自定义活动设计器 @ no__t。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>

    5. <span data-ttu-id="0cf1d-126">在 `MainWindow` 类构造函数中，添加对上文声明的方法的调用，以便注册设计器支持元数据，并创建 <xref:System.Activities.Presentation.WorkflowDesigner>。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>

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
        > <span data-ttu-id="0cf1d-127">`RegisterMetadata` 方法注册包含 <xref:System.Activities.Statements.Sequence> 活动的内置活动的设计器元数据。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="0cf1d-128">由于 `AddDesigner` 方法使用 <xref:System.Activities.Statements.Sequence> 活动，因此必须先调用 `RegisterMetadata` 方法。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>

9. <span data-ttu-id="0cf1d-129">按<kbd>F5</kbd>生成并运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-129">Press <kbd>F5</kbd> to build and run the solution.</span></span>

10. <span data-ttu-id="0cf1d-130">请参阅 [Task 3：创建 "工具箱" 和 "PropertyGrid" 窗格 "no__t-0" 以了解如何向重新承载工作流设计器添加**工具箱**和**PropertyGrid**支持。</span><span class="sxs-lookup"><span data-stu-id="0cf1d-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cf1d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cf1d-131">See also</span></span>

- [<span data-ttu-id="0cf1d-132">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="0cf1d-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- <span data-ttu-id="0cf1d-133">@no__t 0Task 1：创建新的 Windows Presentation Foundation 应用程序 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="0cf1d-133">[Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md)</span></span>
- <span data-ttu-id="0cf1d-134">[Task 3：创建 "工具箱" 和 "PropertyGrid" 窗格 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="0cf1d-134">[Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md)</span></span>
