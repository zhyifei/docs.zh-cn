---
title: "ToolStrip 控件体系结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6884598e6b883ab5e6369be5f2f796a194c7f930
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="toolstrip-control-architecture"></a>ToolStrip 控件体系结构
<xref:System.Windows.Forms.ToolStrip>和<xref:System.Windows.Forms.ToolStripItem>类提供一个灵活、 可扩展系统，用于显示工具栏、 状态和菜单项。 这些类都包含在<xref:System.Windows.Forms>命名空间和它们的所有通常命名以"ToolStrip"前缀 (如<xref:System.Windows.Forms.ToolStripOverflow>) 或"条带"后缀 (例如<xref:System.Windows.Forms.MenuStrip>)。  
  
## <a name="toolstrip"></a>ToolStrip  
 以下主题介绍<xref:System.Windows.Forms.ToolStrip>和从它派生的控件。  
  
 <xref:System.Windows.Forms.ToolStrip>是的抽象基类<xref:System.Windows.Forms.MenuStrip>， <xref:System.Windows.Forms.StatusStrip>，和<xref:System.Windows.Forms.ContextMenuStrip>。 以下对象模型显示<xref:System.Windows.Forms.ToolStrip>继承层次结构。  
  
 ![ToolStrip 对象模型](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.gif "ToolStripObjectModel")  
ToolStrip 对象模型  
  
 你可以访问中的所有项<xref:System.Windows.Forms.ToolStrip>通过<xref:System.Windows.Forms.ToolStrip.Items%2A>集合。 你可以访问中的所有项<xref:System.Windows.Forms.ToolStripDropDownItem>通过<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>集合。 在派生类的<xref:System.Windows.Forms.ToolStrip>，你还可以使用<xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A>属性来访问只当前显示的项。 这些是当前未溢出菜单项。  
  
 以下各项专门用于与都无缝配合<xref:System.Windows.Forms.ToolStripSystemRenderer>和<xref:System.Windows.Forms.ToolStripProfessionalRenderer>中所有的方向。 会在设计时按默认提供的<xref:System.Windows.Forms.ToolStrip>控件：  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip>为取代的顶级容器<xref:System.Windows.Forms.MainMenu>。 它还提供密钥的处理和多文档界面 (MDI) 功能。 就功能而言，<xref:System.Windows.Forms.ToolStripDropDownItem>和<xref:System.Windows.Forms.ToolStripMenuItem>工作连同<xref:System.Windows.Forms.MenuStrip>，尽管它们都派生自<xref:System.Windows.Forms.ToolStripItem>。  
  
 以下各项专门用于与都无缝配合<xref:System.Windows.Forms.ToolStripSystemRenderer>和<xref:System.Windows.Forms.ToolStripProfessionalRenderer>中所有的方向。 会在设计时按默认提供的<xref:System.Windows.Forms.MenuStrip>控件：  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip>替换<xref:System.Windows.Forms.StatusBar>控件。 特殊功能的<xref:System.Windows.Forms.StatusStrip>包括自定义表布局，对窗体的大小调整和移动手柄，支持和`Spring`属性，它允许<xref:System.Windows.Forms.ToolStripStatusLabel>以自动填充可用空间。  
  
 以下各项专门用于与都无缝配合<xref:System.Windows.Forms.ToolStripSystemRenderer>和<xref:System.Windows.Forms.ToolStripProfessionalRenderer>中所有的方向。 会在设计时按默认提供的<xref:System.Windows.Forms.StatusStrip>控件：  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip>替换<xref:System.Windows.Forms.ContextMenu>。 你可以将关联<xref:System.Windows.Forms.ContextMenuStrip>任何控件，与鼠标右键单击自动显示的上下文菜单 （或快捷菜单）。 你可以显示<xref:System.Windows.Forms.ContextMenuStrip>以编程方式通过使用<xref:System.Windows.Forms.ToolStripDropDown.Show%2A>方法。 <xref:System.Windows.Forms.ContextMenuStrip>支持可取消<xref:System.Windows.Forms.ToolStripDropDown.Opening>和<xref:System.Windows.Forms.ToolStripDropDown.Closing>事件，以处理动态填充和多次单击方案。 <xref:System.Windows.Forms.ContextMenuStrip>支持映像、 菜单项检查状态、 文本、 访问密钥、 快捷方式，和级联菜单。  
  
 以下各项专门用于与都无缝配合<xref:System.Windows.Forms.ToolStripSystemRenderer>和<xref:System.Windows.Forms.ToolStripProfessionalRenderer>中所有的方向。 会在设计时按默认提供的<xref:System.Windows.Forms.ContextMenuStrip>控件：  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>ToolStrip 泛型功能  
 以下主题描述了功能和行为的通用到<xref:System.Windows.Forms.ToolStrip>和派生控件。  
  
