---
title: ToolStrip 控件体系结构
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: d0a1441e9bae8d2c1f938e7399c11e736708da4d
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363823"
---
# <a name="toolstrip-control-architecture"></a>ToolStrip 控件体系结构

<xref:System.Windows.Forms.ToolStrip> 和<xref:System.Windows.Forms.ToolStripItem>类提供了一个灵活、可扩展的系统来显示工具栏、状态和菜单项。 这些类都包含在<xref:System.Windows.Forms>命名空间中, 并且通常以 "ToolStrip" 前缀 ( <xref:System.Windows.Forms.ToolStripOverflow>如) 或 "带区后缀" (如<xref:System.Windows.Forms.MenuStrip>) 命名。

## <a name="toolstrip"></a>ToolStrip

以下主题描述<xref:System.Windows.Forms.ToolStrip>和派生自它的控件。

<xref:System.Windows.Forms.ToolStrip>是<xref:System.Windows.Forms.MenuStrip>、 <xref:System.Windows.Forms.StatusStrip>和的抽象基类。<xref:System.Windows.Forms.ContextMenuStrip> 以下对象模型显示<xref:System.Windows.Forms.ToolStrip>了继承层次结构。

![显示 ToolStrip 对象模型的关系图。](./media/toolstrip-control-architecture/toolstrip-object-model.gif)

你可以<xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip.Items%2A>通过集合访问中的所有项。 你可以<xref:System.Windows.Forms.ToolStripDropDownItem> <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>通过集合访问中的所有项。 在从派生的<xref:System.Windows.Forms.ToolStrip>类中, 还可以<xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A>使用属性来仅访问当前显示的那些项。 这些是当前不在溢出菜单中的项。

以下各项专用于在所有方向上无缝<xref:System.Windows.Forms.ToolStripSystemRenderer>使用<xref:System.Windows.Forms.ToolStripProfessionalRenderer>和。 默认情况下, 它们在设计时可用于<xref:System.Windows.Forms.ToolStrip>控件:

- <xref:System.Windows.Forms.ToolStripButton>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="menustrip"></a>MenuStrip

<xref:System.Windows.Forms.MenuStrip>是取代<xref:System.Windows.Forms.MainMenu>的顶级容器。 它还提供密钥处理和多文档界面 (MDI) 功能。 <xref:System.Windows.Forms.ToolStripDropDownItem>功能和<xref:System.Windows.Forms.ToolStripMenuItem>一起<xref:System.Windows.Forms.ToolStripItem>工作<xref:System.Windows.Forms.MenuStrip>, 尽管它们是从派生的。

以下各项专用于在所有方向上无缝<xref:System.Windows.Forms.ToolStripSystemRenderer>使用<xref:System.Windows.Forms.ToolStripProfessionalRenderer>和。 默认情况下, 它们在设计时可用于<xref:System.Windows.Forms.MenuStrip>控件:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="statusstrip"></a>StatusStrip

<xref:System.Windows.Forms.StatusStrip><xref:System.Windows.Forms.StatusBar>替换控件。 的<xref:System.Windows.Forms.StatusStrip>特殊功能包括自定义表布局、支持窗体的大小调整和移动手柄`Spring`以及<xref:System.Windows.Forms.ToolStripStatusLabel>属性 (允许自动填充可用空间)。

以下各项专用于在所有方向上无缝<xref:System.Windows.Forms.ToolStripSystemRenderer>使用<xref:System.Windows.Forms.ToolStripProfessionalRenderer>和。 默认情况下, 它们在设计时可用于<xref:System.Windows.Forms.StatusStrip>控件:

- <xref:System.Windows.Forms.ToolStripStatusLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripProgressBar>

### <a name="contextmenustrip"></a>ContextMenuStrip

<xref:System.Windows.Forms.ContextMenuStrip> 替代 <xref:System.Windows.Forms.ContextMenu>。 您可以将<xref:System.Windows.Forms.ContextMenuStrip>与任何控件相关联, 然后右键单击鼠标右键会自动显示上下文菜单 (或快捷菜单)。 您可以<xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.ToolStripDropDown.Show%2A>使用方法以编程方式显示。 <xref:System.Windows.Forms.ContextMenuStrip>支持可取消<xref:System.Windows.Forms.ToolStripDropDown.Closing>的和事件来处理动态填充和多重单击方案。 <xref:System.Windows.Forms.ToolStripDropDown.Opening> <xref:System.Windows.Forms.ContextMenuStrip>支持图像、菜单项的检查状态、文本、访问键、快捷方式和级联菜单。

