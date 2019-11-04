---
title: 演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 76c880c208355b01d0fbaf46cf58091ad147846b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460610"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>演练：按填充、边距和 AutoSize 属性对控件进行布局

在窗体上精确地放置控件对于许多应用程序而言是高优先级。 Visual Studio 中的**Windows 窗体设计器**提供了许多布局工具来实现此目的。 其中三个最重要的是 <xref:System.Windows.Forms.Control.Margin%2A>、<xref:System.Windows.Forms.Control.Padding%2A>和 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性，这些属性在所有 Windows 窗体控件上都存在。

<xref:System.Windows.Forms.Control.Margin%2A> 属性定义控件周围的空间，该空间使其他控件与该控件的边框保持指定的距离。

<xref:System.Windows.Forms.Control.Padding%2A> 属性定义控件内部的空间，该空间使控件的内容（例如，其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值）与该控件的边框保持指定的距离。

下图显示控件上的 <xref:System.Windows.Forms.Control.Padding%2A> 和 <xref:System.Windows.Forms.Control.Margin%2A> 属性。

![Windows 窗体控件的填充和边距](./media/vs-winformpadmargin.gif)

<xref:System.Windows.Forms.Control.AutoSize%2A> 属性通知控件自动调整其内容的大小。 它不会将其大小调整为小于其原始 <xref:System.Windows.Forms.Control.Size%2A> 属性的值，并且将考虑其 <xref:System.Windows.Forms.Control.Padding%2A> 属性的值。

## <a name="prerequisites"></a>Prerequisites

需要 Visual Studio 才能完成此演练。

## <a name="create-the-project"></a>创建项目

1. 在 Visual Studio 中，创建一个名为 `LayoutExample`的**Windows 应用程序**项目。

2. 在**Windows 窗体设计器**中选择窗体。

## <a name="set-margins-for-controls"></a>设置控件的边距

您可以使用 <xref:System.Windows.Forms.Control.Margin%2A> 属性设置控件之间的默认距离。 当您将控件向右移动到另一个控件时，将看到显示两个控件的边距的对齐线。 您要移动的控件也将与边距定义的距离对齐。

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>使用 Margin 属性排列窗体上的控件

1. 将两个 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖到窗体上。

