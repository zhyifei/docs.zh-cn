---
title: 演练：在 Windows 窗体中承载 3-D WPF 复合控件
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: a35f2b4062edb18914c55046a69dcd9b8825d778
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353850"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>演练：在 Windows 窗体中承载 3-D WPF 复合控件

本演练演示如何使用 @no__t 2 控件创建 @no__t 0 复合控件，并将其托管在 @no__t 1 控件和窗体中。

在本演练中，您将实现一个 @no__t 0 <xref:System.Windows.Controls.UserControl>，其中包含两个子控件。 @No__t-0 将显示一个三维（3-d）圆锥。 与 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 相比，用 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 呈示三维对象更容易。 因此，有必要托管一个 @no__t 0 @no__t 类，以便在 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 中创建三维图形。

本演练涉及以下任务：

- 创建 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] @no__t。

- 正在创建 Windows 窗体主机项目。

- 承载 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] @no__t。

## <a name="prerequisites"></a>先决条件

你需要以下组件来完成本演练：

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>创建 UserControl

1. 创建一个名为 `HostingWpfUserControlInWf` 的**WPF 用户控件库**项目。

2. 在 @no__t 中打开 UserControl1。

3. 将生成的代码替换为以下代码：

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     此代码定义一个 @no__t 0，其中包含两个子控件。 第一个子控件是 @no__t 0 控件;第二个是用于显示三维圆锥的 @no__t 1 控件。

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>创建主机项目

1. 将名为 `WpfUserControlHost` 的**Windows 窗体应用（.NET Framework）** 项目添加到解决方案。

2. 在**解决方案资源管理器**中，添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。

3. 添加对以下 @no__t 的程序集的引用：

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. 添加对 @no__t 项目的引用。

5. 在解决方案资源管理器中，将 @no__t 的项目设置为启动项目。

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>承载 UserControl

1. 在 Windows 窗体设计器中，打开 "Form1"。

2. 在属性窗口中，单击 "**事件**"，然后双击 "@no__t" 事件以创建事件处理程序。

     "代码编辑器" 将打开新生成的 @no__t 0 事件处理程序。

3. 将 Form1.cs 中的代码替换为以下代码。

     @No__t 0 事件处理程序创建 @no__t 为1的实例，并将内部控件的子控件集合添加 @no__t 到该集合。 将 @no__t 0 控件添加到窗体的子控件集合。

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. 按 F5 生成并运行该应用程序。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [演练：在 WPF 中承载 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [在 Windows 窗体示例中承载 WPF 复合控件](https://go.microsoft.com/fwlink/?LinkID=160001)