以下各项专用于在所有方向上无缝<xref:System.Windows.Forms.ToolStripSystemRenderer>使用<xref:System.Windows.Forms.ToolStripProfessionalRenderer>和。 默认情况下, 它们在设计时可用于<xref:System.Windows.Forms.ContextMenuStrip>控件:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="toolstrip-generic-features"></a>ToolStrip 一般功能

以下主题介绍了<xref:System.Windows.Forms.ToolStrip>和派生的控件的通用功能。

#### <a name="painting"></a>绘制

可以通过多种方式在控件<xref:System.Windows.Forms.ToolStrip>中执行自定义绘制。 与其他 Windows 窗体控件一样, 和<xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripItem>都具有可重`OnPaint`写的`Paint`方法和事件。 与常规绘制一样, 坐标系统是相对于控件的工作区的;也就是说, 控件的左上角是 0, 0。 的事件和`OnPaint` 方法<xref:System.Windows.Forms.ToolStripItem>的行为类似于其他控件绘制事件。 `Paint`

<xref:System.Windows.Forms.ToolStrip>控件还<xref:System.Windows.Forms.ToolStripRenderer>通过类提供对项和容器的呈现的更精细的访问, 该类具有可重写的方法, 用于绘制背景、项背景、项图像、项箭头、项文本和边框<xref:System.Windows.Forms.ToolStrip>。 这些方法的事件自变量会公开几个属性, 如矩形、颜色和文本格式, 你可以根据需要进行调整。

若要仅调整项绘制方式的几个方面, 通常会重写<xref:System.Windows.Forms.ToolStripRenderer>。

如果你正在编写一个新项并想要控制绘制的所有方面, 则重写`OnPaint`方法。 从中`OnPaint`, 你可以使用中的<xref:System.Windows.Forms.ToolStripRenderer>方法。

默认情况下, <xref:System.Windows.Forms.ToolStrip>使用<xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>设置进行双缓冲。

#### <a name="parenting"></a>父级

在<xref:System.Windows.Forms.ToolStrip>控件中, 容器所有权和父级的概念比其他 Windows 窗体容器控件更复杂。 这对于支持动态方案 (如溢出)、跨多个<xref:System.Windows.Forms.ToolStrip>项共享下拉项以及支持<xref:System.Windows.Forms.ContextMenuStrip>从控件生成的是必需的。

下表描述了与父级相关的成员, 并说明了它们的用法。

- <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>访问作为下拉项的源的项。 这类似<xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>于, 但它不返回控件, 而是<xref:System.Windows.Forms.ToolStripItem>返回。

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>确定<xref:System.Windows.Forms.ContextMenuStrip>当多个控件共享同一<xref:System.Windows.Forms.ContextMenuStrip>时哪个控件是的源。

- <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>是<xref:System.Windows.Forms.ToolStripItem.Parent%2A>属性的只读访问器。 父级不同于所有者, 因为父对象表示在其中显示项的<xref:System.Windows.Forms.ToolStrip>返回的当前 (可能在溢出区中)。

- <xref:System.Windows.Forms.ToolStripItem.Owner%2A>返回其项集合包含当前<xref:System.Windows.Forms.ToolStripItem>的。 <xref:System.Windows.Forms.ToolStrip> 这是在顶级<xref:System.Windows.Forms.ToolStrip.ImageList%2A> <xref:System.Windows.Forms.ToolStrip>引用或其他属性的最佳方式, 无需编写用于处理溢出的特殊代码。

#### <a name="behavior-of-inherited-controls"></a>继承控件的行为

以下控件将在继承中使用时被锁定:

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.ToolStripPanel>, 其中包括<xref:System.Windows.Forms.ToolStripContainer>和各个<xref:System.Windows.Forms.ToolStripPanel>控件中的面板。

例如, 使用上一列表中的一个或多个控件创建新的 Windows 窗体应用程序。 将一个或多个控件的访问修饰符设置`public`为`protected`或, 然后生成项目。 添加从第一个窗体继承的窗体, 然后选择继承的控件。 控件显示为锁定状态, 其行为与访问修饰符的`private`行为相同。

