---
title: 任务 3：创建工具箱窗格和属性网格窗格
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 402a25c1cb82c245afa94f58cefc180515622ea9
ms.sourcegitcommit: 992f80328b51b165051c42ff5330788627abe973
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2019
ms.locfileid: "72275858"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="3867f-102">任务 3：创建工具箱窗格和属性网格窗格</span><span class="sxs-lookup"><span data-stu-id="3867f-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>

<span data-ttu-id="3867f-103">在此任务中，将创建 "**工具箱**" 和 " **PropertyGrid** " 窗格，并将其添加到 "重新承载 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3867f-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>

<span data-ttu-id="3867f-104">若要参考，MainWindow.xaml.cs 文件中的三个任务完成后，应在重新承载文件中的代码在本主题末尾提供了[工作流设计器](rehosting-the-workflow-designer.md)系列主题。</span><span class="sxs-lookup"><span data-stu-id="3867f-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>

## <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="3867f-105">创建工具箱并将其添加到网格中</span><span class="sxs-lookup"><span data-stu-id="3867f-105">To create the Toolbox and add it to the grid</span></span>

1. <span data-ttu-id="3867f-106">按照[任务2：承载工作流设计器](task-2-host-the-workflow-designer.md)中所述的过程操作，打开所获得的 HostingApplication 项目。</span><span class="sxs-lookup"><span data-stu-id="3867f-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md).</span></span>

2. <span data-ttu-id="3867f-107">在**解决方案资源管理器**窗格中，右键单击*mainwindow.xaml*文件，然后选择 "**查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="3867f-107">In the **Solution Explorer** pane, right-click the *MainWindow.xaml* file and select **View Code**.</span></span>

3. <span data-ttu-id="3867f-108">将 `GetToolboxControl` 方法添加到创建 <xref:System.Activities.Presentation.Toolbox.ToolboxControl>的 `MainWindow` 类，将新的 **"工具箱**" 类别添加到 "**工具箱**"，并将 <xref:System.Activities.Statements.Assign> 和 <xref:System.Activities.Statements.Sequence> 活动类型分配给该类别。</span><span class="sxs-lookup"><span data-stu-id="3867f-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>

    ```csharp
    private ToolboxControl GetToolboxControl()
    {
        // Create the ToolBoxControl.
        var ctrl = new ToolboxControl();

        // Create a category.
        var category = new ToolboxCategory("category1");

        // Create Toolbox items.
        var tool1 =
            new ToolboxItemWrapper("System.Activities.Statements.Assign",
            typeof(Assign).Assembly.FullName, null, "Assign");

        var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
            typeof(Sequence).Assembly.FullName, null, "Sequence");

        // Add the Toolbox items to the category.
        category.Add(tool1);
        category.Add(tool2);

        // Add the category to the ToolBox control.
        ctrl.Categories.Add(category);
        return ctrl;
    }
    ```

4. <span data-ttu-id="3867f-109">向 `MainWindow` 类添加私有 `AddToolbox` 方法，该方法将 "**工具箱**" 放置在网格上的左列中。</span><span class="sxs-lookup"><span data-stu-id="3867f-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>

    ```csharp
    private void AddToolBox()
    {
        ToolboxControl tc = GetToolboxControl();
        Grid.SetColumn(tc, 0);
        grid1.Children.Add(tc);
    }
    ```