#### <a name="painting"></a>绘制  
 你可以执行自定义绘制<xref:System.Windows.Forms.ToolStrip>有几个方面的控件。 与其他 Windows 窗体控件，<xref:System.Windows.Forms.ToolStrip>和<xref:System.Windows.Forms.ToolStripItem>都具有可重写`OnPaint`方法和`Paint`事件。 因为与常规的绘制坐标系统是相对于控件; 的工作区左上角的控件，即为 0，0。 `Paint`事件和`OnPaint`方法<xref:System.Windows.Forms.ToolStripItem>的行为类似于其他控件绘制事件。  
  
 <xref:System.Windows.Forms.ToolStrip>控件还提供更细致的访问的项和容器可以通过的呈现<xref:System.Windows.Forms.ToolStripRenderer>类，该类具有可重写方法，用于绘制背景、 项背景、 项图像、 项箭头、 项文本，和的边框<xref:System.Windows.Forms.ToolStrip>. 这些方法的事件自变量公开多个属性，如矩形、 颜色和可以根据需要进行调整的文本格式。  
  
 若要调整的如何绘制项的几个方面，通常可以重写<xref:System.Windows.Forms.ToolStripRenderer>。  
  
 如果你在编写新的项，并且想要控制绘制的所有方面，重写`OnPaint`方法。 在`OnPaint`，你可以使用从方法<xref:System.Windows.Forms.ToolStripRenderer>。  
  
 默认情况下，<xref:System.Windows.Forms.ToolStrip>进行双缓冲，利用<xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>设置。  
  
#### <a name="parenting"></a>设置父级  
 容器所属权和设置父级的概念是在更复杂<xref:System.Windows.Forms.ToolStrip>控制比其他 Windows 窗体的容器控件中。 这是支持动态的情况下，如溢出，在多个共享下拉列表项所需<xref:System.Windows.Forms.ToolStrip>项，并支持生成的<xref:System.Windows.Forms.ContextMenuStrip>从另一控件。  
  
 以下列表与设置父级的成员进行了说明，并说明其用途。  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>访问的源的下拉列表项的项。 它类似于<xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>，但它将返回而不是返回一个控件， <xref:System.Windows.Forms.ToolStripItem>。  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>确定哪些控件是源的<xref:System.Windows.Forms.ContextMenuStrip>当多个控件共用同一个<xref:System.Windows.Forms.ContextMenuStrip>。  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>是对只读访问器<xref:System.Windows.Forms.ToolStripItem.Parent%2A>属性。 父与不同所有者的父表示返回的当前<xref:System.Windows.Forms.ToolStrip>在其中将显示该项，这可能会溢出区域中。  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A>返回<xref:System.Windows.Forms.ToolStrip>其项集合包含当前<xref:System.Windows.Forms.ToolStripItem>。 这是引用的最佳方式<xref:System.Windows.Forms.ToolStrip.ImageList%2A>或其他属性位于顶级<xref:System.Windows.Forms.ToolStrip>而无需编写特殊的代码来处理溢出。  
  
