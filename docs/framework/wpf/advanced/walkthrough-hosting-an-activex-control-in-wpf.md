---
title: 演练：在 WPF 中承载 ActiveX 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 959bc7942eaae91c0a7a72124f6ab1ab92a3553f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040827"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>演练：在 WPF 中承载 ActiveX 控件
若要实现与浏览器的更好交互，可以在基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中使用 Microsoft ActiveX 控件。 本演练演示如何将 Microsoft Windows Media Player 作为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 页上的控件进行承载。

 本演练涉及以下任务：

- 创建项目。

- 创建 ActiveX 控件。

- 在 WPF 页上承载 ActiveX 控件。

 完成本演练后，你将了解如何在基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中使用 Microsoft ActiveX 控件。

## <a name="prerequisites"></a>Prerequisites
 你需要以下组件来完成本演练：

- Microsoft Windows Media Player 安装在安装了 Visual Studio 的计算机上。

- Visual Studio 2010。

## <a name="creating-the-project"></a>创建项目

### <a name="to-create-and-set-up-the-project"></a>创建并设置项目

1. 创建一个名为 `HostingAxInWpf`的 WPF 应用程序项目。

2. 将 Windows 窗体控件库项目添加到解决方案，并将项目命名为 `WmpAxLib`。

3. 在 WmpAxLib 项目中，添加对 Windows Media Player 程序集的引用，该程序集名为 wmp .dll。

4. 打开**工具箱**。

5. 右键单击 "**工具箱**"，然后单击 "**选择项**"。

6. 单击 " **COM 组件**" 选项卡，选择**Windows Media Player**控件，然后单击 **"确定"** 。

     将 Windows Media Player 控件添加到 "**工具箱**"。

7. 在解决方案资源管理器中，右键单击**UserControl1**文件，然后单击 "**重命名**"。

8. 根据语言，将名称更改为 `WmpAxControl.vb` 或 `WmpAxControl.cs`。

9. 如果系统提示您重命名所有引用，请单击 **"是"** 。

## <a name="creating-the-activex-control"></a>创建 ActiveX 控件
当将控件添加到设计图面时，Visual Studio 会自动为 Microsoft ActiveX 控件生成一个 <xref:System.Windows.Forms.AxHost> 包装器类。 下面的过程创建一个名为 AxInterop. WMPLib 的托管程序集。

### <a name="to-create-the-activex-control"></a>创建 ActiveX 控件

1. 在 Windows 窗体设计器中打开 WmpAxControl 或 WmpAxControl.cs。

2. 从 "**工具箱**" 中，将 "Windows Media Player" 控件添加到设计图面。

3. 在属性窗口中，将 Windows Media Player 控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 "<xref:System.Windows.Forms.DockStyle.Fill>"。

4. 生成 WmpAxLib 控件库项目。

## <a name="hosting-the-activex-control-on-a-wpf-page"></a>在 WPF 页上承载 ActiveX 控件

### <a name="to-host-the-activex-control"></a>承载 ActiveX 控件

1. 在 HostingAxInWpf 项目中，添加对生成的 ActiveX 互操作程序集的引用。

     此程序集命名为 AxInterop，并在导入 Windows Media Player 控件时添加到 WmpAxLib 项目的 Debug 文件夹中。

2. 添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。

3. 添加对 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 程序集的引用，该程序集名为 System.object。

4. 在 WPF 设计器中打开 Mainwindow.xaml。

5. 将 <xref:System.Windows.Controls.Grid> 元素命名为 `grid1`。

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. 在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 元素。

7. 在属性窗口中，单击 "**事件**" 选项卡。

8. 双击 "<xref:System.Windows.FrameworkElement.Loaded>" 事件。

9. 插入以下代码来处理 <xref:System.Windows.FrameworkElement.Loaded> 事件。

     此代码将创建 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件的实例，并将 `AxWindowsMediaPlayer` 控件的一个实例添加为其子级。

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. 按 F5 生成并运行该应用程序。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