2. 选择某个 <xref:System.Windows.Forms.Button> 控件，并将其移动到另一个控件，直到它们接近。

   观察它们之间出现的对齐线。 此距离是两个控件的 <xref:System.Windows.Forms.Control.Margin%2A> 值之和。 正在移动的控件将对齐到此距离。 有关详细信息，请参阅[演练：使用对齐线排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。

3. 通过在 "**属性**" 窗口中展开 "<xref:System.Windows.Forms.Control.Margin%2A>" 条目并将 "<xref:System.Windows.Forms.Padding.All%2A>" 属性设置为 " **20**"，更改其中一个控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。

4. 选择某个 <xref:System.Windows.Forms.Button> 控件，并将其移到另一个控件附近。

   定义边距值的和的对齐线会更长，并使控件与其他控件对齐。

5. 通过在 "**属性**" 窗口中展开 "<xref:System.Windows.Forms.Control.Margin%2A>" 条目并将 "<xref:System.Windows.Forms.Padding.Top%2A>" 属性设置为 " **5**"，更改所选控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。

6. 将所选控件移动到另一个控件的下方，并观察对齐线是否更短。 将所选控件移动到另一个控件的左侧，并观察对齐线是否保留步骤4中观测到的值。

7. 您可以将 <xref:System.Windows.Forms.Control.Margin%2A> 属性的每个方面（<xref:System.Windows.Forms.Padding.Left%2A>、<xref:System.Windows.Forms.Padding.Top%2A>、<xref:System.Windows.Forms.Padding.Right%2A>、<xref:System.Windows.Forms.Padding.Bottom%2A>）设置为不同的值，也可以将它们全部设置为与 <xref:System.Windows.Forms.Padding.All%2A> 属性相同的值。

## <a name="set-padding-for-controls"></a>为控件设置填充

若要实现应用程序所需的精确布局，控件通常会包含子控件。 若要指定子控件边框到父控件边框的邻近性，请结合使用父控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性和子控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。 <xref:System.Windows.Forms.Control.Padding%2A> 属性还可用于控制控件内容（例如，<xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性）与边框的邻近性。

### <a name="arrange-controls-on-your-form-using-padding"></a>使用填充排列窗体上的控件

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。

2. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值更改为**true**。

3. 在 "**属性**" 窗口中展开 "<xref:System.Windows.Forms.Control.Padding%2A>" 条目，并将 "<xref:System.Windows.Forms.Padding.All%2A>" 属性设置为 " **5**"，更改 "<xref:System.Windows.Forms.Control.Padding%2A>" 属性。

   控件将展开以为新的填充提供空间。

4. 从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。 将 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖动到 <xref:System.Windows.Forms.GroupBox> 控件中。 将 <xref:System.Windows.Forms.Button> 控件定位，使其与 <xref:System.Windows.Forms.GroupBox> 控件的右下角对齐。

   观察显示的对齐线，<xref:System.Windows.Forms.Button> 控件接近 <xref:System.Windows.Forms.GroupBox> 控件的下边框和右边框。 这些对齐线对应于 <xref:System.Windows.Forms.Button>的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。

5. 通过在 "**属性**" 窗口中展开 <xref:System.Windows.Forms.Control.Padding%2A> 项并将 <xref:System.Windows.Forms.Padding.All%2A> 属性设置为**20**，更改 <xref:System.Windows.Forms.GroupBox> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性。

6. 选择 <xref:System.Windows.Forms.GroupBox> 控件中的 "<xref:System.Windows.Forms.Button>" 控件，并将其移到 <xref:System.Windows.Forms.GroupBox>中心。

   对齐线与 <xref:System.Windows.Forms.GroupBox> 控件边框的显示距离更远。 此距离是 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性与 <xref:System.Windows.Forms.GroupBox> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性之和。

## <a name="size-controls-automatically"></a>自动调整控件大小

在某些应用程序中，控件的大小在运行时与设计时的大小不相同。 例如，可以从数据库中获取 <xref:System.Windows.Forms.Button> 控件的文本，并且它的长度事先未知。

当 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性设置为 `true`时，控件的大小会自行调整为其内容。 有关详细信息，请参阅[AutoSize 属性概述](autosize-property-overview.md)。

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>使用 AutoSize 属性排列窗体上的控件

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。

2. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值更改为**true**。

3. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为**此按钮的 Text 属性的长字符串**。

   提交更改时，<xref:System.Windows.Forms.Button> 控件会调整其自身大小以适应新文本。

4. 将另一个 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖到窗体上。

5. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为 "**此按钮的 Text 属性的长字符串。** "

   提交更改时，<xref:System.Windows.Forms.Button> 控件不会调整其自身的大小，而是由控件的右边缘剪切文本。

6. 在 "**属性**" 窗口中展开 "<xref:System.Windows.Forms.Control.Padding%2A>" 条目，并将 "<xref:System.Windows.Forms.Padding.All%2A>" 属性设置为 " **5**"，更改 "<xref:System.Windows.Forms.Control.Padding%2A>" 属性。

   控件内部的文本在所有四个边都被剪切。

7. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性更改为**true**。

   <xref:System.Windows.Forms.Button> 控件调整自身大小以包含整个字符串。 此外，文本周围还添加了填充，导致 <xref:System.Windows.Forms.Button> 控件在四个方向上都展开。

8. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。 将其放置在窗体右下角附近。

9. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值更改为**true**。

10. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置为 <xref:System.Windows.Forms.AnchorStyles.Right>，<xref:System.Windows.Forms.AnchorStyles.Bottom>。

11. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Text%2A> 属性更改为 "**此按钮的 Text 属性的长字符串。** "

   提交更改时，<xref:System.Windows.Forms.Button> 控件向左调整其自身大小。 通常，自动调整大小会将控件的大小增加 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置的方向。

## <a name="autosize-and-autosizemode-properties"></a>AutoSize 和 AutoSizeMode 属性

 某些控件支持 `AutoSizeMode` 属性，这使你可以更精细地控制控件的自动调整大小行为。

### <a name="use-the-autosizemode-property"></a>使用 AutoSizeMode 属性

1. 从 <xref:System.Windows.Forms.Panel> “工具箱” **将** 控件拖到你的窗体上。

2. 将 <xref:System.Windows.Forms.Panel> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值设置为**true**。

3. 将 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖动到 <xref:System.Windows.Forms.Panel> 控件中。

4. 将 <xref:System.Windows.Forms.Button> 控件放在 <xref:System.Windows.Forms.Panel> 控件右下角附近。

5. 选择 "<xref:System.Windows.Forms.Panel>" 控件并抓住右下的大小调整控点。 将 <xref:System.Windows.Forms.Panel> 控件的大小调整为更大、更小。

   > [!NOTE]
   > 可以自由调整 <xref:System.Windows.Forms.Panel> 控件的大小，但不能将其大小调整为小于 <xref:System.Windows.Forms.Button> 控件右下角的位置。 此行为由 <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>`AutoSizeMode` 属性的默认值指定。

6. 将 <xref:System.Windows.Forms.Panel> 控件的 `AutoSizeMode` 属性的值设置为 "<xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>"。

   <xref:System.Windows.Forms.Panel> 控件调整自身大小以包围 <xref:System.Windows.Forms.Button> 控件。 无法调整 <xref:System.Windows.Forms.Panel> 控件的大小。

7. 将 <xref:System.Windows.Forms.Button> 控件拖向 <xref:System.Windows.Forms.Panel> 控件的左上角。

   <xref:System.Windows.Forms.Panel> 控件调整到 <xref:System.Windows.Forms.Button> 控件的新位置。

## <a name="next-steps"></a>后续步骤

在 Windows 窗体应用程序中排列控件还有很多其他布局功能。 下面是可以尝试的一些组合：

- 使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件生成窗体。 有关详细信息，请参阅[演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)。 尝试更改 <xref:System.Windows.Forms.TableLayoutPanel> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性的值以及其子控件上的 <xref:System.Windows.Forms.Control.Margin%2A> 属性。

- 使用 <xref:System.Windows.Forms.FlowLayoutPanel> 控件尝试相同的试验。 有关详细信息，请参阅[演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)。

- 尝试在 <xref:System.Windows.Forms.Panel> 控件中停靠子控件。 <xref:System.Windows.Forms.Control.Padding%2A> 属性是对 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> 属性的更通用的实现，你可以通过将子控件置于 <xref:System.Windows.Forms.Panel> 控件中并将子控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>来满足这种情况。 将 <xref:System.Windows.Forms.Panel> 控件的 <xref:System.Windows.Forms.Control.Padding%2A> 属性设置为不同的值，并记下该效果。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [AutoSize 属性概述](autosize-property-overview.md)
- [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [演练：使用对齐线在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
