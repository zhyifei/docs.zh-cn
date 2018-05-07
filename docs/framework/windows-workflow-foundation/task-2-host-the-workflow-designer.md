---
title: 任务 2：承载工作流设计器
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 8ac6b3590d146909c1cb9fd8cf9cae2352b0155b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="task-2-host-the-workflow-designer"></a>任务 2：承载工作流设计器
本主题描述用于托管的实例的过程[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]Windows Presentation Foundation (WPF) 应用程序中。  
  
 过程配置**网格**控件包含设计器中，以编程方式创建的一个实例<xref:System.Activities.Presentation.WorkflowDesigner>包含默认<xref:System.Activities.Statements.Sequence>活动，注册设计器的元数据，以提供所有内置活动和主机的设计器支持[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]中[!INCLUDE[avalon2](../../../includes/avalon2-md.md)]应用程序。  
  
### <a name="to-host-the-workflow-designer"></a>承载工作流设计器  
  
1.  打开 HostingApplication 项目中创建[任务 1： 创建一个新的 Windows Presentation Foundation 应用程序](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)。  
  
2.  调整窗口的大小，以便更轻松地使用 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。 若要执行此操作，选择**MainWindow**在设计器中，按 F4 以显示**属性**窗口中，然后在**布局**部分中，将**宽度**为 600 的值与**高度**为值 350。  
  
3.  通过选择设置网格名称**网格**设计器中的面板 (单击内的小框**MainWindow**) 和设置**名称**顶部属性**属性**窗口为"grid1"。  
  
4.  在**属性**窗口中，单击省略号 (**...**) 旁边`ColumnDefinitions`以打开**集合编辑器**对话框。  
  
5.  在**集合编辑器**对话框中，单击**添加**按钮三次以布局中插入三个列。 第一列将包含**工具箱**，第二列将承载[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]，和第三列用于属性检查器。  
  
6.  设置`Width`中间列的值的属性"4 *"。  
  
7.  单击“确定”  以保存更改。 以下 XAML 将添加到 MainWindow.xaml 文件中：  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8.  在**解决方案资源管理器**，右击 MainWindow.xaml 并选择**查看代码**。 按照以下这些步骤修改代码：  
  
    1.  添加下列命名空间：  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  若要声明某个私有成员字段包含 <xref:System.Activities.Presentation.WorkflowDesigner> 的实例，请将下面的代码添加到 `MainWindow` 类。  
  
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
  
    3.  将下面的 `AddDesigner` 方法添加到 `MainWindow` 类。 实现创建的实例<xref:System.Activities.Presentation.WorkflowDesigner>，将添加<xref:System.Activities.Statements.Sequence>活动，并将其放在中间栏中的置于 grid1**网格**。  
  
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
  
    4.  注册设计器元数据，为所有内置活动添加设计器支持。 通过此方法可以将活动从工具箱拖放到 <xref:System.Activities.Statements.Sequence> 中的原始 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 活动上。 为此，请将 `RegisterMetadata` 方法添加到 `MainWindow` 类中。  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         有关注册活动设计器的详细信息，请参阅[如何： 创建自定义活动设计器](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md)。  
  
    5.  在 `MainWindow` 类构造函数中，添加对上文声明的方法的调用，以便注册设计器支持元数据，并创建 <xref:System.Activities.Presentation.WorkflowDesigner>。  
  
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
        >  `RegisterMetadata` 方法注册包含 <xref:System.Activities.Statements.Sequence> 活动的内置活动的设计器元数据。 由于 `AddDesigner` 方法使用 <xref:System.Activities.Statements.Sequence> 活动，因此必须先调用 `RegisterMetadata` 方法。  
  
9. 按 F5 生成并运行解决方案。  
  
10. 请参阅[任务 3： 创建工具箱窗格和属性网格窗格](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)若要了解如何添加**工具箱**和**属性网格**到重新承载的工作流设计器支持。  
  
## <a name="see-also"></a>请参阅  
 [重新托管工作流设计器](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [任务 1：新建 Windows Presentation Foundation 应用程序](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
 [任务 3：创建“工具箱”和“属性网格”窗格](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)