#### <a name="toolstripcontainer-support-of-inheritance"></a>对继承的 ToolStripContainer 支持

<xref:System.Windows.Forms.ToolStripContainer>控件支持限制的继承方案, 类似于以下示例:

1. 创建新的 Windows 窗体应用程序。

2. 在窗体上添加一个 <xref:System.Windows.Forms.ToolStripContainer> 控件。

3. 将的访问修饰符<xref:System.Windows.Forms.ToolStripContainer>设置为`public`或`protected`。

4. 将<xref:System.Windows.Forms.ToolStrip>、 <xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStripContainer>控件的任意组合<xref:System.Windows.Forms.ContextMenuStrip>添加到的区域。

5. 生成项目。

6. 添加从第一个窗体继承的窗体。

7. 选择窗体<xref:System.Windows.Forms.ToolStripContainer>上继承的。

#### <a name="inherited-behavior-of-child-controls"></a>子控件的继承行为

完成前面的步骤后, 将发生以下继承行为:

- 在设计器中, 控件与继承的图标一起显示。

- <xref:System.Windows.Forms.ToolStripPanel>控件被锁定; 不能选择或重新排列其内容。

- 您可以向<xref:System.Windows.Forms.ToolStripContentPanel>中添加控件, 移动控件, 并使其成为的子控件<xref:System.Windows.Forms.ToolStripContentPanel>。

- 生成窗体后, 你的更改将保持不变。

  > [!NOTE]
  > 从属于的所有<xref:System.Windows.Forms.ToolStripPanel>控件<xref:System.Windows.Forms.ToolStripContainer>中删除访问修饰符。 的访问修饰符<xref:System.Windows.Forms.ToolStripContainer>控制整个控件。

#### <a name="partial-trust"></a>部分信任

部分信任下`ToolStrip`的限制旨在防止无意中输入未经授权的人员或服务可能使用的个人信息。 保护措施如下:

- `ToolStripDropDown`控件需要<xref:System.Security.Permissions.UIPermissionWindow.AllWindows> <xref:System.Windows.Forms.ToolStripControlHost>在中显示项。 这适用于内部控件<xref:System.Windows.Forms.ToolStripTextBox>, 例如、 <xref:System.Windows.Forms.ToolStripComboBox>和<xref:System.Windows.Forms.ToolStripProgressBar> , 以及用户创建的控件。 如果未满足此要求, 则不会显示这些项。 不引发异常。

- 不允许将`false`属性设置为, 并且将忽略可取消的事件参数。<xref:System.Windows.Forms.ToolStripDropDown.Closing> <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> 这样一来, 就不可能输入多个击键而不关闭下拉项。 如果未满足此要求, 则不会显示此类项。 不引发异常。

- 如果在的部分信任上下文<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>中发生事件, 则不会引发许多击键处理事件。

- 未授予访问密钥时<xref:System.Security.Permissions.UIPermissionWindow.AllWindows> , 不会对其进行处理。

#### <a name="usage"></a>用法

以下使用模式与布局、键盘交互<xref:System.Windows.Forms.ToolStrip>和最终用户行为有关:

- 联接于<xref:System.Windows.Forms.ToolStripPanel>

  可以在内和之间<xref:System.Windows.Forms.ToolStripPanel>重定位。 <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 忽略属性,`false`如果属性为<xref:System.Windows.Forms.ToolStrip> ,<xref:System.Windows.Forms.ToolStripPanel>则在将项添加到中时, 的大小将增长。 `Dock` 通常, <xref:System.Windows.Forms.ToolStrip>不参与 tab 键顺序。

- 停靠

  <xref:System.Windows.Forms.ToolStrip>置于固定位置的容器的一侧, 其大小会在其停靠到的整个边缘上展开。 通常, <xref:System.Windows.Forms.ToolStrip>不参与 tab 键顺序。

- 绝对定位

  与其他控件一样, 它是<xref:System.Windows.Forms.Control.Location%2A>由属性放置的, 它具有固定的大小, 并且通常参与 tab 键顺序。 <xref:System.Windows.Forms.ToolStrip>

#### <a name="keyboard-interaction"></a>键盘交互

