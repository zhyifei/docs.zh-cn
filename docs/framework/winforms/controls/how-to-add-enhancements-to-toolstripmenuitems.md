---
title: 如何：向 ToolStripMenuItem 添加增强功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182323"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>如何：向 ToolStripMenuItem 添加增强功能
您可以通过以下方式增强 和<xref:System.Windows.Forms.MenuStrip><xref:System.Windows.Forms.ContextMenuStrip>控件的可用性：  
  
- 添加复选标记以指定要素是打开还是关闭，例如标尺是沿字处理应用程序的边距显示，还是指示显示文件列表中的文件，例如**窗口**菜单上的文件。  
  
- 添加视觉上表示菜单命令的图像。  
  
- 显示快捷键，以提供用于执行命令的鼠标的键盘替代方案。 例如，按 CTRL_C 执行**复制**命令。  
  
- 显示访问键，为菜单导航提供鼠标的键盘替代方案。 例如，按 ALT+F 选择 **"文件**"菜单。  
  
- 显示分隔线以对相关命令进行分组，并使菜单更具可读性。  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>在菜单命令上显示复选标记  
  
- 将其<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性设置为`true`。  
  
     这还将<xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>属性设置到`true`。 仅当希望菜单命令默认显示为选中时，才使用此过程，而不管是否选择了该命令。  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>显示每次单击更改状态的复选标记  
  
- 将菜单命令的属性<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>设置为`true`。  
  
### <a name="to-add-an-image-to-a-menu-command"></a>将图像添加到菜单命令  
  
- 将菜单命令的属性<xref:System.Windows.Forms.ToolStripItem.Image%2A>设置为图像的名称。 如果此<xref:System.Windows.Forms.ToolStripItemDisplayStyle>菜单命令的属性设置为<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>，则无法显示图像。  
  
> [!NOTE]
> 如果愿意，图像边距也可以显示复选标记。 此外，您可以将图像<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>的属性设置为`true`，并且图像将在运行时以填充边框出现在图像周围。  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>显示菜单命令的快捷键  
  
- 将<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>菜单命令的属性设置为所需的键盘组合，如 **"打开**"菜单命令的 CTRL_O，并将<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>该属性设置为`true`。  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>显示菜单命令的自定义快捷键  
  
- 将菜单命令的属性<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>设置为所需的键盘组合，如 CTRL_SHIFT_O 而不是 SHIFT_CTRL_O，并将<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>该属性设置为`true`。  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>显示菜单命令的访问键  
  
- 设置菜单命令的属性<xref:System.Windows.Forms.ToolStripItem.Text%2A>时，在要作为访问键下划线的字母之前输入一个 ampersand （&）。 例如，键入`&Open`作为菜单项<xref:System.Windows.Forms.ToolStripItem.Text%2A>的属性将导致菜单命令显示为<u>O</u>笔。
  
     要导航到此菜单命令，请按 ALT 将焦点<xref:System.Windows.Forms.MenuStrip>放在 上，然后按菜单名称的访问键。 当菜单打开并显示带有访问键的项目时，您只需按访问键即选择菜单命令。  
  
> [!NOTE]
> 避免定义重复的访问键，例如在同一菜单系统中两次定义 ALT+F。 无法保证重复访问密钥的选择顺序。  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>在菜单命令之间显示分隔符  
  
- <xref:System.Windows.Forms.MenuStrip>定义及其将包含的项目后，使用<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>或<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法按所需顺序将菜单命令和<xref:System.Windows.Forms.ToolStripSeparator>控件添加到 。 <xref:System.Windows.Forms.MenuStrip>  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,
    ' and the Save and Exit menu commands to the top-level File menu,
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,
    // and the Save and Exit menu commands to the top-level File menu,
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [MenuStrip 控件概述](menustrip-control-overview-windows-forms.md)
