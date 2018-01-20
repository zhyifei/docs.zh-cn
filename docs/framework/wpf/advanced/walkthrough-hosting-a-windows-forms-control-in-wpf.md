---
title: "演练：在 WPF 中承载 Windows 窗体控件"
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
helpviewer_keywords: hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ce6920e8a6cea08f4aba083b99d56b4252409827
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>演练：在 WPF 中承载 Windows 窗体控件
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了许多具有丰富功能集的控件。 但是，你可能有时想要使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]上的控件你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页。 例如，您可能必须在存在大量的投资[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，或你可能具有[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]提供唯一的功能的控件。  
  
 本演练演示如何承载[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>控制上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]通过使用代码页。  
  
 在本演练中所示的任务的完整代码清单，请参阅[承载 Windows 窗体控件在 WPF 示例](http://go.microsoft.com/fwlink/?LinkID=160057)。  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]。  
  
## <a name="hosting-the-windows-forms-control"></a>承载 Windows 窗体控件  
  
#### <a name="to-host-the-maskedtextbox-control"></a>承载 MaskedTextBox 控件  
  
1.  创建一个名为的 WPF 应用程序项目`HostingWfInWpf`。  
  
2.  添加对下列程序集的引用。  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  打开在 MainWindow.xaml [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。  
  
4.  名称<xref:System.Windows.Controls.Grid>元素`grid1`。  
  
     [!code-xaml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]  
  
5.  在设计视图或 XAML 视图中，选择<xref:System.Windows.Window>元素。  
  
6.  在属性窗口中，单击**事件**选项卡。  
  
7.  双击<xref:System.Windows.FrameworkElement.Loaded>事件。  
  
8.  插入以下代码以处理<xref:System.Windows.FrameworkElement.Loaded>事件。  
  
     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]  
  
9. 在文件的顶部，添加以下`Imports`或`using`语句。  
  
     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]  
  
10. 按 F5 生成并运行该应用程序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [演练：使用 XAML 在 WPF 中托管 Windows 窗体控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)  
 [演练：在 WPF 中托管 Windows 窗体复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [演练：在 Windows 窗体中承载 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Windows 窗体控件和等效的 WPF 控件](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [在 WPF 示例中承载 Windows 窗体控件](http://go.microsoft.com/fwlink/?LinkID=160057)