##### <a name="access-keys"></a>访问密钥

通过与 ALT 键组合在一起或之后, 访问键是使用键盘激活控件的一种方法。 <xref:System.Windows.Forms.ToolStrip>支持显式和隐式访问密钥。 显式定义使用字母前的与号 (&) 字符。 隐式定义使用一种算法, 该算法根据给定`Text`属性中的字符顺序尝试查找匹配项。

##### <a name="shortcut-keys"></a>快捷键

使用的快捷键<xref:System.Windows.Forms.MenuStrip>使用<xref:System.Windows.Forms.Keys>枚举的组合 (不特定于顺序) 来定义快捷键。 你还可以使用<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>属性来显示仅带有文本的快捷键, 例如显示 "Del" 而不是 "Delete"。

##### <a name="navigation"></a>导航

ALT 键激活所指向<xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.Form.MainMenuStrip%2A>的。 在这里, CTRL + TAB 在中<xref:System.Windows.Forms.ToolStrip> `ToolStripPanel`的控件之间导航。 数字键盘上的 TAB 键和箭头键在中<xref:System.Windows.Forms.ToolStrip>的项之间导航。 特殊算法处理溢出区中的导航。 空格键选择<xref:System.Windows.Forms.ToolStripButton>、 <xref:System.Windows.Forms.ToolStripDropDownButton>或。 <xref:System.Windows.Forms.ToolStripSplitButton>

##### <a name="focus-and-validation"></a>焦点和验证

当通过 ALT 键激活时, <xref:System.Windows.Forms.MenuStrip>或<xref:System.Windows.Forms.ToolStrip>通常不会从当前具有焦点的控件中执行焦点, 也不会删除焦点。 如果在<xref:System.Windows.Forms.MenuStrip>或的下拉<xref:System.Windows.Forms.MenuStrip>控件中承载了一个控件, 则当用户按 TAB 键时, 控件将获得焦点。 通常, <xref:System.Windows.Forms.Control.GotFocus>当键盘激活<xref:System.Windows.Forms.Control.LostFocus>时<xref:System.Windows.Forms.Control.Enter>, <xref:System.Windows.Forms.MenuStrip>可能<xref:System.Windows.Forms.Control.Leave>不会引发、、和事件。 在这种情况下, <xref:System.Windows.Forms.MenuStrip.MenuActivate>请<xref:System.Windows.Forms.MenuStrip.MenuDeactivate>改用和事件。

默认情况下<xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> , `false`为。 在<xref:System.Windows.Forms.ContainerControl.Validate%2A>窗体上显式调用以执行验证。

#### <a name="layout"></a>布局

通过选择<xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripLayoutStyle> 具有<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>属性的成员之一来控制布局。

##### <a name="stack-layouts"></a>堆栈布局

堆栈是在两端并排<xref:System.Windows.Forms.ToolStrip>排列项。 下面的列表描述了堆栈布局。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>默认值为。 此设置会使<xref:System.Windows.Forms.ToolStrip>按照<xref:System.Windows.Forms.ToolStrip.Orientation%2A>属性自动更改其布局, 以便处理拖放和停靠方案。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>垂直呈现<xref:System.Windows.Forms.ToolStrip>项。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow>横向呈现<xref:System.Windows.Forms.ToolStrip>项。

##### <a name="other-features-of-stack-layouts"></a>堆栈布局的其他功能

<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>确定项要对齐到<xref:System.Windows.Forms.ToolStrip>的末尾。

当项不适合于<xref:System.Windows.Forms.ToolStrip>时, 会自动显示溢出按钮。 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>属性设置确定某项是否始终出现在溢出区中 (根据需要) 或从不出现。

在此<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>事件中, 你可以<xref:System.Windows.Forms.ToolStripItem.Placement%2A>检查属性, 以确定项是放置在主<xref:System.Windows.Forms.ToolStrip>位置、溢出<xref:System.Windows.Forms.ToolStrip>还是当前根本不显示。 项未显示的典型原因是项不适合 main <xref:System.Windows.Forms.ToolStrip> , 其<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>属性设置为<xref:System.Windows.Forms.ToolStripItemOverflow.Never>。