#### <a name="behavior-of-inherited-controls"></a>继承控件的行为  
 以下控件被锁定，只要它们在继承中：  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel>包括在面板<xref:System.Windows.Forms.ToolStripContainer>和也各个<xref:System.Windows.Forms.ToolStripPanel>控件。  
  
 例如，通过使用上面列表中的一个或多个控件创建一个新的 Windows 窗体应用程序。 设置到的一个或多个控件的访问修饰符`public`或`protected`，然后生成项目。 添加从第一个窗体，继承的窗体，然后选择继承的控件。 该控件会出现锁定，行为就像其访问修饰符是`private`。  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer 的继承支持  
 <xref:System.Windows.Forms.ToolStripContainer>控件支持有限继承的类似于下面的示例方案：  
  
1.  创建新的 Windows 窗体应用程序。  
  
2.  在窗体上添加一个 <xref:System.Windows.Forms.ToolStripContainer> 控件。  
  
3.  设置的访问修饰符<xref:System.Windows.Forms.ToolStripContainer>到`public`或`protected`。  
  
4.  添加的任意组合<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>，和<xref:System.Windows.Forms.ContextMenuStrip>控件添加到<xref:System.Windows.Forms.ToolStripPanel>的区域<xref:System.Windows.Forms.ToolStripContainer>。  
  
5.  生成项目。  
  
6.  添加从第一个窗体继承的窗体。  
  
7.  选择继承<xref:System.Windows.Forms.ToolStripContainer>窗体上。  
  
#### <a name="inherited-behavior-of-child-controls"></a>子控件的继承的行为  
 完成前面的步骤后，将发生以下继承的行为：  
  
-   在设计器中，控件将显示带有继承的图标。  
  
-   <xref:System.Windows.Forms.ToolStripPanel>锁定控件; 不能选择或重新排列其内容。  
  
-   你可以将控件添加到<xref:System.Windows.Forms.ToolStripContentPanel>、 移动的控件，并使它们的子控件<xref:System.Windows.Forms.ToolStripContentPanel>。  
  
-   生成的窗体后保留所做的更改。  
  
    > [!NOTE]
    >  从所有删除的访问修饰符<xref:System.Windows.Forms.ToolStripPanel>控件属于<xref:System.Windows.Forms.ToolStripContainer>。 访问修饰符<xref:System.Windows.Forms.ToolStripContainer>控制整个控件。  
  
#### <a name="partial-trust"></a>部分信任  
 限制`ToolStrip`在部分信任下的 s 旨在防止无意中输入的可能被未经授权的人员或服务使用的个人信息。 保护措施如下所示：  
  
-   `ToolStripDropDown`控件需要<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>以显示中的项<xref:System.Windows.Forms.ToolStripControlHost>。 这如适用于这两个内部控件<xref:System.Windows.Forms.ToolStripTextBox>， <xref:System.Windows.Forms.ToolStripComboBox>，和<xref:System.Windows.Forms.ToolStripProgressBar>作为同时创建用户控件。 如果不满足此要求，将不会显示这些项。 不引发异常。  
  
-   设置<xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A>属性`false`不允许，可取消<xref:System.Windows.Forms.ToolStripDropDown.Closing>事件参数将被忽略。 这使得不可能，如果不关闭下拉列表项中输入多个键击。 如果不满足此要求，将不会显示此类项。 不引发异常。  
  
-   如果它们不在部分信任的上下文中发生，不会引发处理事件的许多击键<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>。  
  
-   访问键不是处理时<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>未被授予。  
  
#### <a name="usage"></a>用法  
 以下使用情况模式影响对<xref:System.Windows.Forms.ToolStrip>布局、 键盘交互和最终用户行为：  
  
-   在中联接<xref:System.Windows.Forms.ToolStripPanel>  
  
     <xref:System.Windows.Forms.ToolStrip>内可重新定位<xref:System.Windows.Forms.ToolStripPanel>并跨<xref:System.Windows.Forms.ToolStripPanel>s。 `Dock`属性将被忽略，并且如果<xref:System.Windows.Forms.ToolStrip.Stretch%2A>属性是`false`，大小为<xref:System.Windows.Forms.ToolStrip>将随着项被添加到<xref:System.Windows.Forms.ToolStripPanel>。 通常情况下，<xref:System.Windows.Forms.ToolStrip>不参与 tab 键顺序。  
  
