---
title: 任务 3:创建工具箱和属性网格窗格
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 8e332c2caa43e1c9703272d7f2be16b545c44fd3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558418"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="2f0f2-102">任务 3:创建工具箱和属性网格窗格</span><span class="sxs-lookup"><span data-stu-id="2f0f2-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>
<span data-ttu-id="2f0f2-103">在本任务中，您将创建**工具箱**并**PropertyGrid**窗格并将其添加到重新承载[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>  
  
 <span data-ttu-id="2f0f2-104">有关参考中的任务应在完成这三个后 MainWindow.xaml.cs 文件中的代码[重新承载工作流设计器](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)系列主题提供本主题末尾处。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="2f0f2-105">创建工具箱并将其添加到网格中</span><span class="sxs-lookup"><span data-stu-id="2f0f2-105">To create the Toolbox and add it to the grid</span></span>  
  
1.  <span data-ttu-id="2f0f2-106">打开按照中所述的过程获得的 HostingApplication 项目[任务 2:承载工作流设计器](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md).</span></span>  
  
2.  <span data-ttu-id="2f0f2-107">在中**解决方案资源管理器**窗格中，右击 MainWindow.xaml 文件，并选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-107">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
3.  <span data-ttu-id="2f0f2-108">添加`GetToolboxControl`方法`MainWindow`类，该类创建<xref:System.Activities.Presentation.Toolbox.ToolboxControl>，添加一个新**工具箱**类别与**工具箱**，并将分配<xref:System.Activities.Statements.Assign>和<xref:System.Activities.Statements.Sequence>向该类别的活动类型。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>  
  
    ```csharp  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
    ```  
  
4.  <span data-ttu-id="2f0f2-109">添加一个私有`AddToolbox`方法`MainWindow`类将放置**工具箱**网格上的左侧列中。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5.  <span data-ttu-id="2f0f2-110">在 `AddToolBox` 类构造函数中添加对 `MainWindow()` 方法的调用，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6.  <span data-ttu-id="2f0f2-111">按“F5”生成并运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-111">Press F5 to build and run your solution.</span></span> <span data-ttu-id="2f0f2-112">**工具箱**包含<xref:System.Activities.Statements.Assign>和<xref:System.Activities.Statements.Sequence>应显示的活动。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>  
  
### <a name="to-create-the-propertygrid"></a><span data-ttu-id="2f0f2-113">创建属性网格</span><span class="sxs-lookup"><span data-stu-id="2f0f2-113">To create the PropertyGrid</span></span>  
  
1.  <span data-ttu-id="2f0f2-114">在中**解决方案资源管理器**窗格中，右击 MainWindow.xaml 文件，并选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-114">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="2f0f2-115">添加`AddPropertyInspector`方法`MainWindow`类，以放置**PropertyGrid**网格上的最右侧列中的窗格。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid.</span></span>  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3.  <span data-ttu-id="2f0f2-116">在 `AddPropertyInspector` 类构造函数中添加对 `MainWindow()` 方法的调用，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
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
  
4.  <span data-ttu-id="2f0f2-117">按 F5 生成并运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-117">Press F5 to build and run the solution.</span></span> <span data-ttu-id="2f0f2-118">**工具箱**，工作流设计画布和**PropertyGrid**窗格应显示，并拖动时<xref:System.Activities.Statements.Assign>活动或<xref:System.Activities.Statements.Sequence>到设计画布上的活动属性网格应根据突出显示的活动更新。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f0f2-119">示例</span><span class="sxs-lookup"><span data-stu-id="2f0f2-119">Example</span></span>  
 <span data-ttu-id="2f0f2-120">现在，MainWindow.xaml.cs 文件应包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="2f0f2-120">The MainWindow.xaml.cs file should now contain the following code.</span></span>  
  
```  
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
//dlls added  
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
            //Create an instance of WorkflowDesigner class.  
            this.wd = new WorkflowDesigner();  
  
            //Place the designer canvas in the middle column of the grid.  
            Grid.SetColumn(this.wd.View, 1);  
  
            //Load a new Sequence as default.  
            this.wd.Load(new Sequence());  
  
            //Add the designer canvas to the grid.  
            grid1.Children.Add(this.wd.View);  
        }  
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
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
  
## <a name="see-also"></a><span data-ttu-id="2f0f2-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f0f2-121">See also</span></span>
- [<span data-ttu-id="2f0f2-122">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="2f0f2-122">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)
- [<span data-ttu-id="2f0f2-123">任务 1:创建新的 Windows Presentation Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="2f0f2-123">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="2f0f2-124">任务 2:承载工作流设计器</span><span class="sxs-lookup"><span data-stu-id="2f0f2-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