将其<xref:System.Windows.Forms.ToolStrip>放<xref:System.Windows.Forms.ToolStripPanel>入, 并将其<xref:System.Windows.Forms.ToolStrip.GripStyle%2A>设置为<xref:System.Windows.Forms.ToolStripGripStyle.Visible>, 使成为可移动的。

##### <a name="other-layout-options"></a>其他布局选项

其他布局选项为<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>和。 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>

##### <a name="flow-layout"></a>流布局

<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>布局是<xref:System.Windows.Forms.ContextMenuStrip>、 <xref:System.Windows.Forms.ToolStripDropDownMenu>和<xref:System.Windows.Forms.ToolStripOverflow>的默认设置。 它类似<xref:System.Windows.Forms.FlowLayoutPanel>于。 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>布局的功能如下所示:

- 的所有功能<xref:System.Windows.Forms.FlowLayoutPanel>都<xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>由属性公开。 您必须将<xref:System.Windows.Forms.LayoutSettings>类强制转换<xref:System.Windows.Forms.FlowLayoutSettings>为类。

- 您可以在代码<xref:System.Windows.Forms.ToolStripItem.Dock%2A>中<xref:System.Windows.Forms.ToolStripItem.Anchor%2A>使用和属性来对齐行中的项。

- <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 属性被忽略。

- 在此<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>事件中, 你可以<xref:System.Windows.Forms.ToolStripItem.Placement%2A>检查属性, 以确定项是放置在主<xref:System.Windows.Forms.ToolStrip>上还是不适合。

- 手柄未呈现, 因此<xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripPanel>无法移动中<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>布局样式中的。

- 溢出按钮不会呈现<xref:System.Windows.Forms.ToolStripItem.Overflow%2A> , 将被忽略。 <xref:System.Windows.Forms.ToolStrip>

##### <a name="table-layout"></a>表布局

<xref:System.Windows.Forms.ToolStripLayoutStyle.Table>布局是的默认值<xref:System.Windows.Forms.StatusStrip>。 它类似于<xref:System.Windows.Forms.TableLayoutPanel>。 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>布局的功能如下所示:

- 的所有功能<xref:System.Windows.Forms.TableLayoutPanel>都<xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>由属性公开。 您必须将<xref:System.Windows.Forms.LayoutSettings>类强制转换<xref:System.Windows.Forms.TableLayoutSettings>为类。

- 您可以在代码<xref:System.Windows.Forms.ToolStripItem.Dock%2A>中<xref:System.Windows.Forms.ToolStripItem.Anchor%2A>使用和属性来对齐表单元格中的项。

- <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 属性被忽略。

- 在此<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>事件中, 你可以<xref:System.Windows.Forms.ToolStripItem.Placement%2A>检查属性, 以确定项是放置在主<xref:System.Windows.Forms.ToolStrip>上还是不适合。

- 手柄未呈现, 因此<xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripPanel>无法移动中<xref:System.Windows.Forms.ToolStripLayoutStyle.Table>布局样式中的。

- 溢出按钮不会呈现<xref:System.Windows.Forms.ToolStripItem.Overflow%2A> , 将被忽略。 <xref:System.Windows.Forms.ToolStrip>

## <a name="toolstripitem"></a>ToolStripItem

以下主题描述<xref:System.Windows.Forms.ToolStripItem>和派生自它的控件。

<xref:System.Windows.Forms.ToolStripItem>是进入中<xref:System.Windows.Forms.ToolStrip>的所有项的抽象基类。 以下对象模型显示<xref:System.Windows.Forms.ToolStripItem>了继承层次结构。

![显示 ToolStripItem 对象模型的关系图。](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)

<xref:System.Windows.Forms.ToolStripItem>类直接从<xref:System.Windows.Forms.ToolStripItem>继承, 或者<xref:System.Windows.Forms.ToolStripControlHost>它们从<xref:System.Windows.Forms.ToolStripItem>或<xref:System.Windows.Forms.ToolStripDropDownItem>间接继承。

<xref:System.Windows.Forms.ToolStripItem><xref:System.Windows.Forms.ToolStrip>控件必须包含在<xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 、、或中,不能直接添加到窗体中。<xref:System.Windows.Forms.StatusStrip> 各种容器类旨在包含控件的<xref:System.Windows.Forms.ToolStripItem>适当子集。

