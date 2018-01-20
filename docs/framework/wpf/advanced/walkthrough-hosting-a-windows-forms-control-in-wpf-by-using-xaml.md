---
title: "演练：使用 XAML 在 WPF 中承载 Windows 窗体控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65afce3e5a5b113b5243d68fd3b35231e2d92f86
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>演练：使用 XAML 在 WPF 中承载 Windows 窗体控件
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了许多具有丰富功能集的控件。 但是，你可能有时想要使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]上的控件你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页。 例如，您可能必须在存在大量的投资[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，或你可能具有[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]提供唯一的功能的控件。  
  
 本演练演示如何承载 Windows 窗体<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>控制上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页上通过使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
 在本演练中所示的任务的完整代码清单，请参阅[承载 Windows 窗体控件在 WPF 中使用的 XAML 示例](http://go.microsoft.com/fwlink/?LinkID=160000)。  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]。  
  
## <a name="hosting-the-windows-forms-control"></a>承载 Windows 窗体控件  
  
#### <a name="to-host-the-maskedtextbox-control"></a>承载 MaskedTextBox 控件  
  
1.  创建一个名为的 WPF 应用程序项目`HostingWfInWpfWithXaml`。  
  
2.  添加对下列程序集的引用。  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  打开在 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。  
  
4.  在<xref:System.Windows.Window>元素中，添加以下命名空间映射。 `wf`命名空间映射建立对包含的程序集的引用[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]控件。  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  在<xref:System.Windows.Controls.Grid>元素中添加以下 XAML。  
  
     <xref:System.Windows.Forms.MaskedTextBox>创建控件的子级<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件。  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  按 F5 生成并运行该应用程序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [演练：在 WPF 中承载 Windows 窗体控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [演练：在 WPF 中托管 Windows 窗体复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [演练：在 Windows 窗体中承载 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Windows 窗体控件和等效的 WPF 控件](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [通过使用 XAML 示例中承载 WPF 中的 Windows 窗体控件](http://go.microsoft.com/fwlink/?LinkID=160000)
