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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: daf0c6495b89033e75c27a1ff0cbceaff9d85f34
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987163"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a>演练：用填充、边距和 AutoSize 属性对控件进行布局

在窗体上精确地放置控件对于许多应用程序而言是高优先级。 Visual Studio 中的**Windows 窗体设计器**提供了许多布局工具来实现此目的。 其中三个最重要的属性<xref:System.Windows.Forms.Control.Margin%2A>是<xref:System.Windows.Forms.Control.Padding%2A>、和<xref:System.Windows.Forms.Control.AutoSize%2A>属性, 它们存在于所有 Windows 窗体控件中。

<xref:System.Windows.Forms.Control.Margin%2A> 属性定义控件周围的空间，该空间使其他控件与该控件的边框保持指定的距离。

<xref:System.Windows.Forms.Control.Padding%2A> 属性定义控件内部的空间，该空间使控件的内容（例如，其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值）与该控件的边框保持指定的距离。

下图显示控件上的 <xref:System.Windows.Forms.Control.Padding%2A> 和 <xref:System.Windows.Forms.Control.Margin%2A> 属性。

![Windows 窗体控件的填充和边距](./media/vs-winformpadmargin.gif)

<xref:System.Windows.Forms.Control.AutoSize%2A>属性告知控件自动调整其内容的大小。 它不会将其大小调整为小于其原始<xref:System.Windows.Forms.Control.Size%2A>属性的值, 并且将会考虑其<xref:System.Windows.Forms.Control.Padding%2A>属性的值。

## <a name="prerequisites"></a>系统必备

需要 Visual Studio 才能完成此演练。

## <a name="create-the-project"></a>创建项目

1. 在 Visual Studio 中, 创建一个名`LayoutExample`为的**Windows 应用程序**项目。

2. 在**Windows 窗体设计器**中选择窗体。

## <a name="set-margins-for-controls"></a>设置控件的边距

您可以使用<xref:System.Windows.Forms.Control.Margin%2A>属性设置控件之间的默认距离。 当您将控件向右移动到另一个控件时, 将看到显示两个控件的边距的对齐线。 您要移动的控件也将与边距定义的距离对齐。

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a>使用 Margin 属性排列窗体上的控件

1. 将两<xref:System.Windows.Forms.Button>个控件从**工具箱**拖到窗体上。

2. 选择其中一个<xref:System.Windows.Forms.Button>控件, 并将其移动到另一个控件, 直到它们接近。

   观察它们之间出现的对齐线。 此距离是两个控件<xref:System.Windows.Forms.Control.Margin%2A>值的总和。 正在移动的控件将对齐到此距离。 有关详细信息, [请参阅演练:使用对齐线](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)排列 Windows 窗体上的控件。

3. <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Padding.All%2A>通过在"**属性**" 窗口中展开条目并将属性设置为**20**, 可更改其中一个控件的属性。<xref:System.Windows.Forms.Control.Margin%2A>

4. 选择其中一个<xref:System.Windows.Forms.Button>控件, 并将其移动到另一个控件。

   定义边距值的和的对齐线会更长, 并使控件与其他控件对齐。

5. <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Padding.Top%2A>通过在"**属性**" 窗口中展开条目并将属性设置为**5**来更改所选控件的属性。<xref:System.Windows.Forms.Control.Margin%2A>

6. 将所选控件移动到另一个控件的下方, 并观察对齐线是否更短。 将所选控件移动到另一个控件的左侧, 并观察对齐线是否保留步骤4中观测到的值。

7. 可以<xref:System.Windows.Forms.Control.Margin%2A>将<xref:System.Windows.Forms.Padding.All%2A>属性<xref:System.Windows.Forms.Padding.Left%2A> <xref:System.Windows.Forms.Padding.Top%2A>的每<xref:System.Windows.Forms.Padding.Right%2A>个方面分别设置为不同的值, 也可以将其设置为与属性相同的值。 <xref:System.Windows.Forms.Padding.Bottom%2A>

## <a name="set-padding-for-controls"></a>为控件设置填充