-   停靠  
  
     <xref:System.Windows.Forms.ToolStrip>放置在固定位置中的容器的一侧上，且其大小将移到停靠的整个边缘扩展。 通常情况下，<xref:System.Windows.Forms.ToolStrip>不参与 tab 键顺序。  
  
-   绝对定位  
  
     <xref:System.Windows.Forms.ToolStrip>相当于其他控件，可通过将其放<xref:System.Windows.Forms.Control.Location%2A>属性，具有固定的大小，并通常参与 tab 键顺序。  
  
#### <a name="keyboard-interaction"></a>键盘交互  
  
##### <a name="access-keys"></a>访问密钥  
 访问键组合使用或紧随 ALT 键，是一种方式利用键盘激活控件。 <xref:System.Windows.Forms.ToolStrip>支持这两个显式和隐式访问密钥。 显式定义使用与号 (&) 字符前面的字母。 隐式定义使用的算法的尝试查找匹配项中的字符顺序基于给定`Text`属性。  
  
##### <a name="shortcut-keys"></a>快捷键  
 使用的键盘快捷方式<xref:System.Windows.Forms.MenuStrip>结合使用<xref:System.Windows.Forms.Keys>枚举 （这不是特定于订单） 来定义的快捷键。 你还可以使用<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>属性来显示与纯文本的快捷键，例如显示"Del"而不"删除"。  
  
##### <a name="navigation"></a>导航  
 ALT 键激活<xref:System.Windows.Forms.MenuStrip>指向<xref:System.Windows.Forms.Form.MainMenuStrip%2A>。 在这里，CTRL + TAB 其之间导航<xref:System.Windows.Forms.ToolStrip>内控制`ToolStripPanel`s。 TAB 键和数字键盘上的箭头键在项之间导航<xref:System.Windows.Forms.ToolStrip>。 特殊算法处理溢出区域中的导航。 空格键选择<xref:System.Windows.Forms.ToolStripButton>， <xref:System.Windows.Forms.ToolStripDropDownButton>，或<xref:System.Windows.Forms.ToolStripSplitButton>。  
  
##### <a name="focus-and-validation"></a>焦点和验证  
 当激活 ALT 键，<xref:System.Windows.Forms.MenuStrip>或<xref:System.Windows.Forms.ToolStrip>通常既不需要也不删除从当前具有焦点的控件的焦点。 如果没有内承载的控件<xref:System.Windows.Forms.MenuStrip>或下拉菜单的<xref:System.Windows.Forms.MenuStrip>，控件在用户按 TAB 键时获得焦点。 一般情况下， <xref:System.Windows.Forms.Control.GotFocus>， <xref:System.Windows.Forms.Control.LostFocus>， <xref:System.Windows.Forms.Control.Enter>，和<xref:System.Windows.Forms.Control.Leave>的事件<xref:System.Windows.Forms.MenuStrip>时键盘会激活这些可能不会引发。 在这种情况下，使用<xref:System.Windows.Forms.MenuStrip.MenuActivate>和<xref:System.Windows.Forms.MenuStrip.MenuDeactivate>事件相反。  
  
 默认情况下，<xref:System.Windows.Forms.ToolStrip.CausesValidation%2A>是`false`。 调用<xref:System.Windows.Forms.ContainerControl.Validate%2A>显式你窗体上进行执行验证。  
  
#### <a name="layout"></a>布局  
 您可以控制<xref:System.Windows.Forms.ToolStrip>通过选择其中一个的成员的布局<xref:System.Windows.Forms.ToolStripLayoutStyle>与<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>属性。  
  
##### <a name="stack-layouts"></a>堆栈布局  
 堆栈是并排排列项相互位于两端<xref:System.Windows.Forms.ToolStrip>。 以下列表介绍堆栈布局。  
  
-   默认为 <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>。 此设置会导致<xref:System.Windows.Forms.ToolStrip>改变其自动中根据所使用的布局<xref:System.Windows.Forms.ToolStrip.Orientation%2A>属性以处理拖动和停靠方案。  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>呈现<xref:System.Windows.Forms.ToolStrip>垂直旁边每个其他项。  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow>呈现<xref:System.Windows.Forms.ToolStrip>水平旁边每个其他项。  
  