5. <span data-ttu-id="3867f-110">在 `MainWindow()` 类构造函数中添加对 `AddToolBox` 方法的调用，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="3867f-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code:</span></span>

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();

        this.AddToolBox();
    }
    ```

6. <span data-ttu-id="3867f-111">按<kbd>F5</kbd>生成并运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="3867f-111">Press <kbd>F5</kbd> to build and run your solution.</span></span> <span data-ttu-id="3867f-112">应显示包含 <xref:System.Activities.Statements.Assign> 和 <xref:System.Activities.Statements.Sequence> 活动的 "**工具箱**"。</span><span class="sxs-lookup"><span data-stu-id="3867f-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>

## <a name="to-create-the-propertygrid"></a><span data-ttu-id="3867f-113">创建属性网格</span><span class="sxs-lookup"><span data-stu-id="3867f-113">To create the PropertyGrid</span></span>

1. <span data-ttu-id="3867f-114">在**解决方案资源管理器**窗格中，右键单击*mainwindow.xaml*文件，然后选择 "**查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="3867f-114">In the **Solution Explorer** pane, right-click the *MainWindow.xaml* file and select **View Code**.</span></span>

2. <span data-ttu-id="3867f-115">将 `AddPropertyInspector` 方法添加到 `MainWindow` 类，以便将 " **PropertyGrid** " 窗格放置在网格上的最右侧列中：</span><span class="sxs-lookup"><span data-stu-id="3867f-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid:</span></span>

    ```csharp
    private void AddPropertyInspector()
    {
        Grid.SetColumn(wd.PropertyInspectorView, 2);
        grid1.Children.Add(wd.PropertyInspectorView);
    }
    ```

3. <span data-ttu-id="3867f-116">在 `MainWindow()` 类构造函数中添加对 `AddPropertyInspector` 方法的调用，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="3867f-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code:</span></span>

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();
        this.AddToolBox();

        this.AddPropertyInspector();
    }
    ```

4. <span data-ttu-id="3867f-117">按<kbd>F5</kbd>生成并运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="3867f-117">Press <kbd>F5</kbd> to build and run the solution.</span></span> <span data-ttu-id="3867f-118">"**工具箱**"、"工作流设计画布" 和 " **PropertyGrid** " 窗格应全部显示，将 <xref:System.Activities.Statements.Assign> 活动或 <xref:System.Activities.Statements.Sequence> 活动拖到设计画布上时，属性网格应根据突出显示的活动进行更新。</span><span class="sxs-lookup"><span data-stu-id="3867f-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>

## <a name="example"></a><span data-ttu-id="3867f-119">示例</span><span class="sxs-lookup"><span data-stu-id="3867f-119">Example</span></span>

<span data-ttu-id="3867f-120">*MainWindow.xaml.cs*文件现在应包含以下代码：</span><span class="sxs-lookup"><span data-stu-id="3867f-120">The *MainWindow.xaml.cs* file should now contain the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;
// dlls added.
using System.Activities;
using System.Activities.Core.Presentation;
using System.Activities.Presentation;
using System.Activities.Presentation.Metadata;
using System.Activities.Presentation.Toolbox;
using System.Activities.Statements;
using System.ComponentModel;

namespace HostingApplication
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        private WorkflowDesigner wd;

        public MainWindow()
        {
            InitializeComponent();
            RegisterMetadata();
            AddDesigner();
            this.AddToolBox();
            this.AddPropertyInspector();
        }

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

        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }

        private ToolboxControl GetToolboxControl()
        {
            // Create the ToolBoxControl.
            var ctrl = new ToolboxControl();

            // Create a category.
            var category = new ToolboxCategory("category1");

            // Create Toolbox items.
            var tool1 =
                new ToolboxItemWrapper("System.Activities.Statements.Assign",
                typeof(Assign).Assembly.FullName, null, "Assign");

            var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
                typeof(Sequence).Assembly.FullName, null, "Sequence");

            // Add the Toolbox items to the category.
            category.Add(tool1);
            category.Add(tool2);

            // Add the category to the ToolBox control.
            ctrl.Categories.Add(category);
            return ctrl;
        }

        private void AddToolBox()
        {
            ToolboxControl tc = GetToolboxControl();
            Grid.SetColumn(tc, 0);
            grid1.Children.Add(tc);
        }

        private void AddPropertyInspector()
        {
            Grid.SetColumn(wd.PropertyInspectorView, 2);
            grid1.Children.Add(wd.PropertyInspectorView);
        }

    }
}
```

## <a name="see-also"></a><span data-ttu-id="3867f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3867f-121">See also</span></span>

- [<span data-ttu-id="3867f-122">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="3867f-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="3867f-123">任务 1：新建 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="3867f-123">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="3867f-124">任务 2：托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="3867f-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
