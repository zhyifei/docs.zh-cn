---
title: 演练：设计时在 Windows 窗体上分配 WPF 内容
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0c1e0c91b7ab8bded677a86b597b02b9cb442d98
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460668"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a>演练：在设计时在 Windows 窗体上分配 WPF 内容

本文介绍如何选择要在窗体上显示的 Windows Presentation Foundation （WPF）控件类型。 可选择项目中包含的任何 WPF 控件类型。

## <a name="prerequisites"></a>Prerequisites

若要完成本演练，必须具有 Visual Studio。

## <a name="create-the-project"></a>创建项目

打开 Visual Studio，并在 Visual Basic 或视觉对象C#命名 `SelectingWpfContent`中创建新的 Windows 窗体应用程序项目。

> [!NOTE]
> 承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。

## <a name="create-the-wpf-control-types"></a>创建 WPF 控件类型

将 WPF 控件类型添加到项目后，可将其托管到不同的 <xref:System.Windows.Forms.Integration.ElementHost> 控件。

1. 将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参阅[演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。

2. 在设计视图中，请确保已选中 `UserControl1`。

3. 在 "**属性**" 窗口中，将 "<xref:System.Windows.FrameworkElement.Width%2A>" 和 "<xref:System.Windows.FrameworkElement.Height%2A>" 属性的值设置为**200**。

4. 向 <xref:System.Windows.Controls.UserControl> 中添加 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件，并将 <xref:System.Windows.Controls.TextBox.Text%2A> 属性的值设置为 "**托管内容**"。

5. 将第二个 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。 使用控件类型的默认名称，`UserControl2.xaml`。

6. 在 "**属性**" 窗口中，将 "<xref:System.Windows.FrameworkElement.Width%2A>" 和 "<xref:System.Windows.FrameworkElement.Height%2A>" 属性的值设置为**200**。

7. 将 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件添加到 <xref:System.Windows.Controls.UserControl> 并将 <xref:System.Windows.Controls.TextBox.Text%2A> 属性的值设置为 "**寄宿内容 2**"。

   > [!NOTE]
   > 一般情况下，你应承载更复杂的 WPF 内容。 此处，<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 控件仅为了便于说明。

8. 生成项目。

## <a name="select-wpf-controls"></a>选择 WPF 控件

可将不同的 WPF 内容分配到 <xref:System.Windows.Forms.Integration.ElementHost> 控件，该控件现已承载内容。

1. 在 Windows 窗体设计器中打开 `Form1`。

2. 在 "**工具箱**" 中，双击 "`UserControl1`" 以在窗体上创建 `UserControl1` 的实例。

   `UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

3. 在 `elementHost1`的智能标记面板中，打开 "**选择所承载的内容**" 下拉列表。

4. 从下拉列表框中选择 " **UserControl2** "。

   `elementHost1` 控件现承载 `UserControl2` 类型的实例。

5. 在 "**属性**" 窗口中，确认 "<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>" 属性设置为 " **UserControl2**"。

6. 从 "**工具箱**" 的 " **WPF 互操作性**" 组中，将 <xref:System.Windows.Forms.Integration.ElementHost> 控件拖到窗体上。

   新控件的默认名称是 `elementHost2`。

7. 在 `elementHost2`的智能标记面板中，打开 "**选择所承载的内容**" 下拉列表。

8. 从下拉列表中选择 " **UserControl1** "。

9. `elementHost2` 控件现承载 `UserControl1` 类型的实例。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [迁移和互操作性](../../wpf/advanced/migration-and-interoperability.md)
- [使用 WPF 控件](using-wpf-controls.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
