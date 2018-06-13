---
title: 任务 2：承载工作流设计器
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 8ac6b3590d146909c1cb9fd8cf9cae2352b0155b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519059"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="fe03f-102">任务 2：承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="fe03f-102">Task 2: Host the Workflow Designer</span></span>
<span data-ttu-id="fe03f-103">本主题描述用于托管的实例的过程[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]Windows Presentation Foundation (WPF) 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="fe03f-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="fe03f-104">过程配置**网格**控件包含设计器中，以编程方式创建的一个实例<xref:System.Activities.Presentation.WorkflowDesigner>包含默认<xref:System.Activities.Statements.Sequence>活动，注册设计器的元数据，以提供所有内置活动和主机的设计器支持[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]中[!INCLUDE[avalon2](../../../includes/avalon2-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe03f-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] application.</span></span>  
  
### <a name="to-host-the-workflow-designer"></a><span data-ttu-id="fe03f-105">承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="fe03f-105">To host the workflow designer</span></span>  
  
1.  <span data-ttu-id="fe03f-106">打开 HostingApplication 项目中创建[任务 1： 创建一个新的 Windows Presentation Foundation 应用程序](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)。</span><span class="sxs-lookup"><span data-stu-id="fe03f-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md).</span></span>  
  
2.  <span data-ttu-id="fe03f-107">调整窗口的大小，以便更轻松地使用 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fe03f-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="fe03f-108">若要执行此操作，选择**MainWindow**在设计器中，按 F4 以显示**属性**窗口中，然后在**布局**部分中，将**宽度**为 600 的值与**高度**为值 350。</span><span class="sxs-lookup"><span data-stu-id="fe03f-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>  
  
3.  <span data-ttu-id="fe03f-109">通过选择设置网格名称**网格**设计器中的面板 (单击内的小框**MainWindow**) 和设置**名称**顶部属性**属性**窗口为"grid1"。</span><span class="sxs-lookup"><span data-stu-id="fe03f-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>  
  
4.  <span data-ttu-id="fe03f-110">在**属性**窗口中，单击省略号 (**...**) 旁边`ColumnDefinitions`以打开**集合编辑器**对话框。</span><span class="sxs-lookup"><span data-stu-id="fe03f-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="fe03f-111">在**集合编辑器**对话框中，单击**添加**按钮三次以布局中插入三个列。</span><span class="sxs-lookup"><span data-stu-id="fe03f-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="fe03f-112">第一列将包含**工具箱**，第二列将承载[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]，和第三列用于属性检查器。</span><span class="sxs-lookup"><span data-stu-id="fe03f-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>  
  
6.  <span data-ttu-id="fe03f-113">设置`Width`中间列的值的属性"4 \*"。</span><span class="sxs-lookup"><span data-stu-id="fe03f-113">Set the `Width` property of the middle column to the value "4\*".</span></span>  
  
7.  <span data-ttu-id="fe03f-114">单击“确定”  以保存更改。</span><span class="sxs-lookup"><span data-stu-id="fe03f-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="fe03f-115">以下 XAML 将添加到 MainWindow.xaml 文件中：</span><span class="sxs-lookup"><span data-stu-id="fe03f-115">The following XAML is added to your MainWindow.xaml file:</span></span>  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8.  <span data-ttu-id="fe03f-116">在**解决方案资源管理器**，右击 MainWindow.xaml 并选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="fe03f-116">In **Solution Explorer**, right-click MainWindow.xaml and select **View Code**.</span></span> <span data-ttu-id="fe03f-117">按照以下这些步骤修改代码：</span><span class="sxs-lookup"><span data-stu-id="fe03f-117">Modify the code by following these steps:</span></span>  
  
    1.  <span data-ttu-id="fe03f-118">添加下列命名空间：</span><span class="sxs-lookup"><span data-stu-id="fe03f-118">Add the following namespaces:</span></span>  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  <span data-ttu-id="fe03f-119">若要声明某个私有成员字段包含 <xref:System.Activities.Presentation.WorkflowDesigner> 的实例，请将下面的代码添加到 `MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="fe03f-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class.</span></span>  
  
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
  
    3.  <span data-ttu-id="fe03f-120">将下面的 `AddDesigner` 方法添加到 `MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="fe03f-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="fe03f-121">实现创建的实例<xref:System.Activities.Presentation.WorkflowDesigner>，将添加<xref:System.Activities.Statements.Sequence>活动，并将其放在中间栏中的置于 grid1**网格**。</span><span class="sxs-lookup"><span data-stu-id="fe03f-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>  
  
        ```csharp  
        private void AddDesigner()  
        {  
            //Create an instance of WorkflowDesigner class.  
            this.wd = new WorkflowDesigner();  
  
            //Place the designer canvas in the middle column of the grid.  
            Grid.SetColumn(this.wd.View, 1);  
  
            //Load a new Sequence as default.  
            this.wd.Load(new Sequence());  
  
            //Add the designer canvas to the grid.  
            grid1.Children.Add(this.wd.View);  
        }  
        ```  
  
    4.  <span data-ttu-id="fe03f-122">注册设计器元数据，为所有内置活动添加设计器支持。</span><span class="sxs-lookup"><span data-stu-id="fe03f-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="fe03f-123">通过此方法可以将活动从工具箱拖放到 <xref:System.Activities.Statements.Sequence> 中的原始 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 活动上。</span><span class="sxs-lookup"><span data-stu-id="fe03f-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="fe03f-124">为此，请将 `RegisterMetadata` 方法添加到 `MainWindow` 类中。</span><span class="sxs-lookup"><span data-stu-id="fe03f-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class.</span></span>  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         <span data-ttu-id="fe03f-125">有关注册活动设计器的详细信息，请参阅[如何： 创建自定义活动设计器](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="fe03f-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md).</span></span>  
  
    5.  <span data-ttu-id="fe03f-126">在 `MainWindow` 类构造函数中，添加对上文声明的方法的调用，以便注册设计器支持元数据，并创建 <xref:System.Activities.Presentation.WorkflowDesigner>。</span><span class="sxs-lookup"><span data-stu-id="fe03f-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>  
  
        ```csharp  
        public MainWindow()  
        {  
            InitializeComponent();  
  
            // Register the metadata  
            RegisterMetadata();  
  
            // Add the WFF Designer  
            AddDesigner();  
        }  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="fe03f-127">`RegisterMetadata` 方法注册包含 <xref:System.Activities.Statements.Sequence> 活动的内置活动的设计器元数据。</span><span class="sxs-lookup"><span data-stu-id="fe03f-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="fe03f-128">由于 `AddDesigner` 方法使用 <xref:System.Activities.Statements.Sequence> 活动，因此必须先调用 `RegisterMetadata` 方法。</span><span class="sxs-lookup"><span data-stu-id="fe03f-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>  
  
9. <span data-ttu-id="fe03f-129">按 F5 生成并运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="fe03f-129">Press F5 to build and run the solution.</span></span>  
  
10. <span data-ttu-id="fe03f-130">请参阅[任务 3： 创建工具箱窗格和属性网格窗格](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)若要了解如何添加**工具箱**和**属性网格**到重新承载的工作流设计器支持。</span><span class="sxs-lookup"><span data-stu-id="fe03f-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe03f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe03f-131">See Also</span></span>  
 [<span data-ttu-id="fe03f-132">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="fe03f-132">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="fe03f-133">任务 1：新建 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="fe03f-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
 [<span data-ttu-id="fe03f-134">任务 3：创建“工具箱”和“属性网格”窗格</span><span class="sxs-lookup"><span data-stu-id="fe03f-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)
