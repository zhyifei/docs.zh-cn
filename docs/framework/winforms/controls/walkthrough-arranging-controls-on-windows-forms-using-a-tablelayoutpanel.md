---
title: 演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with TableLayoutPanel
- TableLayoutPanel control [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d474885e-12cc-4ab7-b997-2a23a643049b
ms.openlocfilehash: 7b7380690d8668f46b98272e1d42640f23679b19
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799112"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel"></a>演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件

某些应用程序需要这样一个窗体，该窗体的布局可在窗体重新调整大小或在内容更改大小时对自身进行排列。 当你需要动态布局并且不希望在代码中显式处理 <xref:System.Windows.Forms.Control.Layout> 事件时，请考虑使用布局面板。

<xref:System.Windows.Forms.FlowLayoutPanel> 控件和 <xref:System.Windows.Forms.TableLayoutPanel> 控件提供可用于排列窗体上的控件的直观方式。 两种控件均提供一种自动的可配置能力来控制包含在控件内的子控件的相对位置，并且两种控件均在运行时提供动态布局功能，以便它们可以在父窗体的尺寸更改时重新调整子控件的大小和对其进行重新定位。 布局面板可以嵌套在布局面板内，从而实现复杂的用户界面。

<xref:System.Windows.Forms.FlowLayoutPanel> 以特定的流向排列其内容：水平或垂直。 可从一行到下一行，或从一列到下列进行内容换行。 还可以剪切内容，而不是进行换行。 有关详细信息，请参阅[演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)。

<xref:System.Windows.Forms.TableLayoutPanel> 在网格中排列其内容，提供类似于 HTML \<table > 元素的功能。 <xref:System.Windows.Forms.TableLayoutPanel> 控件允许您在网格布局中放置控件，而无需精确指定每个控件的位置。 其单元格排列为行和列，并且这些行和列可具有不同的大小。 可以跨行和列合并单元。 单元可以包含表单可以包含的任何内容，并在大多数其他方面作为容器。

<xref:System.Windows.Forms.TableLayoutPanel> 控件还在运行时提供了按比例调整大小的功能，因此，在调整窗体大小时，布局会平滑。 这使得 <xref:System.Windows.Forms.TableLayoutPanel> 控件非常适合用于数据输入窗体和本地化的应用程序等目的。 有关详细信息，请参阅[演练：创建用于数据输入的大小可调的 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))和[演练：创建可本地化的 windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))。

通常，不应将 <xref:System.Windows.Forms.TableLayoutPanel> 控件用作整个布局的容器。 使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件向布局的各个部分提供按比例调整大小的功能。

本演练涉及以下任务：

- 创建 Windows 窗体项目

- 在行和列中排列控件

- 设置行和列属性

- 使用控件跨越行和列

- 自动处理溢出

- 通过在工具箱中双击控件将其插入

- 通过绘制控件轮廓将其插入

- 将现有控件重新分配给另一个父控件

完成上述操作后，你将会了解这些重要布局功能所发挥的作用。

## <a name="creating-the-project"></a>创建项目

第一步是创建项目并设置窗体。

#### <a name="to-create-the-project"></a>要创建项目

1. 创建名为 "TableLayoutPanelExample" 的 Windows 应用程序项目。 有关详细信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)。

2. 在**Windows** **窗体设计器**中选择窗体。

## <a name="arranging-controls-in-rows-and-columns"></a>在行和列中排列控件

利用 <xref:System.Windows.Forms.TableLayoutPanel> 控件，可以轻松地将控件排列为行和列。

#### <a name="to-arrange-controls-in-rows-and-columns-using-a-tablelayoutpanel"></a>使用 TableLayoutPanel 在行和列中排列控件

1. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。 请注意，默认情况下，<xref:System.Windows.Forms.TableLayoutPanel> 控件具有四个单元。

2. 将 <xref:System.Windows.Forms.Button> 控件从**工具箱**拖动到 <xref:System.Windows.Forms.TableLayoutPanel> 控件，并将其放入其中一个单元格。 请注意，<xref:System.Windows.Forms.Button> 控件是在所选单元中创建的。

3. 将 "**工具箱**" 中的三个 <xref:System.Windows.Forms.Button> 控件拖动到 <xref:System.Windows.Forms.TableLayoutPanel> 控件中，以便每个单元格都包含一个按钮。

4. 抓住两列之间的垂直大小调整控点，并将其向左移动。 请注意，第一列中的 <xref:System.Windows.Forms.Button> 控件会调整到较小的宽度，而第二列中 <xref:System.Windows.Forms.Button> 控件的大小不变。

5. 抓住两列之间的垂直大小调整控点，并将其向右移动。 请注意，第一列中的 <xref:System.Windows.Forms.Button> 控件将恢复为其原始大小，而第二列中的 <xref:System.Windows.Forms.Button> 控件将向右移动。

6. 向上和向下移动水平大小调整控点，查看面板中的控件效果。

## <a name="positioning-controls-within-cells-using-docking-and-anchoring"></a>使用停靠和锚定定位单元中的控件

