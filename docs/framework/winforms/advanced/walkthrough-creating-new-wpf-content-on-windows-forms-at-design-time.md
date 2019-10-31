---
title: 演练：设计时在 Windows 窗体上创建新的 WPF 内容
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: fc6f988d6ffd270eba4abe277ca34fa2eeec56fd
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197422"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a>演练：在设计时在 Windows 窗体上创建新的 WPF 内容

本文介绍如何创建 Windows Presentation Foundation （WPF）控件，以便在基于 Windows 窗体的应用程序中使用。

## <a name="prerequisites"></a>Prerequisites

若要完成本演练，必须具有 Visual Studio。

## <a name="create-the-project"></a>创建项目

打开 Visual Studio，并在 Visual Basic 或 Visual C#命名 `HostingWpf`中创建新的**Windows 窗体应用程序（.NET Framework）** 项目。

> [!NOTE]
> 承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。

## <a name="create-a-new-wpf-control"></a>创建新的 WPF 控件

创建新的 WPF 控件并将其添加到你的项目中，这与将任何其他项添加到你的项目中一样容易。 Windows 窗体设计器使用名为*复合控件*或*用户控件*的特定类型控件。 有关 WPF 用户控件的详细信息，请参阅 <xref:System.Windows.Controls.UserControl>。

> [!NOTE]
> WPF 的 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 类型不同于 Windows 窗体提供的用户控件类型（也称为 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>）。

若要创建新的 WPF 控件：

1. 在**解决方案资源管理器**中，将一个新的**WPF 用户控件库（.NET Framework）** 项目添加到解决方案。 使用控件库默认名称 `WpfControlLibrary1`。 默认控件名称是 `UserControl1.xaml`。

   添加新控件具有以下效果：

   - 添加文件 UserControl1.xaml。

   - 添加文件 UserControl1.xaml.cs （或 UserControl1）。 此文件包含事件处理程序和其他实现的代码隐藏。

   - 添加对 WPF 程序集的引用。

   - 文件 UserControl1 在 Visual Studio 的 WPF 设计器中打开。

2. 在设计视图中，请确保已选中 `UserControl1`。

3. 在 "**属性**" 窗口中，将 "<xref:System.Windows.FrameworkElement.Width%2A>" 和 "<xref:System.Windows.FrameworkElement.Height%2A>" 属性的值设置为**200**。

4. 从 "**工具箱**" 中，将 "<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>" 控件拖动到设计图面上。

5. 在 "**属性**" 窗口中，将 "<xref:System.Windows.Controls.TextBox.Text%2A>" 属性的值设置为 "**托管内容**"。

   > [!NOTE]
   > 一般情况下，你应承载更复杂的 WPF 内容。 此处，<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件仅为了便于说明。

6. 生成项目。

## <a name="add-a-wpf-control-to-a-windows-form"></a>将 WPF 控件添加到 Windows 窗体

新的 WPF 控件可供在窗体上使用。 Windows 窗体使用 <xref:System.Windows.Forms.Integration.ElementHost> 控件来承载 WPF 内容。

若要将 WPF 控件添加到 Windows 窗体：

1. 在 Windows 窗体设计器中打开 `Form1`。

2. 在 "**工具箱**" 中，找到标记为 " **WPFUserControlLibrary WPF 用户控件**" 的选项卡。

3. 将 `UserControl1` 的实例拖到窗体上。

    - 在窗体上自动创建 <xref:System.Windows.Forms.Integration.ElementHost> 控件以承载 WPF 控件。

    - <xref:System.Windows.Forms.Integration.ElementHost> 控件被命名为 `elementHost1` 并在 "**属性**" 窗口中，可以看到其 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 属性设置为 " **UserControl1**"。

    - 将对 WPF 程序集的引用添加到项目。

    - `elementHost1` 控件具有显示可用承载选项的智能标记面板。

4. 在 " **ElementHost 任务**" 智能标记面板中，选择 "**在父容器中停靠**"。

5. 按 F5 生成并运行该应用程序。

## <a name="next-steps"></a>后续步骤

Windows 窗体和 WPF 是不同的技术，但它们设计为可以密切地互操作。 若要在应用程序中提供更丰富的外观和行为，请尝试以下操作：

- 在 WPF 页中承载 Windows 窗体控件。 有关详细信息，请参阅[演练：在 WPF 中承载 Windows 窗体控件](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)。

- 将 Windows 窗体的视觉样式应用于你的 WPF 内容。 有关详细信息，请参阅[如何：在混合应用程序中启用视觉样式](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)。

- 更改 WPF 内容的样式。 有关详细信息，请参阅[演练：设置 WPF 内容的样式](walkthrough-styling-wpf-content.md)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [迁移和互操作性](../../wpf/advanced/migration-and-interoperability.md)
- [使用 WPF 控件](using-wpf-controls.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
