---
title: 演练：使用 XAML 在 WPF 中承载 Windows 窗体控件
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 10596f3ec89a5dc8bb7c20274b697d2592ad93d5
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197887"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>演练：使用 XAML 在 WPF 中承载 Windows 窗体控件
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 提供了许多具有丰富功能集的控件。 但是，有时您可能希望在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上使用 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。 例如，您可能在现有 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件中有大量投资，或者您可能有一个提供独特功能的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。  
  
 本演练演示如何使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上承载 Windows 窗体 <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 控件。  
  
 有关本演练中所示任务的完整代码列表，请参阅[使用 XAML 在 WPF 中承载 Windows 窗体控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)。
  
## <a name="prerequisites"></a>Prerequisites  

若要完成本演练，必须具有 Visual Studio。  
  
## <a name="hosting-the-windows-forms-control"></a>承载 Windows 窗体控件  
  
#### <a name="to-host-the-maskedtextbox-control"></a>承载 MaskedTextBox 控件  
  
1. 创建一个名为 `HostingWfInWpfWithXaml`的 WPF 应用程序项目。  
  
2. 添加对下列程序集的引用。  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. 在 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]中打开 Mainwindow.xaml。  
  
4. 在 <xref:System.Windows.Window> 元素中，添加以下命名空间映射。 `wf` 命名空间映射将建立对包含 Windows 窗体控件的程序集的引用。  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. 在 <xref:System.Windows.Controls.Grid> 元素中添加以下 XAML。  
  
     <xref:System.Windows.Forms.MaskedTextBox> 控件创建为 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的子控件。  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. 按 F5 生成并运行该应用程序。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [演练：在 WPF 中承载 Windows 窗体控件](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows 窗体控件和等效的 WPF 控件](windows-forms-controls-and-equivalent-wpf-controls.md)
- [使用 XAML 在 WPF 中承载 Windows 窗体控件](https://go.microsoft.com/fwlink/?LinkID=160000)
