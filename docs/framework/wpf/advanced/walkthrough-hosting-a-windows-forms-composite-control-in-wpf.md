---
title: "演练：在 WPF 中承载 Windows 窗体复合控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f9fc708d3fff3dfca29f46da8d345aeb243df38c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>演练：在 WPF 中承载 Windows 窗体复合控件
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供了用于创建应用程序的丰富环境。 但是，当你有大量的投资[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]它可以更有效地至少重用的代码中，在该代码的一部分你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序而不是从头开始重新编写。 最常见的方案是在你有现成[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]控件。 在某些情况下，你甚至可能无法使用这些控件的源代码。 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]提供一个简单的过程，此类中的控件承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。 例如，你可以使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]大部分你编程，同时承载专用<xref:System.Windows.Forms.DataGridView>控件。  
  
 本演练将引导你通过应用程序承载[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]复合控件，可执行中的数据输入[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。 复合控件打包在一个 DLL 中。 此常规步骤可扩展到更复杂的应用程序和控件。 本演练可在外观和功能几乎完全相同[演练： 承载 Windows 窗体中的 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)。 主要区别在于承载方案是相反的。  
  
 本演练分为两个部分。 第一个部分简要介绍的实现[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]复合控件。 第二个部分详细讨论如何托管中的复合控件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序，从该控件，接收事件，以及访问某些控件的属性。  
  
 本演练涉及以下任务：  
  
-   实现 Windows 窗体复合控件。  
  
-   实现 WPF 主机应用程序。  
  
 本演练的任务的完整代码清单，请参阅[承载 Windows 窗体复合控件在 WPF 示例](http://go.microsoft.com/fwlink/?LinkID=159999)。  
  
## <a name="prerequisites"></a>先决条件  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]。  
  
## <a name="implementing-the-windows-forms-composite-control"></a>实现 Windows 窗体复合控件  
 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]此示例中使用的复合控件是一个简单的数据输入窗体。 此窗体需要用户名和地址，然后使用自定义事件将该信息返回到主机。 下图显示呈现的控件。  
  
 ![简单的 Windows 窗体控件](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")  
Windows 窗体复合控件  
  
### <a name="creating-the-project"></a>创建项目  
 启动项目：  
  
1.  启动[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]，并打开**新项目**对话框。  
  
2.  在窗口类别中，选择**Windows 窗体控件库**模板。  
  
3.  将新项目命名为 `MyControls`。  
  
4.  对于位置，指定将方便地命名的顶级文件夹，如`WpfHostingWindowsFormsControl`。 随后，将主机应用程序放在此文件夹中。  
  
5.  单击**确定**以创建该项目。 默认项目包含一个名为的单个控件`UserControl1`。  
  
6.  在解决方案资源管理器，重命名`UserControl1`到`MyControl1`。  
  
 项目应具有对以下系统 DLL 的引用。 如果默认不包含其中任何 DLL，则将它们添加到项目中。  
  
-   系统  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### <a name="adding-controls-to-the-form"></a>将控件添加到窗体  
 向窗体添加控件：  
  
-   打开`MyControl1`设计器中。  
  
 添加五个<xref:System.Windows.Forms.Label>控件和及其相应<xref:System.Windows.Forms.TextBox>控件、 大小和与上图中，在窗体上排列。 在示例中，<xref:System.Windows.Forms.TextBox>控件命名为：  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 添加两个<xref:System.Windows.Forms.Button>进行标记的控件**确定**和**取消**。 在本示例中，按钮名称就是`btnOK`和`btnCancel`分别。  
  
### <a name="implementing-the-supporting-code"></a>实现支持代码  
 在代码视图中打开窗体。 控件通过引发自定义，将收集的数据返回其主机`OnButtonClick`事件。 数据包含在事件自变量对象中。 以下代码演示事件和委托声明。  
  
 向 `MyControl1` 类添加下面的代码。  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 `MyControlEventArgs`类包含要返回到主机的信息。  
  
 将以下类添加到窗体中。  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 当用户单击**确定**或**取消**按钮，<xref:System.Windows.Forms.Control.Click>事件处理程序创建`MyControlEventArgs`包含数据的对象，并引发`OnButtonClick`事件。 两个处理程序之间的唯一区别是事件自变量的`IsOK`属性。 此属性使主机可以确定单击的按钮。 设置为`true`为**确定**按钮，和`false`为**取消**按钮。 以下代码演示两个按钮处理程序。  
  
 向 `MyControl1` 类添加下面的代码。  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>赋予程序集强名称并生成程序集  
 此程序集引用的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序中，它必须具有强名称。 若要创建强名称，请使用 Sn.exe 创建密钥文件，并将其添加到你的项目。  
  
1.  打开一个 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 命令提示符。 若要执行此操作，请单击**启动**菜单，然后再选择**所有 Programs/Microsoft Visual Studio 2010/Visual Studio 工具/Visual Studio 命令提示符**。 这将启动包含自定义环境变量的控制台窗口。  
  
2.  在命令提示符下，使用`cd`命令可以转到你的项目文件夹。  
  
3.  通过运行以下命令生成名为 MyControls.snk 的密钥文件。  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  若要在你的项目中包含的密钥文件，右键单击解决方案资源管理器中的项目名称，然后单击**属性**。 在项目设计器中，单击**签名**选项卡上，选择**对程序集签名**复选框，然后浏览到你的密钥文件。  
  
5.  生成解决方案。 生成将产生一个名为 MyControls.dll 的 DLL。  
  
## <a name="implementing-the-wpf-host-application"></a>实现 WPF 主机应用程序  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]宿主应用程序使用<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件来承载`MyControl1`。 该应用程序处理`OnButtonClick`事件，以接收来自控件的数据。 它还具有的选项按钮，您可以更改某些控件的属性的集合[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。 下图显示已完成的应用程序。  
  
 ![控件嵌入在 WPF 页中](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")  
显示嵌入在 WPF 应用程序中的控件的完整应用程序  
  
### <a name="creating-the-project"></a>创建项目  
 启动项目：  
  
1.  打开[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]，然后选择**新项目**。  
  
2.  在窗口类别中，选择**WPF 应用程序**模板。
  
3.  将新项目命名为 `WpfHost`。  
  
4.  对于位置，指定包含 MyControls 项目的同一顶层文件夹。  
  
5.  单击**确定**以创建该项目。  
  
 你还需要将引用添加到包含 DLL`MyControl1`和其他程序集。  
  
1.  右键单击解决方案资源管理器中的项目名称并选择**添加引用**。  
  
2.  单击**浏览**选项卡，然后浏览到包含 MyControls.dll 的文件夹。 在本演练中，此文件夹位于 MyControls\bin\Debug。  
  
3.  选择 MyControls.dll，，然后单击**确定**。  
  
4.  添加到名为 WindowsFormsIntegration.dll 的 WindowsFormsIntegration 程序集的引用。  
  
### <a name="implementing-the-basic-layout"></a>实现基本布局  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] MainWindow.xaml 的主机应用程序实现。 此文件包含[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]标记，定义布局，并承载[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]控件。 该应用程序分为三个区域：  
  
-   **控件属性**面板中，其中包含一套可用于修改所承载控件的各种属性的选项按钮。  
  
-   **数据从控件**面板中，其中包含几个<xref:System.Windows.Controls.TextBlock>显示数据的元素返回从所承载的控件。  
  
-   所承载控件本身。  
  
 基本布局如下面的 XAML 中所示。 需要的标记到主机`MyControl1`省略在此示例中，但稍后将作介绍。  
  
 将 MainWindow.xaml 中的 XAML 替换为以下内容。 如果你使用的 Visual Basic，更改到类`x:Class="MainWindow"`。  
  
 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 第一个<xref:System.Windows.Controls.StackPanel>元素包含多个的集<xref:System.Windows.Controls.RadioButton>使你能够修改各种托管控件的默认属性的控件。 后跟<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素，哪些主机`MyControl1`。 最后一个<xref:System.Windows.Controls.StackPanel>元素包含若干<xref:System.Windows.Controls.TextBlock>显示由托管控件的数据的元素。 元素的顺序和<xref:System.Windows.Controls.DockPanel.Dock%2A>和<xref:System.Windows.FrameworkElement.Height%2A>特性设置没有缺口或扭曲的嵌入到窗口托管的控件。  
  
#### <a name="hosting-the-control"></a>承载控件  
 上面的 XAML 的以下编辑的版本侧重于所需的元素到主机`MyControl1`。  
  
 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 `xmlns`命名空间映射特性创建的引用`MyControls`包含托管的控件的命名空间。 此映射可用于表示`MyControl1`中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]作为`<mcl:MyControl1>`。  
  
 XAML 中的两个元素处理承载：  
  
-   `WindowsFormsHost`表示<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素，使你向主机[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]中控制[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序。  
  
-   `mcl:MyControl1`它表示`MyControl1`，添加到<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的子集合。 因此，这[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]作为的一部分时呈现控件[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]窗口中，并且你可以与该控件从应用程序进行通信。  
  
### <a name="implementing-the-code-behind-file"></a>实现代码隐藏文件  
 代码隐藏文件，MainWindow.xaml.vb 或 MainWindow.xaml.cs，包含实现的功能与过程性代码[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]前面部分所述。 主要任务有：  
  
-   附加到事件处理程序`MyControl1`的`OnButtonClick`事件。  
  
-   修改的各种属性`MyControl1`，将根据如何设置的选项按钮的集合。  
  
-   显示控件收集的数据。  
  
#### <a name="initializing-the-application"></a>初始化应用程序  
 中的事件处理程序窗口的包含初始化代码<xref:System.Windows.FrameworkElement.Loaded>事件，并将事件处理程序附加到控件的`OnButtonClick`事件。  
  
 在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，添加以下代码到`MainWindow`类。  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 因为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]讨论以前添加`MyControl1`到<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的子元素集合，可以强制转换<xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的<xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A>获取对引用`MyControl1`。 然后可以使用该引用附加到事件处理程序`OnButtonClick`。  
  
 除了提供对控件本身的引用<xref:System.Windows.Forms.Integration.WindowsFormsHost>公开多个控件的属性，可以从应用程序操作。 初始化代码将这些值分配给私有全局变量，以供稍后在应用程序中使用。  
  
 以便你可以轻松地访问中的类型`MyControls`DLL，添加以下`Imports`或`using`到文件顶部的语句。  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### <a name="handling-the-onbuttonclick-event"></a>处理 OnButtonClick 事件  
 `MyControl1`引发`OnButtonClick`事件在用户单击控件的按钮之一时。  
  
 向 `MainWindow` 类添加下面的代码。  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 中的文本框中的数据打包到`MyControlEventArgs`对象。 如果用户单击**确定**按钮，事件处理程序中提取数据并在下方的面板中显示它`MyControl1`。  
  
#### <a name="modifying-the-controls-properties"></a>修改控件属性  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>元素公开多个托管的控件的默认属性。 因此，可以更改空间外观，以更贴合应用程序的样式。 位于左侧面板中的选项按钮组使用户能够修改多个颜色和字体属性。 按钮的每个集具有的处理程序<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件，也不能检测到用户的选项按钮选择更改在控件上的相应属性。  
  
 向 `MainWindow` 类添加下面的代码。  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 生成并运行应用程序。 Windows 窗体复合控件中添加一些文本，然后单击**确定**。 文本将显示在标签中。 单击不同的单选按钮查看在控件上的效果。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 设计器](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [演练：在 WPF 中承载 Windows 窗体控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [演练：在 Windows 窗体中承载 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