<xref:System.Windows.Forms.TableLayoutPanel> 中的子控件的定位行为与其他容器控件中的行为不同。 子控件的停靠行为与其他容器控件的行为相同。

#### <a name="positioning-controls-within-cells"></a>定位单元中的控件

1. 选择第一个 <xref:System.Windows.Forms.Button> 控件。 将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值更改为 <xref:System.Windows.Forms.DockStyle.Fill>。 请注意，<xref:System.Windows.Forms.Button> 控件将展开以填充单元格。

2. 选择另一个 <xref:System.Windows.Forms.Button> 控件。 将其 <xref:System.Windows.Forms.Control.Anchor%2A> 属性的值更改为 <xref:System.Windows.Forms.AnchorStyles.Right>。 请注意，它将被移动，使其右边框靠近单元格的右边框。 边界之间的距离是 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性与面板的 <xref:System.Windows.Forms.Control.Padding%2A> 属性之和。

3. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性的值更改为 <xref:System.Windows.Forms.AnchorStyles.Right> 和 <xref:System.Windows.Forms.AnchorStyles.Left>。 请注意，控件的大小调整为单元格的宽度，并考虑 <xref:System.Windows.Forms.Control.Margin%2A> 值和 <xref:System.Windows.Forms.Control.Padding%2A> 值。

4. 对 <xref:System.Windows.Forms.AnchorStyles.Top> 和 <xref:System.Windows.Forms.AnchorStyles.Bottom> 样式重复步骤2和3。

## <a name="setting-row-and-column-properties"></a>设置行和列属性

您可以通过使用 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 和 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 集合来设置行和列的单个属性。

#### <a name="to-set-row-and-column-properties"></a>设置行和列属性

1. 选择**Windows 窗体设计器**中的 "<xref:System.Windows.Forms.TableLayoutPanel>" 控件。

