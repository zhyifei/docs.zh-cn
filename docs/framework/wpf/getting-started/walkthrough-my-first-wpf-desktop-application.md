---
title: 在 Visual Studio 2019 - .NET 框架中创建您的第一个 WPF 应用
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: facb9ebebd9ce1904886a946277185ac2c2e4bc4
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463928"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>教程：在 Visual Studio 2019 中创建您的第一个 WPF 应用程序

本文介绍如何开发 Windows 演示文稿基础 （WPF） 桌面应用程序，该应用程序包含大多数 WPF 应用程序共有的元素：可扩展的应用程序标记语言 （XAML） 标记、代码后面、应用程序定义、控件、布局、数据绑定和样式。 要开发该应用程序，您将使用可视化工作室。

在本教程中，你将了解如何执行以下操作：
> [!div class="checklist"]
>
> - 创建 WPF 项目。
> - 使用 XAML 设计应用程序的用户界面 （UI） 的外观。
> - 编写代码以生成应用程序的行为。
> - 创建应用程序定义来管理应用程序。
> - 添加控件并创建布局以组成应用程序 UI。
> - 在整个应用程序的 UI 中创建一致外观的样式。
> - 将 UI 绑定到数据，以便从数据中填充 UI 并保持数据和 UI 同步。

在本教程结束时，您将构建一个独立的 Windows 应用程序，允许用户查看所选人员的费用报告。 该应用程序由托管在浏览器样式窗口中的多个 WPF 页面组成。

> [!TIP]
> 本教程中使用的示例代码可用于[教程 WPF 应用示例代码](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)中的 Visual Basic 和 C#。
>
> 您可以使用此页面顶部的语言选择器在 C# 和 Visual Basic 之间切换示例代码的代码语言。

## <a name="prerequisites"></a>先决条件

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)安装 **.NET 桌面开发**工作负载。

   有关安装最新版本的可视化工作室的详细信息，请参阅[安装可视化工作室](/visualstudio/install/install-visual-studio)。

## <a name="create-the-application-project"></a>创建应用程序项目

第一步是创建应用程序基础结构，其中包括应用程序定义、两页和一个映像。

