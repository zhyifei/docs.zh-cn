---
title: 演练：使用对齐线在 Windows 窗体上排列控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 3ce6c250fadbb56b341d5e8dec3a9cb9d28940fe
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040260"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a>演练：使用对齐线在 Windows 窗体上排列控件
在窗体上精确地放置控件对于许多应用程序而言是高优先级。 Windows 窗体设计器提供了许多布局工具来实现此目的。 最重要的一项是<xref:System.Windows.Forms.Design.Behavior.SnapLine>功能。

 对齐线可精确显示控件与其他控件的对齐位置。 它们还显示了建议的距离, 如 Windows 用户界面准则所指定。 有关详细信息, 请参阅[用户界面设计和开发](https://go.microsoft.com/FWLink/?LinkId=83878)。

 利用对齐线, 可以轻松地对齐控件, 实现简洁、专业的外观和行为 (外观)。

 本演练涉及以下任务：

- 创建 Windows 窗体项目

- 使用对齐线的间距和对齐控件

- 对齐窗体和容器边距

- 对齐分组控件

- 使用对齐线通过大纲显示控件

- 从工具箱拖动控件时使用对齐线

- 使用对齐线调整控件大小

- 将标签与控件的文本对齐

- 通过键盘导航使用对齐线

- 对齐线和布局面板

- 禁用对齐线

 完成后, 你将了解对齐线功能所扮演的布局角色。

## <a name="creating-the-project"></a>创建项目
 第一步是创建项目并设置窗体。

### <a name="to-create-the-project"></a>要创建项目

1. 创建名为 "SnaplineExample" 的基于 Windows 的应用程序项目 (**文件** > **新** > **项目** > **视觉对象C#** 或经典**Visual Basic** > 桌面 > **Windows 窗体应用程序**)。

2. 在窗体设计器中选择窗体。

## <a name="spacing-and-aligning-controls-using-snaplines"></a>使用对齐线的间距和对齐控件
 "对齐线" 为您显示窗体上控件的对齐方式。 当您将选定控件或控件移动到与另一个控件或控件集对齐的位置时, 它们将显示。 在将其移到其他控件之后, 你的选择将 "对齐" 到建议的位置。

### <a name="to-arrange-controls-using-snaplines"></a>使用对齐线排列控件

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。

2. <xref:System.Windows.Forms.Button>将控件移动到窗体的右下角。 请注意, 当<xref:System.Windows.Forms.Button>控件接近窗体的下边框和右边框时显示的对齐线。 这些对齐线显示控件边框与窗体边框之间的建议距离。

3. 围绕窗体的边框移动控件,并注意对齐线出现的位置。<xref:System.Windows.Forms.Button> 完成后, 将<xref:System.Windows.Forms.Button>控件移动到窗体中心附近。

4. 将另<xref:System.Windows.Forms.Button>一个控件从**工具箱**拖到窗体上。

5. 移动第二<xref:System.Windows.Forms.Button>个控件, 直到它接近第一个控件。 请注意, 在这两个按钮的文本基线上出现的对齐线, 并注意您正在移动的控件将对齐到与其他控件完全相同的位置。

6. 移动第二<xref:System.Windows.Forms.Button>个控件, 直到它直接位于第一个控件的上方。 请注意在这两个按钮的左右边缘上出现的对齐线, 并注意您正在移动的控件将对齐到与其他控件完全对齐的位置。

7. 选择其中一个<xref:System.Windows.Forms.Button>控件, 并将其移动到另一个控件, 直到它们接近。 请注意它们之间出现的对齐线。 此距离是控件边框之间建议的距离。 另请注意, 正在移动的控件将对齐到此位置。

8. 将两<xref:System.Windows.Forms.Panel>个控件从**工具箱**拖到窗体上。

9. 移动其中一个<xref:System.Windows.Forms.Panel>控件, 直到它接近于第一个控件。 请注意沿两个控件的上边缘和下边缘显示的对齐线, 并注意您正在移动的控件对齐到与其他控件完全相同的位置。

## <a name="aligning-to-form-and-container-margins"></a>对齐窗体和容器边距
 对齐线有助于以一致的方式将控件与窗体和容器边距对齐。

### <a name="to-align-controls-to-form-and-container-margins"></a>将控件与窗体和容器边距对齐

1. 选择其中一个<xref:System.Windows.Forms.Button>控件, 并将其移动到窗体的右边框, 直到出现对齐线。 对齐线与右边框的距离是控件的<xref:System.Windows.Forms.Control.Margin%2A>属性和窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性值之和。

> [!NOTE]
>  如果窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性设置为 0, 0, 0, 0, 则 Windows 窗体设计器为窗体提供一个阴影<xref:System.Windows.Forms.Control.Padding%2A>值9、9、9、9。 若要重写此行为, 请指定0、0、0、0以外的值。

1. 通过在 "**属性**" <xref:System.Windows.Forms.Button>窗口中<xref:System.Windows.Forms.Control.Margin%2A>展开<xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Padding.All%2A>条目并将属性设置为 0, 可更改控件的属性的值。 有关详细信息, [请参阅演练:通过填充、边距和 AutoSize 属性](windows-forms-controls-padding-autosize.md)对 Windows 窗体控件进行布局。

2. <xref:System.Windows.Forms.Button>将控件移动到窗体的右边框附近, 直到出现对齐线。 此距离现在由窗体的<xref:System.Windows.Forms.Control.Padding%2A>属性的值提供。

3. 从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。

4. 通过在 "**属性**" <xref:System.Windows.Forms.GroupBox>窗口中<xref:System.Windows.Forms.Control.Padding%2A>展开<xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Padding.All%2A>条目并将属性设置为 10, 来更改控件的属性的值。

5. 将控件从 " <xref:System.Windows.Forms.GroupBox>工具箱" 拖放到控件中。 <xref:System.Windows.Forms.Button>

6. 将控件移动到<xref:System.Windows.Forms.GroupBox>控件的右边框附近, 直到出现对齐线。 <xref:System.Windows.Forms.Button> 移动控件<xref:System.Windows.Forms.GroupBox>内的控件,并注意对齐线<xref:System.Windows.Forms.Button>出现的位置。

## <a name="aligning-to-grouped-controls"></a>对齐分组控件
 您可以使用对齐线对齐<xref:System.Windows.Forms.GroupBox>控件中的分组控件和控件。

### <a name="to-align-to-grouped-controls"></a>对齐分组控件

1. 选择窗体上的两个控件。 移动所选内容, 并记下所选内容与其他控件之间出现的对齐线。

2. 从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。

3. 将控件从 " <xref:System.Windows.Forms.GroupBox>工具箱" 拖放到控件中。 <xref:System.Windows.Forms.Button>

4. 选择其中一个<xref:System.Windows.Forms.Button>控件, 并在<xref:System.Windows.Forms.GroupBox>控件上移动它。 请注意<xref:System.Windows.Forms.GroupBox>控件边缘上出现的对齐线。 另请注意控件所包含<xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox>控件边缘上出现的对齐线。 容器控件的子级控件也支持对齐线。

## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a>使用对齐线通过大纲显示控件
 当你首次将控件放置在窗体上时, 对齐线可帮助你对齐控件。

### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a>通过勾画控件大小来使用对齐线放置控件

1. 在“工具箱”中，单击 <xref:System.Windows.Forms.Button> 控件图标。 请勿将其拖到窗体上。

2. 将鼠标指针移动到窗体的设计图面上。 请注意，指针会更改为十字形，同时会附上 <xref:System.Windows.Forms.Button> 控件图标。 另请注意为<xref:System.Windows.Forms.Button>控件建议对齐位置的对齐线。

3. 单击并按住鼠标按钮。

4. 在窗体上拖动鼠标指针。 请注意, 会绘制一个轮廓, 指示控件的位置和大小。

5. 拖动指针, 直到它与窗体上的另一个控件对齐。 请注意, 将显示一条对齐线以指示对齐方式。

6. 释放鼠标按钮。 控件在由轮廓指示的位置和大小创建。

## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a>从工具箱拖动控件时使用对齐线
 当你将控件从 "**工具箱**" 拖到窗体上时, 对齐线可帮助你对齐控件。

### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a>从工具箱拖动控件时使用对齐线

1. 将控件从 "工具箱" 拖到窗体上, 但不释放鼠标按钮。 <xref:System.Windows.Forms.Button>

2. 将鼠标指针移动到窗体的设计图面上。 请注意, 指针会更改以指示将创建新<xref:System.Windows.Forms.Button>控件的位置。

3. 在窗体上拖动鼠标指针。 请注意显示的对齐线, 用于建议<xref:System.Windows.Forms.Button>控件的对齐位置。 查找与其他控件对齐的位置。

4. 释放鼠标按钮。 控件将在对齐线指示的位置创建。

## <a name="resizing-controls-using-snaplines"></a>使用对齐线调整控件大小
 对齐线有助于调整控件的大小。

### <a name="to-resize-a-control-using-snaplines"></a>使用对齐线调整控件大小

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。

2. 通过获取一个角大小调整控点并拖动来调整控件的大小。<xref:System.Windows.Forms.Button> 有关详细信息，请参阅[如何：Windows 窗体](how-to-resize-controls-on-windows-forms.md)上的调整控件大小。

3. 拖动调整大小控点, 直到其中<xref:System.Windows.Forms.Button>一个控件的边框与另一个控件对齐。 请注意, 会显示对齐线。 另请注意, 大小调整控点与对齐线指示的位置对齐。

4. 按不同方向调整控件大小,并将大小调整控点与不同控件对齐。<xref:System.Windows.Forms.Button> 请注意对齐线如何出现在各种方向上以指示对齐方式。

## <a name="aligning-a-label-to-a-controls-text"></a>将标签与控件的文本对齐
 某些控件提供了用于将其他控件对齐到显示文本的对齐线。

### <a name="to-align-a-label-to-a-controls-text"></a>将标签与控件的文本对齐

1. 从 <xref:System.Windows.Forms.TextBox> “工具箱” **将** 控件拖到你的窗体上。 将<xref:System.Windows.Forms.TextBox>控件放到窗体上时, 单击智能标记标志符号, 然后选择 "**将文本设置为 textBox1** " 选项。 有关详细信息, [请参阅演练:使用 Windows 窗体控件](performing-common-tasks-using-smart-tags-on-wf-controls.md)上的智能标记执行常见任务。

2. 从 <xref:System.Windows.Forms.Label> “工具箱” **将** 控件拖到你的窗体上。

3. 将 <xref:System.Windows.Forms.Label> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。 请注意, 控件的边框会调整以适应显示文本。

4. 将控件移动到<xref:System.Windows.Forms.TextBox>控件的左侧, 使其与<xref:System.Windows.Forms.TextBox>控件的下边缘对齐。 <xref:System.Windows.Forms.Label> 请注意在两个控件的下边缘显示的对齐线。

5. 稍微向上移动<xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.TextBox>控件, 直到文本和文本对齐。 <xref:System.Windows.Forms.Label> 请注意显示的样式不同的对齐线, 指示两个控件的文本字段对齐的时间。

## <a name="using-snaplines-with-keyboard-navigation"></a>通过键盘导航使用对齐线
 当使用键盘的箭头键排列控件时, 对齐线可帮助您对齐控件。

### <a name="to-use-snaplines-with-keyboard-navigation"></a>将对齐线用于键盘导航

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。 将其放在窗体的左上角。

2. 按 CTRL + 向下键。 请注意, 控件向下移动到第一个可用的水平对齐位置。

3. 按 CTRL + 向下键, 直到控件到达窗体的底部。 请注意, 它在窗体中向下移动时所占据的位置。

4. 按 CTRL + 向右键。 请注意, 控件在窗体上移动到第一个可用的垂直对齐位置。

5. 按 CTRL + 向右键直到控件到达窗体的一侧。 请注意, 它在窗体中移动时所占据的位置。

6. 使用箭头键的组合在窗体周围移动控件。 请注意控件占据的位置以及伴随控件的对齐线。

7. 按 SHIFT + 任意箭头键可按一个<xref:System.Windows.Forms.Button>像素的增量调整控件的大小。

8. 按 CTRL + SHIFT + 任意箭头键可在对齐<xref:System.Windows.Forms.Button>线增量中调整控件的大小。

## <a name="snaplines-and-layout-panels"></a>对齐线和布局面板
 布局面板中已禁用对齐线。

### <a name="to-selectively-disable-snaplines"></a>有选择地禁用对齐线

1. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。

2. 在“工具箱” <xref:System.Windows.Forms.Button>**中，双击**控件图标。 请注意, 新的按钮控件出现在<xref:System.Windows.Forms.TableLayoutPanel>控件的第一个单元格中。

3. 再次双击**工具箱**中<xref:System.Windows.Forms.Button>的控件图标。 这会在<xref:System.Windows.Forms.TableLayoutPanel>控件中保留一个空单元。

4. 将控件从 "**工具箱**" 拖到<xref:System.Windows.Forms.TableLayoutPanel>控件的空单元中。 <xref:System.Windows.Forms.Button> 请注意, 不会显示对齐线。

5. 将控件拖出<xref:System.Windows.Forms.TableLayoutPanel>控件<xref:System.Windows.Forms.TableLayoutPanel> , 并将其移动到控件上。 <xref:System.Windows.Forms.Button> 请注意, 对齐线将再次出现。

## <a name="disabling-snaplines"></a>禁用对齐线
 默认情况下, 对齐线已打开。 您可以有选择地禁用对齐线, 也可以在设计环境中禁用它。

### <a name="to-selectively-disable-snaplines"></a>有选择地禁用对齐线

- 按 ALT 键, 同时在窗体中移动控件。

     请注意, 不会显示对齐线, 并且控件不会与任何可能的对齐位置对齐。

### <a name="to-disable-snaplines-in-the-design-environment"></a>禁用设计环境中的对齐线

1. 从 "**工具**" 菜单中, 打开 "**选项**" 对话框。 打开 "Windows 窗体设计器" 对话框。 有关详细信息, 请参阅[常规、Windows 窗体设计器、"选项" 对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))。

2. 选择 "**常规**" 节点。 在 "**布局模式**" 部分中, 将所选内容从**对齐线**更改为 "**对齐**"。

3. 单击 "确定" 以应用设置。

4. 选择窗体上的控件, 并将其移动到其他控件上。 请注意, 不会显示对齐线。

## <a name="next-steps"></a>后续步骤
 对齐线提供了在窗体上对齐控件的直观方式。 有关进一步探索的建议包括：

- 尝试将<xref:System.Windows.Forms.GroupBox>控件嵌套在另<xref:System.Windows.Forms.GroupBox>一个控件中。 将控件置于子<xref:System.Windows.Forms.GroupBox>控件内, 并将其放在父<xref:System.Windows.Forms.GroupBox>控件中。 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Button>移动控件以查看对齐线跨容器边界的方式。

- 创建列<xref:System.Windows.Forms.TextBox>控件和相应的<xref:System.Windows.Forms.Label>控件列。 将<xref:System.Windows.Forms.Label> `true`控件的属性值设置为。 <xref:System.Windows.Forms.Control.AutoSize%2A> 使用对齐线移动<xref:System.Windows.Forms.Label>控件, 使其显示的文本与<xref:System.Windows.Forms.TextBox>控件中的文本对齐。

 有关 Windows 用户界面设计的信息, 请参阅*Microsoft Windows 用户体验, Microsoft Windows 用户体验, 用户界面开发人员和设计人员的官方准则*, 华盛顿州:微软出版社, 1999。 (USBN:0-7356-0566-1)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [演练：使用 FlowLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [演练：使用 TableLayoutPanel 排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [演练：通过填充、边距和 AutoSize 属性排放 Windows 窗体控件](windows-forms-controls-padding-autosize.md)
- [在 Windows 窗体上排列控件](arranging-controls-on-windows-forms.md)