2. 在 "**属性**" 窗口中，通过![单击 "**列**" 项旁边的 "Visual Studio](./media/visual-studio-ellipsis-button.png)" 按钮的 "属性窗口的省略号按钮（...）来打开 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 集合。

3. 选择第一列，并将其 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 属性的值更改为 "<xref:System.Windows.Forms.SizeType.AutoSize>"。 单击 **"确定"** 以接受更改。 请注意，第一列的宽度会缩小以适应 <xref:System.Windows.Forms.Button> 控件。 另请注意，列的宽度不可调整大小。

4. 在 "**属性**" 窗口中，打开 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 集合并选择第一列。 将其 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 属性的值更改为 <xref:System.Windows.Forms.SizeType.Percent>。 单击 **"确定"** 以接受更改。 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大的宽度，并注意第一列的宽度将展开。 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件调整为较小的宽度，并注意，第一列中的按钮将调整大小以适合该单元格。 另请注意，列的宽度可调整大小。

5. 在 "**属性**" 窗口中，打开 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 集合，然后选择所有列出的列。 将每个 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 属性的值设置为 <xref:System.Windows.Forms.SizeType.Percent>。 单击 **"确定"** 以接受更改。 对 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 集合重复此操作。

6. 抓住其中一个角调整控点，并调整 <xref:System.Windows.Forms.TableLayoutPanel> 控件的宽度和高度。 请注意，在 <xref:System.Windows.Forms.TableLayoutPanel> 控件大小发生变化时，将调整行和列的大小。 另请注意，行和列可通过水平和垂直大小调整控点进行调整。

## <a name="spanning-rows-and-columns-with-a-control"></a>使用控件跨越行和列

<xref:System.Windows.Forms.TableLayoutPanel> 控件在设计时向控件添加几个新属性。 其中两个属性都 `RowSpan` 和 `ColumnSpan`。 您可以使用这些属性使控件跨越多个行或列。

#### <a name="to-span-rows-and-columns-with-a-control"></a>跨控件拆分行和列

1. 选择第一行和第一列中的 <xref:System.Windows.Forms.Button> 控件。

2. 在 "**属性**" 窗口中，将 "`ColumnSpan`" 属性的值更改为 " **2**"。 请注意，<xref:System.Windows.Forms.Button> 控件将填充第一列和第二列。 另请注意，已添加额外行来容纳此更改。

3. 对于 `RowSpan` 属性，请重复步骤2。

## <a name="inserting-controls-by-double-clicking-them-in-the-toolbox"></a>通过在工具箱中双击控件将其插入

可通过在 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **中双击控件来填充**控件。

#### <a name="to-insert-controls-by-double-clicking-in-the-toolbox"></a>若要通过在工具箱中双击控件将其插入

1. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。

2. 在“工具箱” <xref:System.Windows.Forms.Button>**中，双击**控件图标。 请注意，新的按钮控件出现在 <xref:System.Windows.Forms.TableLayoutPanel> 控件的第一个单元格中。

3. 在 **“工具箱”** 中再双击几个控件。 请注意，新控件连续出现在 <xref:System.Windows.Forms.TableLayoutPanel> 控件的未占用单元格中。 另请注意，如果没有打开的单元格，则 <xref:System.Windows.Forms.TableLayoutPanel> 控件将展开以容纳新的控件。

## <a name="automatic-handling-of-overflows"></a>自动处理溢出

将控件插入 <xref:System.Windows.Forms.TableLayoutPanel> 控件中时，可能会对新控件用尽空单元格。 <xref:System.Windows.Forms.TableLayoutPanel> 控件通过增加单元格数来自动处理这种情况。

#### <a name="to-observe-automatic-handling-of-overflows"></a>观察溢出的自动处理

1. 如果 <xref:System.Windows.Forms.TableLayoutPanel> 控件中仍有空单元格，则继续插入新的 <xref:System.Windows.Forms.Button> 控件，直到 <xref:System.Windows.Forms.TableLayoutPanel> 控件已满。

2. <xref:System.Windows.Forms.TableLayoutPanel> 控件填满后，双击**工具箱**中的 "<xref:System.Windows.Forms.Button>" 图标以插入另一个 <xref:System.Windows.Forms.Button> 控件。 请注意，<xref:System.Windows.Forms.TableLayoutPanel> 控件创建新的单元格来容纳新的控件。 插入更多控件并观察调整大小行为。

3. 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的 <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> 属性值更改为 <xref:System.Windows.Forms.TableLayoutPanelGrowStyle.FixedSize>。 双击**工具箱**中的 "<xref:System.Windows.Forms.Button>" 图标以插入 <xref:System.Windows.Forms.Button> 控件，直到 <xref:System.Windows.Forms.TableLayoutPanel> 控件已满。 再次双击**工具箱**中的 <xref:System.Windows.Forms.Button> 图标。 请注意，你将收到一条错误消息，该**Windows 窗体设计器**通知你无法创建其他行和列。

## <a name="inserting-a-control-by-drawing-its-outline"></a>通过绘制控件轮廓将其插入

你可以通过在单元格中绘制控件轮廓将控件插入 <xref:System.Windows.Forms.TableLayoutPanel> 控件并指定其大小。

#### <a name="to-insert-a-control-by-drawing-its-outline"></a>通过绘制控件轮廓插入控件

1. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。

2. 在“工具箱”中，单击 <xref:System.Windows.Forms.Button> 控件图标。 请勿将其拖到窗体上。

3. 将鼠标指针移到 <xref:System.Windows.Forms.TableLayoutPanel> 控件上。 请注意，指针会更改为十字形，同时会附上 <xref:System.Windows.Forms.Button> 控件图标。

4. 单击并按住鼠标按钮。

5. 拖动鼠标指针以绘制 <xref:System.Windows.Forms.Button> 控件的轮廓。 当获得所需大小时，释放鼠标。 请注意，<xref:System.Windows.Forms.Button> 控件是在您绘制控件轮廓的单元格内创建的。

## <a name="multiple-controls-within-cells-are-not-permitted"></a>不允许单元中有多个控件

<xref:System.Windows.Forms.TableLayoutPanel> 控件每个单元格只能包含一个子控件。

#### <a name="to-demonstrate-that-multiple-controls-within-cells-are-not-permitted"></a>演示不允许单元格中的多个控件

- 将 <xref:System.Windows.Forms.Button> 控件从 "**工具箱**" 拖动到 "<xref:System.Windows.Forms.TableLayoutPanel>" 控件，并将其放入某个已占用的单元格。 请注意，<xref:System.Windows.Forms.TableLayoutPanel> 控件不允许将 <xref:System.Windows.Forms.Button> 控件放入已占用的单元格。

## <a name="swapping-controls"></a>交换控件

利用 <xref:System.Windows.Forms.TableLayoutPanel> 控件，可以交换占用两个不同单元格的控件。

#### <a name="to-swap-controls"></a>交换控件

- 将一个 <xref:System.Windows.Forms.Button> 控件从一个被占用的单元格拖放到另一个占用的单元格上。 请注意，这两个控件将从一个单元格移到另一个单元格。

## <a name="next-steps"></a>后续步骤

可使用布局面板和控件的组合实现复杂布局。 有关进一步探索的建议包括：

- 尝试将其中一个 <xref:System.Windows.Forms.Button> 控件调整到更大的大小，并注意对布局的影响。

- 将选择的多个控件粘贴到 <xref:System.Windows.Forms.TableLayoutPanel> 控件中，并注意控件的插入方式。

- 布局面板可以包含其他布局面板。 试验将 <xref:System.Windows.Forms.TableLayoutPanel> 控件放入现有控件。

- 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件停靠到父窗体。 调整窗体大小，并注意对布局产生的效果。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [演练：使用对齐线在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [演练：创建可根据数据输入需要调整大小的 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))
- [演练：创建可本地化的 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))
- [有关 TableLayoutPanel 控件的最佳做法](best-practices-for-the-tablelayoutpanel-control.md)
- [AutoSize 属性概述](autosize-property-overview.md)
- [如何：在 Windows 窗体上停靠控件](how-to-dock-controls-on-windows-forms.md)
- [如何：在 Windows 窗体上锚定控件](how-to-anchor-controls-on-windows-forms.md)
- [演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局](windows-forms-controls-padding-autosize.md)