##### <a name="other-features-of-stack-layouts"></a>堆栈布局的其他功能  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>确定的末尾<xref:System.Windows.Forms.ToolStrip>到项对齐。  
  
 当项不适合在<xref:System.Windows.Forms.ToolStrip>，溢出按钮自动显示。 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>属性设置确定是否项出现在溢出区域始终，根据需要或永远不会。  
  
 在<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>事件中，你可以检查<xref:System.Windows.Forms.ToolStripItem.Placement%2A>属性来确定某项放在主<xref:System.Windows.Forms.ToolStrip>，溢出<xref:System.Windows.Forms.ToolStrip>，或如果当前根本未显示。 为什么不显示项的通常原因是，在主无法容纳该项<xref:System.Windows.Forms.ToolStrip>及其<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>属性设置为<xref:System.Windows.Forms.ToolStripItemOverflow.Never>。  
  
 请<xref:System.Windows.Forms.ToolStrip>可移动通过将它放入<xref:System.Windows.Forms.ToolStripPanel>和设置其<xref:System.Windows.Forms.ToolStrip.GripStyle%2A>到<xref:System.Windows.Forms.ToolStripGripStyle.Visible>。  
  
##### <a name="other-layout-options"></a>其他布局选项  
 其他布局选项为<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>和<xref:System.Windows.Forms.ToolStripLayoutStyle.Table>。  
  
##### <a name="flow-layout"></a>流布局  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>布局的默认设置是<xref:System.Windows.Forms.ContextMenuStrip>， <xref:System.Windows.Forms.ToolStripDropDownMenu>，和<xref:System.Windows.Forms.ToolStripOverflow>。 它是类似于<xref:System.Windows.Forms.FlowLayoutPanel>。 功能<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>布局如下所示：  
  
-   所有功能<xref:System.Windows.Forms.FlowLayoutPanel>公开的<xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>属性。 您必须将转换<xref:System.Windows.Forms.LayoutSettings>类到<xref:System.Windows.Forms.FlowLayoutSettings>类。  
  
-   你可以使用<xref:System.Windows.Forms.ToolStripItem.Dock%2A>和<xref:System.Windows.Forms.ToolStripItem.Anchor%2A>以对齐行中的项的代码中的属性。  
  
-   <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 属性被忽略。  
  
-   在<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>事件中，你可以检查<xref:System.Windows.Forms.ToolStripItem.Placement%2A>属性来确定某项放在主<xref:System.Windows.Forms.ToolStrip>还是无法容纳。  
  
-   不呈现手柄，因此<xref:System.Windows.Forms.ToolStrip>中<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>中的布局样式<xref:System.Windows.Forms.ToolStripPanel>无法移动。  
  
-   <xref:System.Windows.Forms.ToolStrip>不呈现溢出按钮，和<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>将被忽略。  
  
##### <a name="table-layout"></a>表布局  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>布局的默认设置是<xref:System.Windows.Forms.StatusStrip>。 它是类似于<xref:System.Windows.Forms.TableLayoutPanel>。 功能<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>布局如下所示：  
  
-   所有功能<xref:System.Windows.Forms.TableLayoutPanel>公开的<xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>属性。 您必须将转换<xref:System.Windows.Forms.LayoutSettings>类到<xref:System.Windows.Forms.TableLayoutSettings>类。  
  
-   你可以使用<xref:System.Windows.Forms.ToolStripItem.Dock%2A>和<xref:System.Windows.Forms.ToolStripItem.Anchor%2A>代码中用于对齐表单元格内的项的属性。  
  
-   <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 属性被忽略。  
  
-   在<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>事件中，你可以检查<xref:System.Windows.Forms.ToolStripItem.Placement%2A>属性来确定某项放在主<xref:System.Windows.Forms.ToolStrip>还是无法容纳。  
  
-   不呈现手柄，因此<xref:System.Windows.Forms.ToolStrip>中<xref:System.Windows.Forms.ToolStripLayoutStyle.Table>中的布局样式<xref:System.Windows.Forms.ToolStripPanel>无法移动。  
  