若要实现应用程序所需的精确布局, 控件通常会包含子控件。 若要指定子控件边框到父控件边框的邻近性, 请结合使用父<xref:System.Windows.Forms.Control.Padding%2A>控件的属性和子<xref:System.Windows.Forms.Control.Margin%2A>控件的属性。 属性还可用于控制控件内容 (例如<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Text%2A>属性) 与边框的邻近性。 <xref:System.Windows.Forms.Control.Padding%2A>

### <a name="arrange-controls-on-your-form-using-padding"></a>使用填充排列窗体上的控件

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。

2. 将<xref:System.Windows.Forms.Button>控件的属性值更改为<xref:System.Windows.Forms.Control.AutoSize%2A> true。

3. <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>通过在"**属性**" 窗口中展开条目并将属性设置为**5**来更改属性。<xref:System.Windows.Forms.Control.Padding%2A>

   控件将展开以为新的填充提供空间。

4. 从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。 将控件从 " <xref:System.Windows.Forms.GroupBox>工具箱" 拖放到控件中。 <xref:System.Windows.Forms.Button> 定位控件, 使其与<xref:System.Windows.Forms.GroupBox>控件的右下角齐平。 <xref:System.Windows.Forms.Button>

   观察<xref:System.Windows.Forms.Button>控件在控件接近<xref:System.Windows.Forms.GroupBox>控件的下边框和右边框时显示的对齐线。 这些对齐线与的<xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Button>属性相对应。

5. <xref:System.Windows.Forms.Padding.All%2A> <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.GroupBox>通过在 "**属性**" 窗口中展开条目并将属性设置为**20**, 可更改控件的属性。

6. 选择<xref:System.Windows.Forms.Button> 控件<xref:System.Windows.Forms.GroupBox>内的控件, 并将其移动到的中心<xref:System.Windows.Forms.GroupBox>。

   对齐线的显示距离<xref:System.Windows.Forms.GroupBox>控件边框更远。 此距离是<xref:System.Windows.Forms.Button>控件的<xref:System.Windows.Forms.Control.Margin%2A>属性和<xref:System.Windows.Forms.GroupBox>控件的<xref:System.Windows.Forms.Control.Padding%2A>属性的总和。

## <a name="size-controls-automatically"></a>自动调整控件大小

在某些应用程序中, 控件的大小在运行时与设计时的大小不相同。 例如, 可以从<xref:System.Windows.Forms.Button>数据库中获取控件的文本, 并且该文本的长度事先未知。

当属性设置为`true`时, 控件将自行调整其内容大小。 <xref:System.Windows.Forms.Control.AutoSize%2A> 有关详细信息, 请参阅[AutoSize 属性概述](autosize-property-overview.md)。

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a>使用 AutoSize 属性排列窗体上的控件

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。

2. 将<xref:System.Windows.Forms.Button>控件的属性值更改为<xref:System.Windows.Forms.Control.AutoSize%2A> true。

3. 将控件的<xref:System.Windows.Forms.Control.Text%2A>属性更改为**此按钮的 Text 属性的长字符串。** <xref:System.Windows.Forms.Button>

   提交更改时, <xref:System.Windows.Forms.Button>控件会自行调整大小以适应新文本。

4. 将另<xref:System.Windows.Forms.Button>一个控件从**工具箱**拖到窗体上。

5. 将控件的<xref:System.Windows.Forms.Control.Text%2A>属性更改为 "**此按钮的文本属性具有长字符串。"** <xref:System.Windows.Forms.Button>

   提交更改时, <xref:System.Windows.Forms.Button>控件不会调整其自身的大小, 而是由控件的右边缘剪切文本。

6. <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>通过在"**属性**" 窗口中展开条目并将属性设置为**5**来更改属性。<xref:System.Windows.Forms.Control.Padding%2A>

   控件内部的文本在所有四个边都被剪切。

7. 将控件的<xref:System.Windows.Forms.Control.AutoSize%2A>属性更改为**true。** <xref:System.Windows.Forms.Button>

   <xref:System.Windows.Forms.Button>控件调整自身大小以包含整个字符串。 此外, 还会围绕文本添加填充, 从而导致<xref:System.Windows.Forms.Button>控件在四个方向上都展开。

8. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。 将其放置在窗体右下角附近。

9. 将<xref:System.Windows.Forms.Button>控件的属性值更改为<xref:System.Windows.Forms.Control.AutoSize%2A> true。

10. 将控件的<xref:System.Windows.Forms.Control.Anchor%2A>属性设置为<xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>。 <xref:System.Windows.Forms.Button>

11. 将控件的<xref:System.Windows.Forms.Control.Text%2A>属性更改为 "**此按钮的文本属性具有长字符串。"** <xref:System.Windows.Forms.Button>

   当你提交更改时, 控件会<xref:System.Windows.Forms.Button>向左调整控件的大小。 通常, 自动调整大小会使控件在其<xref:System.Windows.Forms.Control.Anchor%2A>属性设置的方向上增加。

## <a name="autosize-and-autosizemode-properties"></a>AutoSize 和 AutoSizeMode 属性

 某些控件支持`AutoSizeMode`属性, 这使你可以更精细地控制控件的自动调整大小行为。

### <a name="use-the-autosizemode-property"></a>使用 AutoSizeMode 属性

1. 从 <xref:System.Windows.Forms.Panel> “工具箱” **将** 控件拖到你的窗体上。

2. 将<xref:System.Windows.Forms.Panel>控件的属性的值设置为<xref:System.Windows.Forms.Control.AutoSize%2A> true。

3. 将控件从 " <xref:System.Windows.Forms.Panel>工具箱" 拖放到控件中。 <xref:System.Windows.Forms.Button>

4. 将控件放置在<xref:System.Windows.Forms.Panel>控件的右下角附近。 <xref:System.Windows.Forms.Button>

5. <xref:System.Windows.Forms.Panel>选择控件并抓住右下的大小调整控点。 将控件<xref:System.Windows.Forms.Panel>的大小调整为更大、更小。

   > [!NOTE]
   > 您可以随意调整<xref:System.Windows.Forms.Panel>控件大小, 但不能将其大小调整为小于<xref:System.Windows.Forms.Button>控件右下角的位置。 此行为由`AutoSizeMode`属性的默认值指定, <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>即。

6. 将<xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>控件的属性的值设置为。 `AutoSizeMode`

   控件自行调整大小以<xref:System.Windows.Forms.Button>包围控件。 <xref:System.Windows.Forms.Panel> 无法调整控件的<xref:System.Windows.Forms.Panel>大小。

7. 将控件拖动到<xref:System.Windows.Forms.Panel>控件的左上角。 <xref:System.Windows.Forms.Button>

   控件的大小调整<xref:System.Windows.Forms.Button>为控件的新位置。 <xref:System.Windows.Forms.Panel>

## <a name="next-steps"></a>后续步骤

在 Windows 窗体应用程序中排列控件还有很多其他布局功能。 下面是可以尝试的一些组合:

- 使用<xref:System.Windows.Forms.TableLayoutPanel>控件生成窗体。 有关详细信息, [请参阅演练:使用 TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)排列 Windows 窗体上的控件。 尝试更改<xref:System.Windows.Forms.TableLayoutPanel>控件的<xref:System.Windows.Forms.Control.Padding%2A>属性的值以及其子控件的<xref:System.Windows.Forms.Control.Margin%2A>属性。

- 使用<xref:System.Windows.Forms.FlowLayoutPanel>控件尝试相同的试验。 有关详细信息, [请参阅演练:使用 FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)排列 Windows 窗体上的控件。

- 尝试在<xref:System.Windows.Forms.Panel>控件中停靠子控件。 属性是对<xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>属性的更通用的实现, 你可以通过在<xref:System.Windows.Forms.Panel>控件中放置一个子控件并将子控件的<xref:System.Windows.Forms.Control.Dock%2A>属性设置为来自行满足这种情况。 <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.DockStyle.Fill>. 将控件的属性<xref:System.Windows.Forms.Control.Padding%2A>设置为不同的值并记下该效果。 <xref:System.Windows.Forms.Panel>

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [AutoSize 属性概述](autosize-property-overview.md)
- [演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [演练：使用对齐线排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