下表列出了常用<xref:System.Windows.Forms.ToolStripItem>控件和它们最适合的容器。 尽管任何<xref:System.Windows.Forms.ToolStrip>项都可以在任何<xref:System.Windows.Forms.ToolStrip>派生的容器中托管, 但这些项在以下容器中的设计效果最好:

> [!NOTE]
> <xref:System.Windows.Forms.ToolStripDropDown>不会出现在设计器工具箱中。

|包含的项|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|
|<xref:System.Windows.Forms.ToolStripButton>|是|No|No|No|是|
|<xref:System.Windows.Forms.ToolStripComboBox>|是|是|是|No|是|
|<xref:System.Windows.Forms.ToolStripSplitButton>|是|No|No|是|是|
|<xref:System.Windows.Forms.ToolStripLabel>|是|No|No|是|是|
|<xref:System.Windows.Forms.ToolStripSeparator>|是|是|是|No|是|
|<xref:System.Windows.Forms.ToolStripDropDownButton>|是|No|No|是|是|
|<xref:System.Windows.Forms.ToolStripTextBox>|是|是|是|No|是|
|<xref:System.Windows.Forms.ToolStripMenuItem>|No|是|是|No|No|
|<xref:System.Windows.Forms.ToolStripStatusLabel>|No|No|No|是|No|
|<xref:System.Windows.Forms.ToolStripProgressBar>|是|No|No|是|No|
|<xref:System.Windows.Forms.ToolStripControlHost>|是|是|No|是|是|

### <a name="toolstripbutton"></a>ToolStripButton

<xref:System.Windows.Forms.ToolStripButton>是的<xref:System.Windows.Forms.ToolStrip>按钮项。 您可以使用各种边框样式显示它, 并且可以使用它来表示和激活操作状态。 你还可以将其定义为默认情况下具有焦点。

### <a name="toolstriplabel"></a>ToolStripLabel

在控件中<xref:System.Windows.Forms.ToolStrip> 提供标签功能。<xref:System.Windows.Forms.ToolStripLabel> <xref:System.Windows.Forms.ToolStripLabel> 类似于,默认情况下不会获得焦点,且不会呈现为按下或<xref:System.Windows.Forms.ToolStripButton>突出显示的。

<xref:System.Windows.Forms.ToolStripLabel>作为托管项, 支持访问密钥。

使用<xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>上的<xref:System.Windows.Forms.ToolStripLabel> 、和属性支持中的链接控件<xref:System.Windows.Forms.ToolStrip>。

### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel

<xref:System.Windows.Forms.ToolStripStatusLabel>是专用于在<xref:System.Windows.Forms.ToolStripLabel>中<xref:System.Windows.Forms.StatusStrip>使用的的版本。 特殊功能包括<xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>、 <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>和<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>。

### <a name="toolstripseparator"></a>ToolStripSeparator

根据方向, 向工具栏或菜单添加垂直或水平线条。<xref:System.Windows.Forms.ToolStripSeparator> 它提供项的分组或区分, 如菜单上的项。

您可以<xref:System.Windows.Forms.ToolStripSeparator>在设计时通过从下拉列表中选择来添加。 但是, 还可以<xref:System.Windows.Forms.ToolStripSeparator>通过在设计器模板节点或<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法中键入连字符 (-) 来自动创建。

### <a name="toolstripcontrolhost"></a>ToolStripControlHost

<xref:System.Windows.Forms.ToolStripControlHost>是<xref:System.Windows.Forms.ToolStripComboBox>、 <xref:System.Windows.Forms.ToolStripTextBox>和的抽象基类。<xref:System.Windows.Forms.ToolStripProgressBar> <xref:System.Windows.Forms.ToolStripControlHost>可以通过两种方式承载其他控件, 包括自定义控件:

- 使用派生自<xref:System.Windows.Forms.Control>的类构造。 <xref:System.Windows.Forms.ToolStripControlHost> 若要完全访问所承载的控件和属性, 必须将<xref:System.Windows.Forms.ToolStripControlHost.Control%2A>属性强制转换回它所表示的实际类。

- 扩展<xref:System.Windows.Forms.ToolStripControlHost>, 并在继承类的无参数构造函数中, 调用基类构造函数, 该构造函数传递<xref:System.Windows.Forms.Control>派生自的类。 使用此选项可以包装常用控制方法和属性, 以便在中<xref:System.Windows.Forms.ToolStrip>轻松访问。