-   <xref:System.Windows.Forms.ToolStrip>不呈现溢出按钮，和<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>将被忽略。  
  
## <a name="toolstripitem"></a>ToolStripItem  
 以下主题介绍<xref:System.Windows.Forms.ToolStripItem>和从它派生的控件。  
  
 <xref:System.Windows.Forms.ToolStripItem>是的抽象基类的所有项的进入<xref:System.Windows.Forms.ToolStrip>。 以下对象模型显示<xref:System.Windows.Forms.ToolStripItem>继承层次结构。  
  
 ![ToolStripItem 对象模型](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.gif "ToolStripItemObjectModel")  
ToolStripItem 对象模型  
  
 <xref:System.Windows.Forms.ToolStripItem>请从直接继承的类<xref:System.Windows.Forms.ToolStripItem>，或它们间接继承自<xref:System.Windows.Forms.ToolStripItem>通过<xref:System.Windows.Forms.ToolStripControlHost>或<xref:System.Windows.Forms.ToolStripDropDownItem>。  
  
 <xref:System.Windows.Forms.ToolStripItem>控件必须包含在<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>， <xref:System.Windows.Forms.StatusStrip>，或<xref:System.Windows.Forms.ContextMenuStrip>和不能直接添加到窗体。 各种容器类被设计为包含的相应子集<xref:System.Windows.Forms.ToolStripItem>控件。  
  
 下表列出了常用<xref:System.Windows.Forms.ToolStripItem>控件和它们显示最佳的容器。 尽管任何<xref:System.Windows.Forms.ToolStrip>项可以承载于任何<xref:System.Windows.Forms.ToolStrip>-派生容器，这些项已设计用于查找最佳以下容器中：  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown>未出现在设计器工具箱。  
  
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
 <xref:System.Windows.Forms.ToolStripButton>对按钮项<xref:System.Windows.Forms.ToolStrip>。 可使用不同的边框样式，来显示和可用来表示和激活的操作状态。 你还可以定义其默认情况下具有焦点。  
  
### <a name="toolstriplabel"></a>ToolStripLabel  
 <xref:System.Windows.Forms.ToolStripLabel>标签在提供的功能<xref:System.Windows.Forms.ToolStrip>控件。 <xref:System.Windows.Forms.ToolStripLabel>类似<xref:System.Windows.Forms.ToolStripButton>，不会默认情况下获取焦点并不会呈现为推送或突出显示。  
  
 <xref:System.Windows.Forms.ToolStripLabel>作为托管项支持访问密钥。  
  
 使用<xref:System.Windows.Forms.LinkLabel.LinkColor%2A>， <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>，和<xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>属性<xref:System.Windows.Forms.ToolStripLabel>以支持中的链接控件<xref:System.Windows.Forms.ToolStrip>。  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel>是的版本<xref:System.Windows.Forms.ToolStripLabel>专为在中使用<xref:System.Windows.Forms.StatusStrip>。 特殊的功能包括<xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>， <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>，和<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>。  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 <xref:System.Windows.Forms.ToolStripSeparator>将垂直或水平行添加到工具栏或菜单上，具体取决于方向。 它提供的分组或项，例如菜单上的那些之间的区别。  
  
 你可以添加<xref:System.Windows.Forms.ToolStripSeparator>在设计时通过从下拉列表中选择它。 但是，你可以还会自动创建<xref:System.Windows.Forms.ToolStripSeparator>通过键入连字符 （-） 在设计器的模板节点中或在<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法。  
  
### <a name="toolstripcontrolhost"></a>ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost>是的抽象基类<xref:System.Windows.Forms.ToolStripComboBox>， <xref:System.Windows.Forms.ToolStripTextBox>，和<xref:System.Windows.Forms.ToolStripProgressBar>。 <xref:System.Windows.Forms.ToolStripControlHost>可以托管其他控件，包括自定义控件，两种方式：  
  
-   构造<xref:System.Windows.Forms.ToolStripControlHost>与派生自的类<xref:System.Windows.Forms.Control>。 若要完全访问托管的控件和属性，必须强制转换<xref:System.Windows.Forms.ToolStripControlHost.Control%2A>于实际的属性类它表示。  
  
