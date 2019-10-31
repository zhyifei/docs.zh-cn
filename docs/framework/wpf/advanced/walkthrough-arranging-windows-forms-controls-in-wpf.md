---
title: 演练：在 WPF 中排列 Windows 窗体控件
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 484895db539b288bf388ff6c2ce3c29db55080b1
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197840"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>演练：在 WPF 中排列 Windows 窗体控件

本演练演示如何使用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 布局功能在混合应用程序中排列 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。

本演练涉及以下任务：

- 创建项目。
- 使用默认布局设置。
- 根据内容调整大小。
- 使用绝对定位。
- 显式指定大小。
- 设置布局属性。
- 了解 Z 顺序限制。
- 停靠。
- 设置可见性。
- 承载不拉伸的控件。
- 缩放。
- 旋转。
- 设置填充和边距。
- 使用动态布局容器。

有关本演练中所述任务的完整代码列表，请参阅[在 WPF 中排列 Windows 窗体控件示例](https://go.microsoft.com/fwlink/?LinkID=159971)。

完成后，你将了解基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 布局功能。

## <a name="prerequisites"></a>Prerequisites

若要完成本演练，必须具有 Visual Studio。

## <a name="creating-the-project"></a>创建项目

若要创建和设置项目，请执行以下步骤：

1. 创建一个名为 `WpfLayoutHostingWf`的 WPF 应用程序项目。

2. 在解决方案资源管理器中，添加对以下程序集的引用：

    - WindowsFormsIntegration
    - System.Windows.Forms
    - System.Drawing

3. 双击 " *mainwindow.xaml* " 以在 xaml 视图中打开它。

4. 在 <xref:System.Windows.Window> 元素中，添加以下 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 命名空间映射。

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. 在 <xref:System.Windows.Controls.Grid> 元素中，将 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 属性设置为 `true`，并定义五行和三列。

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a>使用默认布局设置

默认情况下，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素处理承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的布局。

若要使用默认布局设置，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> 控件将出现在 <xref:System.Windows.Controls.Canvas>中。 承载的控件根据其内容调整大小，并调整 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的大小以适应所承载的控件。

## <a name="sizing-to-content"></a>按内容调整大小

<xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素确保所承载的控件的大小调整为正确显示其内容。

若要调整内容的大小，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 这两个新按钮控件的大小调整为正确显示较长的文本字符串和更大的字号，并调整 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的大小以容纳所承载的控件。

## <a name="using-absolute-positioning"></a>使用绝对定位

可以使用绝对定位将 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素放在用户界面（UI）中的任意位置。

若要使用绝对定位，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素位于网格单元顶部20个像素的位置，左侧20个像素。

## <a name="specifying-size-explicitly"></a>显式指定大小

您可以使用 <xref:System.Windows.FrameworkElement.Width%2A> 和 <xref:System.Windows.FrameworkElement.Height%2A> 属性指定 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的大小。

若要显式指定大小，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的大小设置为50像素宽 x 70 像素高，小于默认布局设置。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件的内容会相应地重新排列。

## <a name="setting-layout-properties"></a>设置布局属性

始终使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的属性设置寄宿控件上与布局相关的属性。 直接对承载控件设置布局属性会产生意外结果。

 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的托管控件上设置与布局相关的属性不起作用。

若要查看在承载控件上设置属性的效果，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. 在**解决方案资源管理器**中，双击 " *mainwindow.xaml* " 或 " *MainWindow.xaml.cs* " 以在代码编辑器中将其打开。

3. 将以下代码复制到 `MainWindow` 类定义：

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. 按 F5 生成并运行该应用程序<kbd></kbd>。

5. 单击 "**单击**此按钮"。 `button1_Click` 事件处理程序在承载的控件上设置 <xref:System.Windows.Forms.Control.Top%2A> 和 <xref:System.Windows.Forms.Control.Left%2A> 属性。 这会导致在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素内重新定位寄宿的控件。 宿主保持相同的屏幕区域，但承载控件被剪裁。 托管控件应始终填充 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素。

## <a name="understanding-z-order-limitations"></a>了解 Z 顺序限制

可见 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素始终在其他 WPF 元素之上绘制，它们不受 z 顺序的影响。 若要查看此 z 顺序行为，请执行以下操作：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素绘制在 label 元素上。

## <a name="docking"></a>停靠

<xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素支持 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 停靠。 设置 <xref:System.Windows.Controls.DockPanel.Dock%2A> 附加属性以将承载的控件停靠在 <xref:System.Windows.Controls.DockPanel> 元素中。

若要停靠托管控件，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素停靠在 <xref:System.Windows.Controls.DockPanel> 元素的右侧。

## <a name="setting-visibility"></a>设置可见性

可以通过在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素上设置 <xref:System.Windows.UIElement.Visibility%2A> 属性使 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件不可见或折叠。 当控件不可见时，控件不会显示，但会占据布局空间。 当控件处于折叠状态时，控件不会显示，也不会占据布局空间。

若要设置寄宿的控件的可见性，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. 在*mainwindow.xaml*或*MainWindow.xaml.cs*中，将以下代码复制到类定义中：

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. 按 F5 生成并运行该应用程序<kbd></kbd>。

4. 单击 "**单击以使不可见**" 按钮，使 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素不可见。

5. 单击 "**单击以折叠**" 按钮可完全隐藏布局中的 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素。 折叠 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件时，会重新排列周围的元素以占用其空间。

## <a name="hosting-a-control-that-does-not-stretch"></a>承载不拉伸的控件

某些 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件具有固定大小，且不会拉伸以填充布局中的可用空间。 例如，<xref:System.Windows.Forms.MonthCalendar> 控件在一个固定空间内显示月份。

若要承载不拉伸的控件，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素在网格行的中心，但不会拉伸以填充可用空间。 如果窗口足够大，则可能会看到宿主 <xref:System.Windows.Forms.MonthCalendar> 控件显示两个或更多月份，但这些月份位于行的中心。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 布局引擎集中元素，这些元素无法调整大小以填充可用空间。

## <a name="scaling"></a>缩放

与 WPF 元素不同，大多数 Windows 窗体控件不是持续缩放的。 若要提供自定义缩放，请重写 <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> 方法。

若要使用默认行为缩放托管控件，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 承载控件及其周围元素按 0.5 的比例进行缩放。 但是，承载控件的字体不缩放。

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>旋转

与 WPF 元素不同，Windows 窗体控件不支持旋转。 应用旋转转换时，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素不随其他 WPF 元素一起旋转。 180度以外的任何旋转值都将引发 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 事件。

若要查看混合应用程序中的旋转效果，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 承载控件不旋转，但是它周围的元素旋转 180 度。 可能必须调整窗口大小才能看到这些元素。

## <a name="setting-padding-and-margins"></a>设置填充和边距

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 布局中的填充和边距类似于 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中的填充和边距。 只需在 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素上设置 <xref:System.Windows.Controls.Control.Padding%2A> 和 <xref:System.Windows.FrameworkElement.Margin%2A> 属性即可。

若要为承载的控件设置填充和边距，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. 按 F5 生成并运行该应用程序<kbd></kbd>。 填充和边距设置将以应用于 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中应用的相同方式应用于承载 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。

## <a name="using-dynamic-layout-containers"></a>使用动态布局容器

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 提供了两个动态布局容器，<xref:System.Windows.Forms.FlowLayoutPanel> 和 <xref:System.Windows.Forms.TableLayoutPanel>。 你还可以在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 布局中使用这些容器。

若要使用动态布局容器，请执行以下步骤：

1. 将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. 在*mainwindow.xaml*或*MainWindow.xaml.cs*中，将以下代码复制到类定义中：

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. 在构造函数中添加对 `InitializeFlowLayoutPanel` 方法的调用：

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. 按 F5 生成并运行该应用程序<kbd></kbd>。 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素填充 <xref:System.Windows.Controls.DockPanel>，<xref:System.Windows.Forms.FlowLayoutPanel> 将其子控件排列在默认的 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>中。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [WindowsFormsHost 元素的布局注意事项](layout-considerations-for-the-windowsformshost-element.md)
- [在 WPF 中排列 Windows 窗体控件示例](https://go.microsoft.com/fwlink/?LinkID=159971)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
