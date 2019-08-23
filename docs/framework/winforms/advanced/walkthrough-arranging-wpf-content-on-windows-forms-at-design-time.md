---
title: 演练：在设计时在 Windows 窗体上排列 WPF 内容
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7858ffd708c78d6397d533f613ccc2ea78d6cbed
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658523"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a>演练：在设计时排列 Windows 窗体上的 WPF 内容

本文介绍如何使用 Windows 窗体布局功能 (如锚定和对齐线) 来排列 Windows Presentation Foundation (WPF) 控件。

## <a name="prerequisites"></a>系统必备

若要完成本演练，必须具有 Visual Studio。

## <a name="create-the-project"></a>创建项目

打开 Visual Studio, 并在 Visual Basic 或视觉对象C#中创建一个名为`ArrangeElementHost`的新 Windows 窗体应用程序项目。

> [!NOTE]
> 承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。

## <a name="create-the-wpf-control"></a>创建 WPF 控件

将 WPF 控件添加到项目后，就可以在窗体上对其进行排列。

1. 将新的 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参见[演练：在设计时](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)在 Windows 窗体上创建新的 WPF 内容。

2. 在设计视图中，请确保已选中 `UserControl1`。

3. 在 "**属性**" 窗口中, 将<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性的值设置为**200**。

4. 将<xref:System.Windows.Controls.Control.Background%2A>属性的值设置为**蓝色**。

5. 生成项目。

## <a name="host-wpf-controls-in-a-layout-panel"></a>在布局面板中承载 WPF 控件

在布局面板中使用 WPF 控件与使用其他 Windows 窗体控件的方式可以相同。

1. 在 Windows 窗体设计器中打开 `Form1`。

2. 在 "**工具箱**" 中, <xref:System.Windows.Forms.TableLayoutPanel>将控件拖到窗体上。

3. 在控件的智能标记面板上, 选择 "**删除最后一行**"。 <xref:System.Windows.Forms.TableLayoutPanel>

4. 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大的宽度和高度。

5. 在 "**工具箱**" 中, 双击`UserControl1`以在<xref:System.Windows.Forms.TableLayoutPanel>控件的第`UserControl1`一个单元格中创建的实例。

   `UserControl1` 的实例承载在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

6. 在 "**工具箱**" 中, 双击`UserControl1`以在<xref:System.Windows.Forms.TableLayoutPanel>控件的第二个单元格中创建另一个实例。

7. 在 "**文档大纲**" 窗口中`tableLayoutPanel1`, 选择。

8. 在 "**属性**" 窗口中, 将<xref:System.Windows.Forms.Control.Padding%2A>属性的值设置为10、 **10、10、10**。

   调整两个 <xref:System.Windows.Forms.Integration.ElementHost> 控件的大小以适应新的布局。

## <a name="use-snaplines-to-align-wpf-controls"></a>使用对齐线对齐 WPF 控件

使用对齐线能够轻松对齐窗体上的控件。 还可以使用对齐线对齐 WPF 控件。 有关详细信息，请参见[演练：使用对齐线](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)排列 Windows 窗体上的控件。

1. 从 "**工具箱**" 中, 将的`UserControl1`实例拖到窗体上, 并将其放在<xref:System.Windows.Forms.TableLayoutPanel>控件下的空间中。

   `UserControl1` 的实例承载在名为 `elementHost3` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

2. 使用对齐线，将 `elementHost3` 的左边缘与 <xref:System.Windows.Forms.TableLayoutPanel> 控件的左边缘对齐。

3. 使用对齐线，将 `elementHost3` 按与 <xref:System.Windows.Forms.TableLayoutPanel> 控件相同的宽度排列。

4. 朝着 <xref:System.Windows.Forms.TableLayoutPanel> 控件移动 `elementHost3`，直到控件间显示居中对齐线。

5. 在 "**属性**" 窗口中, 将 "Margin" 属性的值设置为**20、20、20、20**。

6. 向远离 <xref:System.Windows.Forms.TableLayoutPanel> 控件的方向移动 `elementHost3`，直到再次显示居中对齐线。 现在，居中对齐线指示边距为 20。

7. 向`elementHost3`右移动, 直到其左边缘与的左边`elementHost1`缘对齐。

8. 更改 `elementHost3` 的宽度，直到其右边缘与 `elementHost2` 的右边缘对齐。

## <a name="anchor-and-dock-wpf-controls"></a>定位和停靠 WPF 控件

窗体上承载的 WPF 控件具有与其他 Windows 窗体控件相同的锚定和停靠行为。

1. 选择 `elementHost1`。

2. 在 "**属性**" 窗口中, <xref:System.Windows.Forms.Control.Anchor%2A>将属性设置为**顶部、底部、左侧和右侧**。

3. 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大。

   调整 `elementHost1` 控件大小，以填充单元格。

4. 选择 `elementHost2`。

5. 在 "**属性**" 窗口中, 将<xref:System.Windows.Forms.Control.Dock%2A>属性的值设置为。 <xref:System.Windows.Forms.DockStyle.Fill>

   调整 `elementHost2` 控件大小，以填充单元格。

6. 选择 <xref:System.Windows.Forms.TableLayoutPanel> 控件。

7. 将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Top>。

8. 选择 `elementHost3`。

9. 将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Fill>。

   调整 `elementHost3` 控件大小，以填充窗体上的剩余空间。

10. 调整窗体大小。

    所有三个 <xref:System.Windows.Forms.Integration.ElementHost> 控件将相应地调整大小。

    有关详细信息，请参阅[如何：在 TableLayoutPanel 控件](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)中锚定和停靠子控件。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [如何：在设计时将控件与窗体边缘对齐](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [演练：使用对齐线排列 Windows 窗体上的控件](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [迁移和互操作性](../../wpf/advanced/migration-and-interoperability.md)
- [使用 WPF 控件](using-wpf-controls.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/designers/designing-xaml-in-visual-studio)
