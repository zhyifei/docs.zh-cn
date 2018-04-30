---
title: 如何：创建返回 UI 的外接程序
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e89cb9d0c8e5a26703ff5f56a3af10d7fe9923f
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>如何：创建返回 UI 的外接程序
此示例演示如何创建 Windows Presentation Foundation (WPF) 返回到主机的外接程序[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]独立的应用程序。  
  
 外接程序返回[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]即[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]用户控件。 用户控件的内容是单个按钮，单击时会显示消息框。 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]独立的应用程序承载外接程序，并将用户控件 （由外接程序返回） 显示为应用程序主窗口的内容。  
  
 **系统必备**  
  
 此示例重点介绍[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]扩展[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，启用此方案中，假设您具备以下：  
  
-   知识[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，包括管道、 外接程序和主机开发。 如果你不熟悉这些概念，请参阅[外接程序和扩展性](../../../../docs/framework/add-ins/index.md)。 有关演示如何实现管道、 外接程序和主机应用程序的教程，请参阅[演练： 创建可扩展应用程序](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)。  
  
-   知识[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]扩展[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型，这可在此处找到： [WPF 外接程序概述](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)。  
  
## <a name="example"></a>示例  
 若要返回的外接程序创建[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]以及每个管道段外, 接程序时，主机应用程序需要特定的代码。  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>实现协定管道段  
 方法必须由返回的协定定义[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]，且其返回值必须为类型<xref:System.AddIn.Contract.INativeHandleContract>。 说明了这一点通过`GetAddInUI`方法`IWPFAddInContract`在下面的代码协定。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>实现外接程序视图管道段  
 因为外接程序实现[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]它作为的子类提供<xref:System.Windows.FrameworkElement>，与容量相关联的外接程序视图上的方法`IWPFAddInView.GetAddInUI`必须返回类型的值<xref:System.Windows.FrameworkElement>。 以下代码显示作为接口实现的协定的外接程序视图。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>实现外接程序端适配器管道段  
 该协定方法返回<xref:System.AddIn.Contract.INativeHandleContract>，但外接程序返回<xref:System.Windows.FrameworkElement>（所指定的外接程序视图）。 因此，<xref:System.Windows.FrameworkElement>必须转换为<xref:System.AddIn.Contract.INativeHandleContract>在越过隔离边界之前。 通过调用执行此工作的外接程序端适配器<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>，如下面的代码中所示。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>实现主机视图管道段  
 因为主机应用程序将显示<xref:System.Windows.FrameworkElement>，与容量相关联的主机视图上的方法`IWPFAddInHostView.GetAddInUI`必须返回类型的值<xref:System.Windows.FrameworkElement>。 以下代码显示作为接口实现的协定的主机视图。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>实现主机端适配器管道段  
 该协定方法返回<xref:System.AddIn.Contract.INativeHandleContract>，但主机应用程序需要<xref:System.Windows.FrameworkElement>（所指定的主机视图）。 因此，<xref:System.AddIn.Contract.INativeHandleContract>必须转换为<xref:System.Windows.FrameworkElement>越过隔离边界之后。 通过调用执行此工作的主机端适配器<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>，如下面的代码中所示。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>实现外接程序  
 使用外接程序端适配器和外接程序中创建视图外, 接程序 (`WPFAddIn1.AddIn`) 必须实现`IWPFAddInView.GetAddInUI`方法以返回<xref:System.Windows.FrameworkElement>对象 (<xref:System.Windows.Controls.UserControl>在此示例中)。 实现<xref:System.Windows.Controls.UserControl>， `AddInUI`，通过以下代码所示。  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 实现`IWPFAddInView.GetAddInUI`通过外接程序只需返回的新实例`AddInUI`，如下面的代码所示。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>实现主机应用程序  
 主机端适配器和创建主机视图中，主机应用程序可以使用[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]外接程序模型来打开管道，可获取的宿主视图的外接程序，并调用`IWPFAddInHostView.GetAddInUI`方法。 这些步骤在以下代码中显示。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>请参阅  
 [外接程序和扩展性](../../../../docs/framework/add-ins/index.md)  
 [WPF 外接程序概述](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