-   扩展<xref:System.Windows.Forms.ToolStripControlHost>，并在继承的类的默认构造函数调用基类构造函数并传递派生自的类<xref:System.Windows.Forms.Control>。 此选项允许你包装公共控件方法和属性中的轻松访问<xref:System.Windows.Forms.ToolStrip>。  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox>是<xref:System.Windows.Forms.ComboBox>进行承载而优化<xref:System.Windows.Forms.ToolStrip>。 托管的控件的属性和事件的一个子集公开在<xref:System.Windows.Forms.ToolStripComboBox>级别，但基础<xref:System.Windows.Forms.ComboBox>控件是完全可通过访问<xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A>属性。  
  
### <a name="toolstriptextbox"></a>ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox>是<xref:System.Windows.Forms.TextBox>进行承载而优化<xref:System.Windows.Forms.ToolStrip>。 托管的控件的属性和事件的一个子集公开在<xref:System.Windows.Forms.ToolStripTextBox>级别，但基础<xref:System.Windows.Forms.TextBox>控件是完全可通过访问<xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A>属性。  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar>是<xref:System.Windows.Forms.ProgressBar>进行承载而优化<xref:System.Windows.Forms.ToolStrip>。 托管的控件的属性和事件的一个子集公开在<xref:System.Windows.Forms.ToolStripProgressBar>级别，但基础<xref:System.Windows.Forms.ProgressBar>控件是完全可通过访问<xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A>属性。  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem>是的抽象基类<xref:System.Windows.Forms.ToolStripMenuItem>， <xref:System.Windows.Forms.ToolStripDropDownButton>，和<xref:System.Windows.Forms.ToolStripSplitButton>，这可以托管直接项或主机下拉容器中的其他项。 执行此操作通过设置<xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A>属性<xref:System.Windows.Forms.ToolStripDropDown>和设置<xref:System.Windows.Forms.ToolStrip.Items%2A>属性<xref:System.Windows.Forms.ToolStripDropDown>。 访问直接通过这些下拉列表项<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>属性。  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem>是<xref:System.Windows.Forms.ToolStripDropDownItem>适用于<xref:System.Windows.Forms.ToolStripDropDownMenu>和<xref:System.Windows.Forms.ContextMenuStrip>来处理菜单的特殊突出显示、 布局和列排列。  
  
### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton>看起来像<xref:System.Windows.Forms.ToolStripButton>，但它显示一个下拉列表区域，当用户单击它。 隐藏或显示的设置的下拉箭头<xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A>属性。 <xref:System.Windows.Forms.ToolStripDropDownButton>主机<xref:System.Windows.Forms.ToolStripOverflowButton>显示溢出的项<xref:System.Windows.Forms.ToolStrip>。  
  
### <a name="toolstripsplitbutton"></a>ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton>将按钮和下拉按钮功能的组合。  
  
 使用<xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A>属性来同步<xref:System.Windows.Forms.Control.Click>具有在按钮上显示的项的选择下拉列表项的事件。  
  
### <a name="toolstripitem-generic-features"></a>ToolStripItem 泛型功能  
 <xref:System.Windows.Forms.ToolStripItem>提供以下泛型功能和选项以继承控件：  
  
-   核心事件  
  
-   图像处理  
  
-   对齐  
  
-   文本和图像的关系  
  
-   显示样式  
  
#### <a name="core-events"></a>核心事件  
 <xref:System.Windows.Forms.ToolStripItem>控件接收其自己的单击、 鼠标，以及绘制事件，并且可以执行某些键盘还预处理。  
  
