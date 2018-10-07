---
title: 演练：使用 XAML 在 WPF 中承载 Windows 窗体控件
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: eafed4db9b40d3cd6b83087d0ea4999b0854c417
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845328"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>演练：使用 XAML 在 WPF 中承载 Windows 窗体控件
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了许多具有丰富功能集的控件。 但是，您可能有时想要使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]上的控件在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页。 例如，可能有大量现有投入[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，或者您可能需[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件，用于提供的独特功能。  
  
 本演练演示如何承载 Windows 窗体<xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType>对的 control 权限[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]页上通过使用[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
 在本演练中所示的任务的完整代码列表，请参阅[承载 Windows 窗体控件在 WPF 中使用 XAML 示例](https://go.microsoft.com/fwlink/?LinkID=160000)。  
  
## <a name="prerequisites"></a>系统必备  

需要 Visual Studio 来完成本演练。  
  
## <a name="hosting-the-windows-forms-control"></a>承载 Windows 窗体控件  
  
#### <a name="to-host-the-maskedtextbox-control"></a>承载 MaskedTextBox 控件  
  
1.  创建一个名为的 WPF 应用程序项目`HostingWfInWpfWithXaml`。  
  
2.  添加对下列程序集的引用。  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  打开 MainWindow.xaml 中的[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。  
  
4.  在<xref:System.Windows.Window>元素中，添加以下命名空间映射。 `wf`命名空间映射建立对包含在 Windows 窗体控件的程序集的引用。  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  在<xref:System.Windows.Controls.Grid>添加以下 XAML 元素。  
  
     <xref:System.Windows.Forms.MaskedTextBox>控件被创建为的子<xref:System.Windows.Forms.Integration.WindowsFormsHost>控件。  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  按 F5 生成并运行该应用程序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [演练：在 WPF 中承载 Windows 窗体控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [演练：在 WPF 中托管 Windows 窗体复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [演练：在 Windows 窗体中承载 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Windows 窗体控件和等效的 WPF 控件](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [通过使用 XAML 示例中承载 WPF 中的 Windows 窗体控件](https://go.microsoft.com/fwlink/?LinkID=160000)