1. 在名为**`ExpenseIt`**"可视基本"或"可视化 C#的可视化 C# 中创建新的 WPF 应用程序项目：

   1. 打开可视化工作室，在"**开始"** 菜单下选择 **"创建新项目**"。

      将打开"**创建新项目**"对话框。

   2. 在 **"语言**"下拉列表中，选择**C#** 或**可视化基本**。

   3. 选择**WPF 应用 （.NET 框架）** 模板，然后选择 **"下一步**"。

      ![“创建新项目”对话框](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      将打开"**配置新项目**"对话框。

   4. 输入项目名称**`ExpenseIt`**，然后选择 **"创建**"。

      ![配置新项目对话框](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio 创建项目并打开名为**MainWindow.xaml**的默认应用程序窗口的设计器。

2. 打开*应用程序.xaml（* 视觉基本）或*App.xaml* （C#）。

    此 XAML 文件定义 WPF 应用程序和任何应用程序资源。 您还可以使用此文件指定 UI，在本例中*为 MainWindow.xaml，* 在应用程序启动时自动显示。

    您的 XAML 在可视化基础知识中应如下所示：

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    和以下 C#：

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. 打开*主窗口.xaml*。

    此 XAML 文件是应用程序的主窗口，并显示在页面中创建的内容。 类<xref:System.Windows.Window>定义窗口的属性，如其标题、大小或图标，并处理事件，如关闭或隐藏。

4. 将<xref:System.Windows.Window>元素更改为 ，<xref:System.Windows.Navigation.NavigationWindow>如以下 XAML 所示：

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   此应用根据用户输入导航到不同的内容。 这就是为什么需要将主要<xref:System.Windows.Window>需要更改为 。 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow>继承<xref:System.Windows.Window>的所有属性。 XAML<xref:System.Windows.Navigation.NavigationWindow>文件中的元素创建类的<xref:System.Windows.Navigation.NavigationWindow>实例。 有关详细信息，请参阅[导航概述](../app-development/navigation-overview.md)。

5. 从<xref:System.Windows.Navigation.NavigationWindow>标记<xref:System.Windows.Controls.Grid>之间删除元素。

6. 更改<xref:System.Windows.Navigation.NavigationWindow>元素的 XAML 代码中的以下属性：

    - 将<xref:System.Windows.Window.Title%2A>属性设置为""。`ExpenseIt`

    - 将<xref:System.Windows.FrameworkElement.Height%2A>属性设置为 350 像素。

    - 将<xref:System.Windows.FrameworkElement.Width%2A>属性设置为 500 像素。

    对于可视化基本版，您的 XAML 应如下所示：

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    与以下 C# 类似：

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. 打开*主窗口.xaml.vb*或*MainWindow.xaml.cs*。

    此文件是一个代码背后的文件，其中包含用于处理*MainWindow.xaml*中声明的事件的代码。 此文件包含在 XAML 中定义的窗口的分部类。

8. 如果使用 C#，则更改从 派生`MainWindow`的<xref:System.Windows.Navigation.NavigationWindow>类。 （在可视化基本版中，当您在 XAML 中更改窗口时，会自动发生这种情况。您的 C# 代码现在应如下所示：

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>将文件添加到应用程序

本部分将向应用程序添加两个页面和一个图像。

1. 向项目添加新页面，并命名为*`ExpenseItHome.xaml`*：

   1. 在**解决方案资源管理器****`ExpenseIt`** 中，右键单击项目节点并选择 **"添加** > **页面**"。

   1. 在"**添加新项目"** 对话框中，已选择**页面 （WPF）** 模板。 输入名称**`ExpenseItHome`**，然后选择 **"添加**"。

    此页是应用程序启动时显示的第一页。 它将显示要从中选择的人员列表，以显示其支出报表。

1. 打开*`ExpenseItHome.xaml`*。

1. 将<xref:System.Windows.Controls.Page.Title%2A>设置为""。`ExpenseIt - Home`

1. 将`DesignHeight`设置为 350 像素，`DesignWidth`将 设置为 500 像素。

    XAML 现在显示如下视觉基础：

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    与以下 C# 类似：

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. 打开*主窗口.xaml*。

1. 将属性<xref:System.Windows.Navigation.NavigationWindow.Source%2A>添加到元素并将其<xref:System.Windows.Navigation.NavigationWindow>设置为""。`ExpenseItHome.xaml`

    这将集*`ExpenseItHome.xaml`* 为应用程序启动时打开的第一页。

    可视化基础知识中的 XAML 示例：

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    在 C# 中：

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > 您还可以在 **"属性"** 窗口的 **"杂项**"类别中设置 **"源**"属性。
   >
   > ![属性窗口中的源属性](./media/properties-source.png)

1. 向项目添加另一个新 WPF 页面，并将其命名为 *"费用报告页.xaml：：*

   1. 在**解决方案资源管理器****`ExpenseIt`** 中，右键单击项目节点并选择 **"添加** > **页面**"。

   1. 在"**添加新项目"** 对话框中，选择**页面 （WPF）** 模板。 输入名称 **"支出报告页**"，然后选择 **"添加**"。

    此页将显示**`ExpenseItHome`** 页面上所选人员的费用报表。

1. 打开*费用报告页.xaml*。

1. 将<xref:System.Windows.Controls.Page.Title%2A>设置为""。`ExpenseIt - View Expense`

1. 将`DesignHeight`设置为 350 像素，`DesignWidth`将 设置为 500 像素。

    *支出报告页.xaml*现在在可视化基础知识中如下所示：

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    和以下 C#：

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. 打开*费用它Home.xaml.vb*和*费用报告页.xaml.vb，* 或*ExpenseItHome.xaml.cs*和*ExpenseReportPage.xaml.cs。*

    创建新的 Page 文件时，Visual Studio 会自动创建其*代码背后的*文件。 这些代码隐藏文件处理响应用户输入的逻辑。

    对于 ： 的代码应如下所示**`ExpenseItHome`**：

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    和下面的**费用报告页**：

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. 向项目添加名为*水印.png*的图像。 您可以创建自己的映像、从示例代码复制文件或从[Microsoft/WPF-示例](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png)GitHub 存储库获取该文件。

    1. 右键单击项目节点并选择"**添加** > **现有项目**"，或按 **"移动**+**Alt**+**A**"。

    2. 在"**添加现有项目"** 对话框中，将文件筛选器设置为 **"所有文件**"或 **"图像文件**"，浏览到要使用的图像文件，然后选择"**添加**"。

## <a name="build-and-run-the-application"></a>构建并运行应用程序

1. 要生成和运行应用程序，请按**F5**或从**调试**菜单中选择 **"开始调试**"。

    下图显示了带有<xref:System.Windows.Navigation.NavigationWindow>按钮的应用程序：

    ![生成并运行应用程序后。](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. 关闭应用程序以返回到可视化工作室。

## <a name="create-the-layout"></a>创建布局

布局提供了放置 UI 元素的有序方式，并在调整 UI 大小时管理这些元素的大小和位置。 通常使用以下布局控件之一来创建布局：

- <xref:System.Windows.Controls.Canvas>- 定义一个区域，您可以在其中使用与"画布"区域相关的坐标显式定位子元素。
- <xref:System.Windows.Controls.DockPanel>- 定义一个区域，您可以在其中水平或垂直排列子元素，彼此相对。
- <xref:System.Windows.Controls.Grid>- 定义由列和行组成的灵活网格区域。
- <xref:System.Windows.Controls.StackPanel>- 将子元素排列成一条可以水平或垂直方向的直线。
- <xref:System.Windows.Controls.VirtualizingStackPanel>- 在水平或垂直方向的一条线上排列和虚拟化内容。
- <xref:System.Windows.Controls.WrapPanel>- 将子元素从左向右定位在顺序位置，将内容分解到包含框边缘的下一行。 后续排序按顺序从上到下或从右向左进行，具体取决于方向属性的值。

每个布局控件都支持其子元素的特定类型的布局。 `ExpenseIt`页面可以调整大小，并且每个页面都有与其他元素一起水平和垂直排列的元素。 在此示例中，<xref:System.Windows.Controls.Grid>用作应用程序的布局元素。

> [!TIP]
> 有关<xref:System.Windows.Controls.Panel>元素的详细信息，请参阅[面板概述](../controls/panels-overview.md)。 有关布局的详细信息，请参阅[布局](../advanced/layout.md)。

在本节中，通过将列和行定义添加到 in，<xref:System.Windows.Controls.Grid>*`ExpenseItHome.xaml`* 可以创建包含三行和 10 像素边距的单列表。

1. 在*`ExpenseItHome.xaml`* 中，<xref:System.Windows.FrameworkElement.Margin%2A>将元素的属性<xref:System.Windows.Controls.Grid>设置为"10，0，10，10"，对应于左、上、右和下边距：

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > 您还可以在"**属性**"窗口中的 **"布局"** 类别下设置 **"边距**"值：
   >
   > ![属性窗口中的边距值](./media/properties-margin.png)

2. 在<xref:System.Windows.Controls.Grid>标记之间添加以下 XAML 以创建行和列定义：

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    两<xref:System.Windows.Controls.RowDefinition.Height%2A>行的 设置为<xref:System.Windows.GridLength.Auto%2A>，这意味着行的大小基于行中的内容。 默认值<xref:System.Windows.Controls.RowDefinition.Height%2A>为<xref:System.Windows.GridUnitType.Star>大小调整，这意味着行高度是可用空间的加权比例。 例如，如果两行各有一个<xref:System.Windows.Controls.RowDefinition.Height%2A>"*"，则它们每个行的高度是可用空间的一半。

    您<xref:System.Windows.Controls.Grid>现在应该包含以下 XAML：

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>添加控件

在本节中，您将更新主页 UI 以显示人员列表，其中选择一个人来显示其支出报表。 控件是允许用户与应用程序交互的 UI 对象。 有关详细信息，请参阅[控件](../controls/index.md)。

要创建此 UI，您将将以下元素添加到*`ExpenseItHome.xaml`*：

- A（<xref:System.Windows.Controls.ListBox>用于人员列表）。
- A（<xref:System.Windows.Controls.Label>对于列表标头）。
- （<xref:System.Windows.Controls.Button>单击以查看列表中所选人员的支出报表）。

通过设置附加属性，将每个控件放置在<xref:System.Windows.Controls.Grid>的一<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>行中。 有关附加属性的详细信息，请参阅[附加属性概述](../advanced/attached-properties-overview.md)。

1. 在*`ExpenseItHome.xaml`* 中，在<xref:System.Windows.Controls.Grid>标记之间添加以下 XAML：

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > 还可以通过将控件从 **"工具箱"** 窗口拖动到设计窗口，然后在 **"属性"** 窗口中设置其属性来创建控件。

2. 生成并运行应用程序。

    下图显示了您创建的控件：

![支出它示例屏幕截图显示名称列表](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>添加图像和标题

在本节中，您将使用图像和页面标题更新主页 UI。

1. 在*`ExpenseItHome.xaml`* 中，将另一<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A>列添加到固定<xref:System.Windows.Controls.ColumnDefinition.Width%2A>为 230 像素的 列：

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. 向 添加<xref:System.Windows.Controls.Grid.RowDefinitions%2A>另一行，共四行：

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. 通过将<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>属性设置为三个控件（边框、ListBox 和 Button）中每个控件中的 1，将控件移动到第二列。

4. 将每个控件向下移动一行，将<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>三个控件（边框、ListBox 和 Button）和"边框"元素的值分别增加 1。

   三个控件的 XAML 现在如下所示：

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. 通过将以下<xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>XAML 添加到 和`<Grid>``</Grid>`标记之间的任意位置，将属性设置为*水印.png*图像文件：

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. 在元素<xref:System.Windows.Controls.Border>之前，添加包含<xref:System.Windows.Controls.Label>内容"查看支出报表"的 。 此标签是页面的标题。

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. 生成并运行应用程序。

下图显示了您刚刚添加的内容的结果：

![费用它示例屏幕截图，显示新的图像背景和页面标题](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>添加代码以处理事件

1. 在*`ExpenseItHome.xaml`* 中，<xref:System.Windows.Controls.Primitives.ButtonBase.Click>向<xref:System.Windows.Controls.Button>元素添加事件处理程序。 有关详细信息，请参阅[操作：创建一个简单的事件处理程序](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))。

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. 打开*`ExpenseItHome.xaml.vb`* 或*`ExpenseItHome.xaml.cs`*。

3. 将以下代码添加到类以`ExpenseItHome`添加按钮单击事件处理程序。 事件处理程序将打开 **"支出报告页"** 页。

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>为支出报表页创建 UI

*支出报告Page.xaml*显示**`ExpenseItHome`** 页面上所选人员的费用报表。 在本节中，您将为**支出报表页**创建 UI。 您还将向各种 UI 元素添加背景和填充颜色。

1. 打开*费用报告页.xaml*。

2. 在<xref:System.Windows.Controls.Grid>标记之间添加以下 XAML：

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    此 UI 与*`ExpenseItHome.xaml`* 类似，但报表数据显示在 中<xref:System.Windows.Controls.DataGrid>。

3. 生成并运行应用程序。

4. 选择 **"查看**"按钮。

    出现费用报告页。 另请注意，后退导航按钮已启用。

下图显示了添加到*支出报表Page.xaml*的 UI 元素。

![支出它示例屏幕截图，显示刚刚为支出报告页创建的 UI。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>样式控件

对于 UI 中相同类型的所有元素，各种元素的外观通常相同。 UI 使用[样式](../controls/styling-and-templating.md)使外观可跨多个元素重用。 样式的可重用性有助于简化 XAML 的创建和管理。 本部分替换在以前步骤中通过样式定义的按元素划分的属性。

1. 打开*应用程序.xaml*或*App.xaml*。

2. 在<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>标记之间添加以下 XAML：

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    此 XAML 将添加以下样式：

    - `headerTextStyle`：可设置页标题 <xref:System.Windows.Controls.Label>的格式。

    - `labelStyle`：可设置 <xref:System.Windows.Controls.Label> 控件的格式。

    - `columnHeaderStyle`：可设置 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>的格式。

    - `listHeaderStyle`：可设置列表标头 <xref:System.Windows.Controls.Border> 控件的格式。

    - `listHeaderTextStyle`：格式化列表标头<xref:System.Windows.Controls.Label>。

    - `buttonStyle`：格式化<xref:System.Windows.Controls.Button>on `ExpenseItHome.xaml`。

    请注意，样式是属性元素的资源和子元素<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>。 在此位置中，这些样式将应用到应用程序中的所有元素。 有关在 .NET 应用中使用资源的示例，请参阅[使用应用程序资源](../advanced/how-to-use-application-resources.md)。

3. 在*`ExpenseItHome.xaml`* 中，将<xref:System.Windows.Controls.Grid>元素之间的所有内容替换为以下 XAML：

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    应用样式会删除和替换定义每个控件外观的属性（如 <xref:System.Windows.VerticalAlignment> 和 <xref:System.Windows.Media.FontFamily> 。 例如，`headerTextStyle`应用于"查看费用报表"。 <xref:System.Windows.Controls.Label>

4. 打开*费用报告页.xaml*。

5. 将<xref:System.Windows.Controls.Grid>元素之间的所有内容替换为以下 XAML：

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    此 XAML 向<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Border>元素添加样式。

6. 生成并运行应用程序。 窗口外观与以前相同。

    ![支出它示例屏幕截图的外观与上一节相同。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. 关闭应用程序以返回到可视化工作室。

## <a name="bind-data-to-a-control"></a>将数据绑定到控件

在本节中，您将创建绑定到各种控件的 XML 数据。

1. 在*`ExpenseItHome.xaml`* 打开<xref:System.Windows.Controls.Grid>元素之后，添加以下 XAML 以创建包含每个人<xref:System.Windows.Data.XmlDataProvider>数据的 a：

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    数据作为<xref:System.Windows.Controls.Grid>资源创建。 通常，此数据将作为文件加载，但为了简单起见，数据将内联添加。

2. 在`<Grid.Resources>`元素中，添加以下`<xref:System.Windows.DataTemplate>`元素，该元素定义如何在<xref:System.Windows.Controls.ListBox>`<XmlDataProvider>`元素之后在 中显示数据：

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    有关数据模板的详细信息，请参阅[数据模板概述](../data/data-templating-overview.md)。

3. 将现有<xref:System.Windows.Controls.ListBox>替换为以下 XAML：

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    此 XAML 将<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的属性<xref:System.Windows.Controls.ListBox>绑定到数据源，并将数据模板应用为 。 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>

## <a name="connect-data-to-controls"></a>将数据连接到控件

接下来，您将添加代码来检索**`ExpenseItHome`** 页面上选择的名称，并将其传递给**费用报表页的**构造函数。 **支出报告页**将其数据上下文与传递的项设置，这是*支出报告页.xaml*中定义的控件绑定到的。

1. 打开*费用报告页.xaml.vb*或*ExpenseReportPage.xaml.cs*。

2. 添加获取对象的构造函数，以便传递所选人员的费用报表数据。

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. 打开*`ExpenseItHome.xaml.vb`* 或*`ExpenseItHome.xaml.cs`*。

4. 更改<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序以调用新的构造函数，传递所选人员的费用报表数据。

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>使用数据模板对数据进行样式设置数据

在本节中，您将使用数据绑定列表中的每个项目更新 UI。

1. 打开*费用报告页.xaml*。

2. 将"名称"和"部门"<xref:System.Windows.Controls.Label>元素的内容绑定到相应的数据源属性。 有关数据绑定的详细信息，请参阅[数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)。

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. 在打开<xref:System.Windows.Controls.Grid>元素之后，添加以下数据模板，这些模板定义如何显示支出报表数据：

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. 将<xref:System.Windows.Controls.DataGridTextColumn>元素替换为元素<xref:System.Windows.Controls.DataGridTemplateColumn>，<xref:System.Windows.Controls.DataGrid>并将模板应用于它们。

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. 生成并运行应用程序。

6. 选择人员，然后选择 **"查看**"按钮。

下图显示了应用控件、布局、样式`ExpenseIt`、数据绑定和数据模板的应用程序两页：

![显示名称列表和支出报表的应用两个页面。](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> 此示例演示了 WPF 的特定功能，并且不遵循安全、本地化和可访问性等所有最佳实践。 有关 WPF 和 .NET 应用开发最佳实践的全面覆盖，请参阅以下主题：
>
> - [辅助功能](../../ui-automation/accessibility-best-practices.md)
> - [安全性](../security-wpf.md)
> - [WPF 全球化和本地化](../advanced/wpf-globalization-and-localization-overview.md)
> - [WPF 性能](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>后续步骤

在本演练中，您学习了使用 Windows 演示文稿基础 （WPF） 创建 UI 的多种技术。 现在，您应该对数据绑定 .NET 应用的构建基块有基本的了解。 有关 WPF 体系结构和编程模型的详细信息，请参阅以下主题：

- [WPF 架构](../advanced/wpf-architecture.md)
- [XAML 概述 （WPF）](../advanced/xaml-overview-wpf.md)
- [依赖项属性概述](../advanced/dependency-properties-overview.md)
- [布局](../advanced/layout.md)

有关创建应用程序的详细信息，请参阅以下主题：

- [应用程序开发](../app-development/index.md)
- [控件](../controls/index.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [图形和多媒体](../graphics-multimedia/index.md)
- [WPF 中的文档](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>请参阅

- [面板概述](../controls/panels-overview.md)
- [数据模板概述](../data/data-templating-overview.md)
- [构建 WPF 应用程序](../app-development/building-a-wpf-application-wpf.md)
- [样式和模板](../controls/styles-and-templates.md)
