---
title: "演练：绑定到混合应用程序中的数据"
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
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1348f3a57dd04d58298c9746b74a7c3a1baf30c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>演练：绑定到混合应用程序中的数据
将数据源绑定到控件而言至关重要向用户提供访问基础数据，无论使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]或[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 本演练演示如何同时包含这两者的混合应用程序中使用数据绑定[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]和[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件。  
  
 本演练涉及以下任务：  
  
-   创建项目。  
  
-   定义数据模板。  
  
-   指定窗体布局。  
  
-   指定数据绑定。  
  
-   使用互操作功能显示数据。  
  
-   向项目添加数据源。  
  
-   绑定到数据源。  
  
 本演练的任务的完整代码清单，请参阅[混合应用程序示例中的数据绑定](http://go.microsoft.com/fwlink/?LinkID=159983)。  
  
 完成本演练后，你将对混合应用程序中的数据绑定功能有所了解。  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]。  
  
-   包含到 Northwind 示例数据库运行在 Microsoft SQL Server 上的访问。  
  
## <a name="creating-the-project"></a>创建项目  
  
#### <a name="to-create-and-set-up-the-project"></a>创建并设置项目  
  
1.  创建一个名为的 WPF 应用程序项目`WPFWithWFAndDatabinding`。  
  
2.  在解决方案资源管理器中，添加对下列程序集的引用。  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  打开在 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。  
  
4.  在<xref:System.Windows.Window>元素中，添加以下[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]命名空间映射。  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  将默认值<xref:System.Windows.Controls.Grid>元素`mainGrid`通过分配<xref:System.Windows.FrameworkElement.Name%2A>属性。  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a>定义数据模板  
 中显示的客户的主列表<xref:System.Windows.Controls.ListBox>控件。 下面的代码示例定义<xref:System.Windows.DataTemplate>对象名为`ListItemsTemplate`控制的可视化树<xref:System.Windows.Controls.ListBox>控件。 这<xref:System.Windows.DataTemplate>分配给<xref:System.Windows.Controls.ListBox>控件的<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>属性。  
  
#### <a name="to-define-the-data-template"></a>定义数据模板  
  
-   将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a>指定窗体布局  
 窗体的布局由一个三行三列的网格来定义。 <xref:System.Windows.Controls.Label>控件可用于标识客户表中的每个列。  
  
#### <a name="to-set-up-the-grid-layout"></a>设置网格布局  
  
-   将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a>设置 Label 控件  
  
-   将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a>指定数据绑定  
 中显示的客户的主列表<xref:System.Windows.Controls.ListBox>控件。 附加`ListItemsTemplate`将绑定<xref:System.Windows.Controls.TextBlock>控制转移到`ContactName`从数据库字段。  
  
 每个客户记录的详细信息显示在多个<xref:System.Windows.Controls.TextBox>控件。  
  
#### <a name="to-specify-data-bindings"></a>指定数据绑定  
  
-   将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。  
  
     <xref:System.Windows.Data.Binding>类绑定<xref:System.Windows.Controls.TextBox>到数据库中的相应字段的控件。  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a>使用互操作功能显示数据  
 对应于所选客户的订单显示在<xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType>控件名为`dataGridView1`。 `dataGridView1`控件绑定到数据源中的代码隐藏文件。 A<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件是此父[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件。  
  
#### <a name="to-display-data-in-the-datagridview-control"></a>在 DataGridView 控件中显示数据  
  
-   将复制到下面的 XAML<xref:System.Windows.Controls.Grid>元素的声明。  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a>向项目添加数据源  
 与[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]，你可以轻松添加到你的项目的数据源。 此过程将向项目添加强类型数据集。 还添加了其他支持类，例如每个所选表适用的表适配器。  
  
#### <a name="to-add-the-data-source"></a>添加数据源  
  
1.  从**数据**菜单上，选择**添加新数据源**。  
  
2.  在**数据源配置向导**，通过使用数据集创建到 Northwind 数据库的连接。 有关详细信息，请参阅[如何： 连接到数据库中的数据](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)。  
  
3.  在提示你时通过**数据源配置向导**，保存连接字符串作为`NorthwindConnectionString`。  
  
4.  当系统提示你选择数据库对象时，选择`Customers`和`Orders`表和名称生成的数据集`NorthwindDataSet`。  
  
## <a name="binding-to-the-data-source"></a>绑定到数据源  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>组件提供统一的接口，用于应用程序的数据源。 绑定到数据源是在代码隐藏文件中实现的。  
  
#### <a name="to-bind-to-the-data-source"></a>绑定到数据源  
  
1.  打开名为 MainWindow.xaml.vb 或 MainWindow.xaml.cs 的代码隐藏文件。  
  
2.  下面的代码复制到`MainWindow`类定义。  
  
     此代码声明<xref:System.Windows.Forms.BindingSource>组件和连接到数据库的关联的帮助程序类。  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  将以下代码复制到构造函数中。  
  
     此代码创建并初始化<xref:System.Windows.Forms.BindingSource>组件。  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  打开 MainWindow.xaml。  
  
5.  在设计视图或 XAML 视图中，选择<xref:System.Windows.Window>元素。  
  
6.  在属性窗口中，单击**事件**选项卡。  
  
7.  双击<xref:System.Windows.FrameworkElement.Loaded>事件。  
  
8.  下面的代码复制到<xref:System.Windows.FrameworkElement.Loaded>事件处理程序。  
  
     此代码将分配<xref:System.Windows.Forms.BindingSource>组件作为数据上下文，并填充`Customers`和`Orders`适配器对象。  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. 下面的代码复制到`MainWindow`类定义。  
  
     此方法可处理<xref:System.Windows.Data.CollectionView.CurrentChanged>事件并更新数据绑定的当前项。  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. 按 F5 生成并运行该应用程序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [混合应用程序示例中的数据绑定](http://go.microsoft.com/fwlink/?LinkID=159983)  
 [演练：在 WPF 中托管 Windows 窗体复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [演练：在 Windows 窗体中承载 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
