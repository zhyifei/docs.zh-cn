---
title: 如何：创建作为 UI 的外接程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 339231031b9e57b9f00a2aeb6fbbde8ad66c1ad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141024"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>如何：创建作为 UI 的外接程序
此示例演示如何创建由 WPF 独立应用程序托管的 Windows 演示文稿基础 （WPF） 的外接程序。  
  
 外接程序是 WPF 用户控件的 UI。 用户控件的内容是单个按钮，单击时会显示消息框。 WPF 独立应用程序将外接程序 UI 托管为主应用程序窗口的内容。  
  
 **系统必备**  
  
 此示例突出显示启用此方案的 .NET 框架外接程序模型的 WPF 扩展，并假定以下内容：  
  
- 了解 .NET 框架外接程序模型，包括管道、外接程序和主机开发。 如果您不熟悉这些概念，请参阅[加载项和可扩展性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。 有关演示管道、外接程序和主机应用程序的实现的教程，请参阅[演练：创建可扩展应用程序](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))。  
  
- WPF 扩展到 .NET 框架外接程序模型的知识。 请参阅[WPF 加载项概述](wpf-add-ins-overview.md)。  
  
## <a name="example"></a>示例  
 要创建一个附加程序，即 WPF UI 需要每个管道段、外接程序和主机应用程序的特定代码。  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>实现协定管道段

当外接程序是 UI 时，外接程序的协定必须实现<xref:System.AddIn.Contract.INativeHandleContract>。 在此示例中，`IWPFAddInContract`实现<xref:System.AddIn.Contract.INativeHandleContract>， 如以下代码所示。  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>实现外接程序视图管道段

由于外接程序是作为<xref:System.Windows.FrameworkElement>类型的子类实现的，因此外接程序视图还必须子类<xref:System.Windows.FrameworkElement>。 以下代码显示作为`WPFAddInView`类实现的协定的外接程序视图。  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
此处，外接程序视图派生自<xref:System.Windows.Controls.UserControl>。 因此，外接程序 UI 也应派生自<xref:System.Windows.Controls.UserControl>。  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>实现外接程序端适配器管道段

当协定是 时<xref:System.AddIn.Contract.INativeHandleContract>，外接程序是 （<xref:System.Windows.FrameworkElement>由外接程序视图管道段指定）。 因此，在<xref:System.Windows.FrameworkElement>跨越隔离边界之前，<xref:System.AddIn.Contract.INativeHandleContract>必须转换为 。 此工作由外接程序端适配器通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>执行，如以下代码所示。  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

在外接程序返回 UI 的外接程序模型中（请参阅[创建返回 UI 的外接程序](how-to-create-an-add-in-that-returns-a-ui.md)），外接程序适配器<xref:System.Windows.FrameworkElement><xref:System.AddIn.Contract.INativeHandleContract>通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>将 转换为 。 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>还必须在此模型中调用，尽管您需要实现一个方法，从中编写代码来调用它。 通过重写<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>和实现调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>的代码（如果调用<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>的代码是预期 ） <xref:System.AddIn.Contract.INativeHandleContract> 在此情况下，调用方将为主机端适配器，这在后续子节中有所介绍。  
  
> [!NOTE]
> 您还需要在此模型中重写<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>，以便在主机应用程序 UI 和外接程序 UI 之间启用选项卡。 有关详细信息，请参阅[WPF 外接程序概述中的"WPF](wpf-add-ins-overview.md)外接程序限制"。  
  
由于外接程序适配器实现派生自<xref:System.AddIn.Contract.INativeHandleContract>的接口，因此还需要实现<xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>，尽管在重写时<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>将忽略这一点。  
  
<a name="HostViewPipeline"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>实现主机视图管道段

在此模型中，主机应用程序通常希望主机视图是<xref:System.Windows.FrameworkElement>子类。 主机端适配器必须在<xref:System.AddIn.Contract.INativeHandleContract><xref:System.Windows.FrameworkElement><xref:System.AddIn.Contract.INativeHandleContract>跨越隔离边界后将 转换为 。 由于主机应用程序不调用 方法来获取 ，<xref:System.Windows.FrameworkElement>因此主机视图必须通过包含它来"返回"。 <xref:System.Windows.FrameworkElement> 因此，主机视图必须派生自 可以包含其他<xref:System.Windows.FrameworkElement>UI 的子类，如<xref:System.Windows.Controls.UserControl>。 以下代码显示作为类实现的协定的`WPFAddInHostView`主机视图。  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>实现主机端适配器管道段

当协定是 时<xref:System.AddIn.Contract.INativeHandleContract>，主机应用程序需要 （<xref:System.Windows.Controls.UserControl>如主机视图指定）。 因此，<xref:System.AddIn.Contract.INativeHandleContract>在跨越隔离边界之前<xref:System.Windows.FrameworkElement><xref:System.Windows.Controls.UserControl>，必须将 转换为 。  
  
这一工作由主机端适配器执行，如以下代码所示。  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

如您所见，主机端适配器<xref:System.AddIn.Contract.INativeHandleContract>通过调用外接程序端适配器<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>的方法获取 获取 （这是跨越<xref:System.AddIn.Contract.INativeHandleContract>隔离边界的点）。  
  
然后，主机端适配器通过调用<xref:System.AddIn.Contract.INativeHandleContract><xref:System.Windows.FrameworkElement><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>将 转换为 。 最后，<xref:System.Windows.FrameworkElement>将 设置为主机视图的内容。  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>实现外接程序

外接程序端适配器和外接程序视图就位后，外接程序就可以通过派生自外接程序视图来实现，如以下代码所示。  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

在此示例中，您可以看到此模型的一个有趣好处：外接程序开发人员只需要实现外接程序（因为它也是 UI），而不是外接程序类和外接程序 UI。  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>实现主机应用程序

创建主机端适配器和主机视图后，主机应用程序可以使用 .NET 框架外接程序模型打开管道并获取外接程序的主机视图。 这些步骤在以下代码中显示。  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

主机应用程序使用典型的 .NET Framework 外接程序模型代码来激活外接程序，该加载项隐式地将主机视图返回到主机应用程序。 主机应用程序随后显示 中的主机视图 （这是<xref:System.Windows.Controls.UserControl>a ） <xref:System.Windows.Controls.Grid>。  
  
 处理与外接程序 UI 交互的代码在外接程序的应用程序域中运行。 这些交互包括以下内容：  
  
- 处理<xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。  
  
- 显示<xref:System.Windows.MessageBox>。  
  
 此活动完全独立于主机应用程序。  
  
## <a name="see-also"></a>另请参阅

- [外接程序和扩展性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [WPF 外接程序概述](wpf-add-ins-overview.md)