### <a name="toolstripcombobox"></a>ToolStripComboBox

<xref:System.Windows.Forms.ToolStripComboBox>是针对<xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ToolStrip>在中承载的进行了优化。 托管控件的属性和事件的子集在<xref:System.Windows.Forms.ToolStripComboBox>级别公开, 但基础<xref:System.Windows.Forms.ComboBox>控件可通过<xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A>属性完全访问。

### <a name="toolstriptextbox"></a>ToolStripTextBox

<xref:System.Windows.Forms.ToolStripTextBox>是针对<xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.ToolStrip>在中承载的进行了优化。 托管控件的属性和事件的子集在<xref:System.Windows.Forms.ToolStripTextBox>级别公开, 但基础<xref:System.Windows.Forms.TextBox>控件可通过<xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A>属性完全访问。

### <a name="toolstripprogressbar"></a>ToolStripProgressBar

<xref:System.Windows.Forms.ToolStripProgressBar>是针对<xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ToolStrip>在中承载的进行了优化。 托管控件的属性和事件的子集在<xref:System.Windows.Forms.ToolStripProgressBar>级别公开, 但基础<xref:System.Windows.Forms.ProgressBar>控件可通过<xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A>属性完全访问。

### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem

<xref:System.Windows.Forms.ToolStripDropDownItem>是<xref:System.Windows.Forms.ToolStripMenuItem>、 <xref:System.Windows.Forms.ToolStripDropDownButton>和的抽象基类,它可以直接承载项或在下拉容器中承载附加项。<xref:System.Windows.Forms.ToolStripSplitButton> 为此, 可将<xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A>属性设置为<xref:System.Windows.Forms.ToolStrip.Items%2A> , 并设置的<xref:System.Windows.Forms.ToolStripDropDown>属性。 <xref:System.Windows.Forms.ToolStripDropDown> 直接通过<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>属性访问这些下拉项。

### <a name="toolstripmenuitem"></a>ToolStripMenuItem

<xref:System.Windows.Forms.ToolStripMenuItem><xref:System.Windows.Forms.ToolStripDropDownItem>与<xref:System.Windows.Forms.ToolStripDropDownMenu>和配合<xref:System.Windows.Forms.ContextMenuStrip>使用来处理菜单的特殊突出显示、布局和列排列。

### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton

<xref:System.Windows.Forms.ToolStripDropDownButton>看起来<xref:System.Windows.Forms.ToolStripButton>像这样, 但当用户单击它时, 它会显示一个下拉区域。 通过设置<xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A>属性, 隐藏或显示下拉箭头。 <xref:System.Windows.Forms.ToolStripDropDownButton>承载用于显示溢出的<xref:System.Windows.Forms.ToolStrip>项的。 <xref:System.Windows.Forms.ToolStripOverflowButton>

### <a name="toolstripsplitbutton"></a>ToolStripSplitButton

<xref:System.Windows.Forms.ToolStripSplitButton>组合按钮和下拉按钮的功能。

使用属性将所选下拉<xref:System.Windows.Forms.Control.Click>项的事件与按钮上显示的项同步。 <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A>

### <a name="toolstripitem-generic-features"></a>ToolStripItem 一般功能

<xref:System.Windows.Forms.ToolStripItem>提供以下用于继承控件的通用功能和选项:

- 核心事件

- 图像处理

- 对齐方式

- 文本和图像关系

- 显示样式

#### <a name="core-events"></a>核心事件

<xref:System.Windows.Forms.ToolStripItem>控件接收自己的 click、鼠标和 paint 事件, 还可以执行一些键盘预处理。

#### <a name="image-handling"></a>图像处理

<xref:System.Windows.Forms.ToolStripItem.Image%2A>、 、、<xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>和属性与图像处理的<xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A>各个方面相关。 <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A> <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A> 在控件中<xref:System.Windows.Forms.ToolStrip>使用图像, 方法是直接设置这些属性, 或者通过设置 "仅<xref:System.Windows.Forms.ToolStrip.ImageList%2A>运行时–只" 属性。

图像缩放是通过<xref:System.Windows.Forms.ToolStrip>和<xref:System.Windows.Forms.ToolStripItem>中的属性交互确定的, 如下所示:

