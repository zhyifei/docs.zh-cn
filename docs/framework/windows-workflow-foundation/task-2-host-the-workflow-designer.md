---
title: 任务 2：承载工作流设计器
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 92c5fa347cc7a2c0088ab8f4fbdfddf25ffb83c1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037860"
---
# <a name="task-2-host-the-workflow-designer"></a>任务 2：承载工作流设计器

本主题介绍在 Windows Presentation Foundation (WPF) 应用程序中[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]承载的实例的过程。

过程配置包含设计器的**网格**控件, 以编程方式创建包含默认<xref:System.Activities.Presentation.WorkflowDesigner> <xref:System.Activities.Statements.Sequence>活动的实例, 注册设计器元数据以提供所有内置活动, 并[!INCLUDE[wfd2](../../../includes/wfd2-md.md)]在 WPF 应用程序中承载。

### <a name="to-host-the-workflow-designer"></a>承载工作流设计器

1. 打开你在任务1中[创建的 HostingApplication 项目:创建新的 Windows Presentation Foundation 应用](task-1-create-a-new-wpf-app.md)程序。

2. 调整窗口的大小，以便更轻松地使用 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。 为此, 请在设计器中选择 " **mainwindow.xaml** ", 按 F4 以显示 "**属性**" 窗口, 并在 "**布局**" 部分中, 将 "**宽度**" 设置为 600, 将 "**高度**" 设置为值350。

3. 设置网格名称, 方法是在设计器中选择 "**网格**" 面板 (单击**mainwindow.xaml**中的框), 然后将 "**属性**" 窗口顶部的 "**名称**" 属性设置为 "grid1"。

4. 在 "**属性**" 窗口中, 单击`ColumnDefinitions`属性旁边的省略号 ( **...** ) 以打开 "**集合编辑器**" 对话框。

5. 在 "**集合编辑器**" 对话框中, 单击 "**添加**" 按钮三次, 以便在布局中插入三列。 第一列将包含 "**工具箱**", 第二列将承载[!INCLUDE[wfd2](../../../includes/wfd2-md.md)], 第三列将用于属性检查器。

6. 将中间列的属性设置为值"4*"。`Width`

7. 单击“确定” 以保存更改。 以下 XAML 将添加到 MainWindow.xaml 文件中：

    ```xml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. 在**解决方案资源管理器**中, 右键单击 mainwindow.xaml, 然后选择 "**查看代码**"。 按照以下这些步骤修改代码：

    1. 添加下列命名空间：

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. 若要声明某个私有成员字段包含 <xref:System.Activities.Presentation.WorkflowDesigner> 的实例，请将下面的代码添加到 `MainWindow` 类。

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

    3. 将下面的 `AddDesigner` 方法添加到 `MainWindow` 类。 实现创建的<xref:System.Activities.Presentation.WorkflowDesigner>实例, 向其中添加一个<xref:System.Activities.Statements.Sequence>活动, 并将其放在 grid1**网格**的中间列中。

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

    4. 注册设计器元数据，为所有内置活动添加设计器支持。 通过此方法可以将活动从工具箱拖放到 <xref:System.Activities.Statements.Sequence> 中的原始 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] 活动上。 为此，请将 `RegisterMetadata` 方法添加到 `MainWindow` 类中。

        ```csharp
        private void RegisterMetadata()
        {
            DesignerMetadata dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        有关注册活动设计器的详细信息, [请参阅如何:创建自定义活动设计](how-to-create-a-custom-activity-designer.md)器。

    5. 在 `MainWindow` 类构造函数中，添加对上文声明的方法的调用，以便注册设计器支持元数据，并创建 <xref:System.Activities.Presentation.WorkflowDesigner>。

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
        > `RegisterMetadata` 方法注册包含 <xref:System.Activities.Statements.Sequence> 活动的内置活动的设计器元数据。 由于 `AddDesigner` 方法使用 <xref:System.Activities.Statements.Sequence> 活动，因此必须先调用 `RegisterMetadata` 方法。

9. 按 F5 生成并运行解决方案。

10. 请[参阅任务 3:创建 "工具箱" 和 "](task-3-create-the-toolbox-and-propertygrid-panes.md) PropertyGrid" 窗格, 了解如何向重新承载工作流设计器添加 **"工具箱" 和 "** **PropertyGrid** " 支持。

## <a name="see-also"></a>请参阅

- [重新托管工作流设计器](rehosting-the-workflow-designer.md)
- [任务 1:创建新的 Windows Presentation Foundation 应用程序](task-1-create-a-new-wpf-app.md)
- [任务 3:创建 "工具箱" 和 "PropertyGrid" 窗格](task-3-create-the-toolbox-and-propertygrid-panes.md)
