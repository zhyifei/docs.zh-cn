---
title: 如何：创建作为 UI 的外接程序
ms.date: 03/30/2017
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 4bd03c2f879ecab83306bb68552c044a33f2e6e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549586"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>如何：创建作为 UI 的外接程序
此示例演示如何为 Windows Presentation Foundation (WPF) 由承载的外接程序创建[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]独立的应用程序。  
  
 外接程序是[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]即[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]用户控件。 用户控件的内容是单个按钮，单击时会显示消息框。 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]外接程序的独立应用程序承载[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]用作应用程序主窗口的内容。  
  
 **系统必备**  
  
 此示例重点介绍[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]扩展[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，启用此方案中，假设您具备以下：  
  
-   知识[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，包括管道、 外接程序和主机开发。 如果你不熟悉这些概念，请参阅[外接程序和扩展性](../../../../docs/framework/add-ins/index.md)。 有关演示如何实现管道、 外接程序和主机应用程序的教程，请参阅[演练： 创建可扩展应用程序](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)。  
  
-   知识[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]扩展[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，这可在此处找到： [WPF 外接程序概述](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)。  
  
## <a name="example"></a>示例  
 若要创建是[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]以及每个管道段外, 接程序时，主机应用程序需要特定的代码。  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>实现协定管道段  
 外接程序时[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]外, 接程序的协定必须实现<xref:System.AddIn.Contract.INativeHandleContract>。 在示例中，`IWPFAddInContract`实现<xref:System.AddIn.Contract.INativeHandleContract>，如下面的代码中所示。  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>实现外接程序视图管道段  
 由于外接程序作为的一个子类实现<xref:System.Windows.FrameworkElement>类型外, 接程序视图还必须子类<xref:System.Windows.FrameworkElement>。 下面的代码演示作为实现的协定的外接程序视图`WPFAddInView`类。  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 在这里外, 接程序视图派生自<xref:System.Windows.Controls.UserControl>。 因此外, 接程序[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]还应派生自<xref:System.Windows.Controls.UserControl>。  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>实现外接程序端适配器管道段  
 协定是<xref:System.AddIn.Contract.INativeHandleContract>外, 接程序是<xref:System.Windows.FrameworkElement>（所指定的外接程序视图管道段）。 因此，<xref:System.Windows.FrameworkElement>必须转换为<xref:System.AddIn.Contract.INativeHandleContract>在越过隔离边界之前。 通过调用执行此工作的外接程序端适配器<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>，如下面的代码中所示。  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 在外接程序模型在外接程序返回[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)](请参阅[创建外接程序中，将返回 UI](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)) 外, 接程序适配器转换<xref:System.Windows.FrameworkElement>到<xref:System.AddIn.Contract.INativeHandleContract>通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>。 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 必须还调用在此模型中，尽管你需要实现一种方法从其编写代码以调用它。 执行此操作通过重写<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>和实现调用的代码，<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>如果正在调用的代码<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>预期<xref:System.AddIn.Contract.INativeHandleContract>。 在此情况下，调用方将为主机端适配器，这在后续子节中有所介绍。  
  
> [!NOTE]
>  你还需要重写<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>使用 tab 键切换之间主机应用程序在此模型中[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]和外接程序[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 有关详细信息，请参阅"WPF 外接程序限制" [WPF 外接程序概述](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)。  
  
 因为外接程序端适配器实现的接口。 派生自<xref:System.AddIn.Contract.INativeHandleContract>，你还需要实现<xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>，但这将被忽略时<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>被重写。  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>实现主机视图管道段  
 在此模型中，主机应用程序通常需要为主机视图<xref:System.Windows.FrameworkElement>子类。 主机端适配器必须将转换<xref:System.AddIn.Contract.INativeHandleContract>到<xref:System.Windows.FrameworkElement>后<xref:System.AddIn.Contract.INativeHandleContract>跨越隔离边界。 由于方法未调用由主机应用程序获取<xref:System.Windows.FrameworkElement>，主机视图必须"返回"<xref:System.Windows.FrameworkElement>通过将包含它。 因此，主机视图必须派生自的一个子类<xref:System.Windows.FrameworkElement>可包含其他[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]，如<xref:System.Windows.Controls.UserControl>。 下面的代码演示作为实现的协定主机视图`WPFAddInHostView`类。  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>实现主机端适配器管道段  
 协定是<xref:System.AddIn.Contract.INativeHandleContract>，主机应用程序期望<xref:System.Windows.Controls.UserControl>（所指定的主机视图）。 因此，<xref:System.AddIn.Contract.INativeHandleContract>必须转换为<xref:System.Windows.FrameworkElement>之前被设置为主机视图的内容越过隔离边界之后, (它派生自<xref:System.Windows.Controls.UserControl>)。  
  
 这一工作由主机端适配器执行，如以下代码所示。  
  
  
  
 如你所见，主机端适配器获取<xref:System.AddIn.Contract.INativeHandleContract>通过调用外接程序端适配器<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>方法 (这是点，其中<xref:System.AddIn.Contract.INativeHandleContract>跨越隔离边界)。  
  
 主机端适配器，然后将转换<xref:System.AddIn.Contract.INativeHandleContract>到<xref:System.Windows.FrameworkElement>通过调用<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>。 最后，<xref:System.Windows.FrameworkElement>设置为主机视图的内容。  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>实现外接程序  
 外接程序端适配器和外接程序视图就位后，外接程序就可以通过派生自外接程序视图来实现，如以下代码所示。  
  
  
  
  
  
 在此示例中，你可以看到此模型的一个突出优点： 外接程序开发人员只需实现外接程序 (因为它是[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]也)，而不是一个外接程序类和外接程序[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>实现主机应用程序  
 主机端适配器和创建主机视图中，主机应用程序可以使用[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型来打开管道并获得的外接程序的主机视图。 这些步骤在以下代码中显示。  
  
  
  
 主机应用程序使用典型[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型代码以激活外接程序，它将隐式返回主机应用程序的主机视图。 主机应用程序随后将显示主机视图 (即<xref:System.Windows.Controls.UserControl>) 从<xref:System.Windows.Controls.Grid>。  
  
 处理与外接程序的交互的代码[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]在外接程序的应用程序域中运行。 这些交互包括以下内容：  
  
-   处理<xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件。  
  
-   显示<xref:System.Windows.MessageBox>。  
  
 此活动完全独立于主机应用程序。  
  
## <a name="see-also"></a>请参阅  
 [外接程序和扩展性](../../../../docs/framework/add-ins/index.md)  
 [WPF 外接程序概述](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
