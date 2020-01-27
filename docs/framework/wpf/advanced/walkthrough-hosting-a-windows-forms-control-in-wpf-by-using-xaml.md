---
title: 使用 XAML 在 WPF 中承载 Windows 窗体控件
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: a0a88c39a25e5292365a6447cefdd8f31db5e5c3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744919"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>연습: XAML을 사용하여 WPF에서 Windows Forms 컨트롤 호스팅
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 풍부한 기능 집합이 있는 많은 컨트롤을 제공합니다. 但是，有时您可能希望在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上使用 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。 例如，您可能在现有 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件中有大量投资，或者您可能有一个提供独特功能的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件。  
  
 本演练演示如何使用 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上承载 Windows 窗体 <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 控件。  
  
 有关本演练中所示任务的完整代码列表，请参阅[使用 XAML 在 WPF 中承载 Windows 窗体控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)。
  
## <a name="prerequisites"></a>先决条件  

이 연습을 완료하려면 Visual Studio가 필요합니다.  
  
## <a name="hosting-the-windows-forms-control"></a>Windows Forms 컨트롤 호스팅  
  
#### <a name="to-host-the-maskedtextbox-control"></a>MaskedTextBox 컨트롤을 호스트하려면  
  
1. 创建一个名为 `HostingWfInWpfWithXaml`的 WPF 应用程序项目。  
  
2. 다음 어셈블리에 대한 참조를 추가합니다.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. 在 WPF 设计器中打开 Mainwindow.xaml。  
  
4. 在 <xref:System.Windows.Window> 元素中，添加以下命名空间映射。 `wf` 命名空间映射将建立对包含 Windows 窗体控件的程序集的引用。  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. 在 <xref:System.Windows.Controls.Grid> 元素中添加以下 XAML。  
  
     <xref:System.Windows.Forms.MaskedTextBox> 控件创建为 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的子控件。  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows Forms 컨트롤 및 해당 WPF 컨트롤](windows-forms-controls-and-equivalent-wpf-controls.md)
- [使用 XAML 在 WPF 中承载 Windows 窗体控件](https://go.microsoft.com/fwlink/?LinkID=160000)
