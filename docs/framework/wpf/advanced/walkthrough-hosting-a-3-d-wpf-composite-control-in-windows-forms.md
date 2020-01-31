---
title: 在 Windows 窗体中托管 3D WPF 复合控件
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: 07222809d62b207730ddad3c87b8fb60e1602bc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744450"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a>演练：在 Windows 窗体中托管 3D WPF 复合控件

本演练演示如何创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 复合控件，并使用 <xref:System.Windows.Forms.Integration.ElementHost> 控件将其承载于 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件和窗体中。

在本演练中，您将实现一个 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>，其中包含两个子控件。 <xref:System.Windows.Controls.UserControl> 显示三维（3D）圆锥。 与 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]相比，呈现3D 对象更容易 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 因此，在 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]中承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 类来创建3D 图形是有意义的。

이 연습에서 설명하는 작업은 다음과 같습니다.

- 创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。

- 正在创建 Windows 窗体主机项目。

- 承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。

## <a name="prerequisites"></a>先决条件

이 연습을 완료하려면 다음 구성 요소가 필요합니다.

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>创建 UserControl

1. 创建一个名为 `HostingWpfUserControlInWf`的**WPF 用户控件库**项目。

2. 在 WPF 设计器中打开 UserControl1。

3. 将生成的代码替换为以下代码：

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     此代码定义一个包含两个子控件的 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>。 第一个子控件是 <xref:System.Windows.Controls.Label?displayProperty=nameWithType> 控件;第二个是显示三维圆锥的 <xref:System.Windows.Controls.Viewport3D> 控件。

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>创建主机项目

1. 将名为 `WpfUserControlHost` 的**Windows 窗体应用（.NET Framework）** 项目添加到解决方案。

2. 在**解决方案资源管理器**中，添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。

3. 添加对以下 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 程序集的引用：

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. 添加对 `HostingWpfUserControlInWf` 项目的引用。

5. 在解决方案资源管理器中，将 `WpfUserControlHost` 项目设置为启动项目。

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>承载 UserControl

1. 在 Windows 窗体设计器中，打开 "Form1"。

2. 在属性窗口中，单击 "**事件**"，然后双击 <xref:System.Windows.Forms.Form.Load> 事件创建事件处理程序。

     "代码编辑器" 将打开新生成的 `Form1_Load` 事件处理程序。

3. 将 Form1.cs 中的代码替换为以下代码。

     `Form1_Load` 事件处理程序将创建 `UserControl1` 的实例，并将内部添加到 <xref:System.Windows.Forms.Integration.ElementHost> 控件的子控件集合。 <xref:System.Windows.Forms.Integration.ElementHost> 控件将添加到窗体的子控件集合。

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다.

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Visual Studio에서 XAML 디자인](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [在 Windows 窗体示例中承载 WPF 复合控件](https://go.microsoft.com/fwlink/?LinkID=160001)