- <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>最终映像的小数位数, 由图像<xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A>设置和<xref:System.Windows.Forms.ToolStrip.AutoSize%2A>容器设置的组合确定。

  - 如果<xref:System.Windows.Forms.ToolStrip.AutoSize%2A> <xref:System.Windows.Forms.ToolStripItemImageScaling>为`true` (默认值) 并且为<xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, 则不会进行图像缩放, <xref:System.Windows.Forms.ToolStrip>并且大小是最大项的大小, 或者是指定的最小大小。

  - 如果<xref:System.Windows.Forms.ToolStrip.AutoSize%2A>为`false`且<xref:System.Windows.Forms.ToolStrip>为,则<xref:System.Windows.Forms.ToolStripItemImageScaling.None>不会发生图像和缩放。 <xref:System.Windows.Forms.ToolStripItemImageScaling>

#### <a name="alignment"></a>对齐方式

<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>属性的值确定项出现的结束<xref:System.Windows.Forms.ToolStrip>位置。 仅<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>当的布局样式<xref:System.Windows.Forms.ToolStrip>设置为某个堆栈溢出值时, 属性才有效。

项<xref:System.Windows.Forms.ToolStrip>按项在项集合中出现的顺序放置在上。 若要以编程方式更改项的布局位置, 请<xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A>使用方法移动集合中的项。 此方法会移动项, 但不会复制该项。

#### <a name="text-and-image-relationship"></a>文本和图像关系

属性定义图像相对于<xref:System.Windows.Forms.ToolStripItem>上的文本的相对位置。 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 缺少图像、文本或二者的项被视为特殊情况, 因此<xref:System.Windows.Forms.ToolStripItem> , 不会为缺少的元素显示空白点。

#### <a name="display-style"></a>显示样式

<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>允许您设置项的文本和图像属性的值, 同时只显示您需要的内容。 这通常用于在不同的上下文中显示相同项时仅更改显示样式。

## <a name="accessory-classes"></a>附件类

提供各种其他功能的类包括:

- <xref:System.Windows.Forms.ToolStripManager>支持<xref:System.Windows.Forms.ToolStrip>与整个应用程序相关的任务, 例如合并、设置和呈现器选项。

- <xref:System.Windows.Forms.ToolStripRenderer>允许您<xref:System.Windows.Forms.ToolStrip>轻松地将特定样式或主题应用于。

- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>基于可替换颜色表 (<xref:System.Windows.Forms.ProfessionalColorTable>) 创建笔和画笔。

- <xref:System.Windows.Forms.ToolStripSystemRenderer>将系统颜色和平面视觉样式<xref:System.Windows.Forms.ToolStrip>应用于应用程序。

- <xref:System.Windows.Forms.ToolStripContainer>类似于<xref:System.Windows.Forms.SplitContainer>。 它使用四个停靠的面板 (实例<xref:System.Windows.Forms.ToolStripPanel>) 和一个中央面板 ( <xref:System.Windows.Forms.ToolStripContentPanel>实例) 来创建典型的排列方式。 不能移除侧面板, 但可以隐藏它们。 不能删除或隐藏中央面板。 您可以排列侧面板中<xref:System.Windows.Forms.ToolStrip>的<xref:System.Windows.Forms.MenuStrip>一个或<xref:System.Windows.Forms.StatusStrip>多个、或控件, 还可以使用中央面板来查看其他控件。 <xref:System.Windows.Forms.ToolStripContentPanel>还提供了一种方法来获取窗体正文的呈现器支持, 以实现一致的外观。 <xref:System.Windows.Forms.ToolStripContainer>不支持多文档界面 (MDI)。

- <xref:System.Windows.Forms.ToolStripPanel>为移动和排列<xref:System.Windows.Forms.ToolStrip>控件提供空间。 如果选择了, 则只能使用一个面板, <xref:System.Windows.Forms.ToolStripPanel>在 MDI 方案中可以很好地运行。

## <a name="see-also"></a>请参阅

- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
- [MenuStrip 控件](menustrip-control-windows-forms.md)
- [StatusStrip 控件](statusstrip-control.md)
- [ContextMenuStrip 控件](contextmenustrip-control.md)
- [BindingNavigator 控件](bindingnavigator-control-windows-forms.md)
