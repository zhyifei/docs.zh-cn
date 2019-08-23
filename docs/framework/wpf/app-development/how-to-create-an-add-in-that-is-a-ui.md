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
ms.openlocfilehash: fa30b7860bd8afdb68b0b54cd8d40f3e1ec86077
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949135"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>如何：创建作为 UI 的外接程序
此示例演示如何创建一个外接程序, 该外接程序是由 WPF 独立应用程序承载的 Windows Presentation Foundation (WPF)。  
  
 外接程序是一个用户界面, 它是一个 WPF 用户控件。 用户控件的内容是单个按钮，单击时会显示消息框。 WPF 独立应用程序承载外接程序 UI 作为主应用程序窗口的内容。  
  
 **系统必备**  
  
 此示例突出显示了支持此方案的 .NET Framework 外接程序模型的 WPF 扩展, 并假设以下内容:  
  
- .NET Framework 外接程序模型 (包括管道、外接程序和主机开发) 的知识。 如果不熟悉这些概念, 请参阅[外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。 有关演示管道、外接程序和主机应用程序实现的教程, 请参阅[演练:创建可扩展应用程序](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))。  
  
- 了解 .NET Framework 外接程序模型的 WPF 扩展。 请参阅[WPF 外接程序概述](wpf-add-ins-overview.md)。  
  
## <a name="example"></a>示例  
 若要创建作为 WPF UI 的外接程序, 需要每个管道段、外接程序和宿主应用程序的特定代码。  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>实现协定管道段

当外接程序是 UI 时, 外接程序的协定必须实现<xref:System.AddIn.Contract.INativeHandleContract>。 在此示例中`IWPFAddInContract` , <xref:System.AddIn.Contract.INativeHandleContract>实现, 如以下代码所示。  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>实现外接程序视图管道段

由于外接程序作为<xref:System.Windows.FrameworkElement>类型的子类实现, 外接程序视图还必须是子类。 <xref:System.Windows.FrameworkElement> 下面的代码演示作为`WPFAddInView`类实现的协定的外接程序视图。  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
此处, 外接程序视图派生自<xref:System.Windows.Controls.UserControl>。 因此, 外接程序 UI 还应派生自<xref:System.Windows.Controls.UserControl>。  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>实现外接程序端适配器管道段

当协定为<xref:System.AddIn.Contract.INativeHandleContract>时, 外接程序<xref:System.Windows.FrameworkElement>是 (由外接程序视图管道段指定)。 因此, <xref:System.Windows.FrameworkElement>必须<xref:System.AddIn.Contract.INativeHandleContract>先将转换为, 然后才能跨越隔离边界。 此工作由外接程序端适配器通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>执行, 如以下代码所示。  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

在加载项返回 ui 的外接程序模型中 (请参阅[创建返回 ui 的外](how-to-create-an-add-in-that-returns-a-ui.md)接程序), 外接程序适配器<xref:System.Windows.FrameworkElement> <xref:System.AddIn.Contract.INativeHandleContract>通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>将转换为。 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>还必须在此模型中调用, 不过, 您需要实现一个方法, 通过该方法可以编写代码来调用它。 为此, 可以重<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>写和实现调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>的代码 (如果调用<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>的代码应为)。 <xref:System.AddIn.Contract.INativeHandleContract> 在此情况下，调用方将为主机端适配器，这在后续子节中有所介绍。  
  
> [!NOTE]
> 还需要在此模型<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>中重写, 以便在宿主应用程序 ui 和外接程序 ui 之间启用 tab 键切换。 有关详细信息, 请参阅[Wpf 外接程序概述](wpf-add-ins-overview.md)中的 "wpf 外接程序限制"。  
  
由于外接程序端适配器实现了一个派生自<xref:System.AddIn.Contract.INativeHandleContract>的接口, 因此您还需要实现<xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, 但在重写时<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> , 将忽略此情况。  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>实现主机视图管道段

在此模型中, 主机应用程序通常要求主机视图<xref:System.Windows.FrameworkElement>为子类。 宿主端适配器必须在<xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Contract.INativeHandleContract>跨越隔离边界<xref:System.Windows.FrameworkElement>之后将转换为。 由于宿主应用程序未调用方法来获取<xref:System.Windows.FrameworkElement>, 因此宿主视图必须<xref:System.Windows.FrameworkElement>通过包含它来 "返回"。 因此, 宿主视图必须派生自可包含其他 ui <xref:System.Windows.FrameworkElement>的子类, <xref:System.Windows.Controls.UserControl>如。 下面的代码演示作为`WPFAddInHostView`类实现的协定的主机视图。  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>实现主机端适配器管道段

当协定是<xref:System.AddIn.Contract.INativeHandleContract>时, 主机应用程序<xref:System.Windows.Controls.UserControl>需要 (由主机视图指定)。 因此, <xref:System.AddIn.Contract.INativeHandleContract>在将设置为主机视图<xref:System.Windows.FrameworkElement> (派生自<xref:System.Windows.Controls.UserControl>) 的内容之前, 必须在越过隔离边界之后转换为。  
  
这一工作由主机端适配器执行，如以下代码所示。  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

如您所见, 主机端适配器<xref:System.AddIn.Contract.INativeHandleContract>通过调用外接程序端适配器的<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>方法 (这<xref:System.AddIn.Contract.INativeHandleContract>是跨越隔离边界的点) 来获取。  
  
然后, 宿主端适配器<xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement>通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>将转换为。 最后, <xref:System.Windows.FrameworkElement>将设置为宿主视图的内容。  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>实现外接程序

外接程序端适配器和外接程序视图就位后，外接程序就可以通过派生自外接程序视图来实现，如以下代码所示。  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

在此示例中, 你可以看到此模型的一个有趣的优点: 外接程序开发人员只需实现外接程序 (因为它也是 UI), 而不是同时实现外接程序类和外接程序用户界面。  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>实现主机应用程序

创建主机端适配器和主机视图后, 宿主应用程序可以使用 .NET Framework 外接程序模型打开管道并获取外接程序的宿主视图。 这些步骤在以下代码中显示。  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

宿主应用程序使用典型 .NET Framework 外接程序模型代码激活外接程序, 该外接程序将宿主视图隐式返回到主机应用程序。 宿主应用程序随后会<xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Grid>从中显示宿主视图 (即)。  
  
 用于处理与外接程序 UI 交互的代码在外接程序的应用程序域中运行。 这些交互包括以下内容：  
  
- <xref:System.Windows.Controls.Button> 处理<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。  
  
- <xref:System.Windows.MessageBox>显示。  
  
 此活动完全独立于主机应用程序。  
  
## <a name="see-also"></a>请参阅

- [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [WPF 外接程序概述](wpf-add-ins-overview.md)