#### <a name="image-handling"></a>图像处理  
 <xref:System.Windows.Forms.ToolStripItem.Image%2A>， <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>， <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>， <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>，和<xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A>属性与图像处理的各个方面。 使用中的映像<xref:System.Windows.Forms.ToolStrip>控件通过设置这些属性直接或通过设置运行-– 仅限时间<xref:System.Windows.Forms.ToolStrip.ImageList%2A>属性。  
  
 图像缩放由属性中的交互<xref:System.Windows.Forms.ToolStrip>和<xref:System.Windows.Forms.ToolStripItem>、，如下所示：  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>是所确定的最终图像的图像的组合按比例<xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A>设置和容器的<xref:System.Windows.Forms.ToolStrip.AutoSize%2A>设置。  
  
    -   如果<xref:System.Windows.Forms.ToolStrip.AutoSize%2A>是`true`（默认值） 和<xref:System.Windows.Forms.ToolStripItemImageScaling>是<xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>，会发生任何图像缩放，和<xref:System.Windows.Forms.ToolStrip>大小是最大项或规定的最小大小。  
  
    -   如果<xref:System.Windows.Forms.ToolStrip.AutoSize%2A>是`false`和<xref:System.Windows.Forms.ToolStripItemImageScaling>是<xref:System.Windows.Forms.ToolStripItemImageScaling.None>，既不映像也不<xref:System.Windows.Forms.ToolStrip>会进行缩放。  
  
#### <a name="alignment"></a>对齐  
 值<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>属性确定的末尾<xref:System.Windows.Forms.ToolStrip>在出现的项。 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>属性时才起作用的布局样式<xref:System.Windows.Forms.ToolStrip>设置为堆栈溢出值之一。  
  
 项将置于<xref:System.Windows.Forms.ToolStrip>项项集合中的出现顺序。 若要以编程方式更改项的布局，请使用<xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A>方法可在集合中移动项。 此方法移动项，但不进行复制。  
  
#### <a name="text-and-image-relationship"></a>文本和图像关系  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>属性上定义图像相对于文本的相对位置<xref:System.Windows.Forms.ToolStripItem>。 中缺少映像、 文本或这两项，将被视为特殊情况下，以便<xref:System.Windows.Forms.ToolStripItem>不会显示为缺少的一个或多个元素的空白处。  
  
#### <a name="display-style"></a>显示样式  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>使用此选项可以显示你只想时设置的项的文本和图像属性的值。 这通常用于在不同的上下文中显示的相同项时更改仅显示样式。  
  
## <a name="accessory-classes"></a>附件类  
 提供各种其他功能的类包括：  
  
-   <xref:System.Windows.Forms.ToolStripManager>支持<xref:System.Windows.Forms.ToolStrip>-相关的任务对于整个应用程序，如合并、 设置和呈现器的选项。  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>允许你应用的特定样式或主题应用于<xref:System.Windows.Forms.ToolStrip>轻松。  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer>创建钢笔和画笔基于可替换颜色表 (<xref:System.Windows.Forms.ProfessionalColorTable>)。  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer>将系统颜色和到平面视觉样式<xref:System.Windows.Forms.ToolStrip>应用程序。  
  
-   <xref:System.Windows.Forms.ToolStripContainer>类似于<xref:System.Windows.Forms.SplitContainer>。 它使用四个停靠的侧面板 (的实例<xref:System.Windows.Forms.ToolStripPanel>) 和一个中间面板 (实例<xref:System.Windows.Forms.ToolStripContentPanel>) 若要创建典型的排列方式。 无法删除侧面板中，但你可以将其隐藏。 不能删除或隐藏中间面板。 一个或多个可以排列<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>，或<xref:System.Windows.Forms.StatusStrip>控件在侧面板中，并且你可以将其他控件使用中间面板。 <xref:System.Windows.Forms.ToolStripContentPanel>还使您能够获取到一致的外观窗体的正文的呈现器的支持。 <xref:System.Windows.Forms.ToolStripContainer>不支持多文档界面 (MDI)。  
  
-   <xref:System.Windows.Forms.ToolStripPanel>提供用于移动和排列空间<xref:System.Windows.Forms.ToolStrip>控件。 如果你这么选择，可以使用只有一个面板和<xref:System.Windows.Forms.ToolStripPanel>适用于 MDI 方案。  
  
## <a name="see-also"></a>另请参阅  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 技术摘要](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)  
 [ToolStrip 控件](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [MenuStrip 控件](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [StatusStrip 控件](../../../../docs/framework/winforms/controls/statusstrip-control.md)  
 [ContextMenuStrip 控件](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)  
 [BindingNavigator 控件](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
