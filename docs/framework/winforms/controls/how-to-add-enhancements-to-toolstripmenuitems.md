---
title: "如何：向 ToolStripMenuItem 添加增强功能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2701094ffcbcf7eeb14444163b995816398876fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a>如何：向 ToolStripMenuItem 添加增强功能
你可以增强的可用性<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>通过以下方式控件：  
  
-   添加复选标记来指定是否打开或关闭，打开某项功能，如是否沿字处理应用程序，边距显示标尺或来表示文件的文件的列表中的哪正在显示，此类上**窗口**菜单。  
  
-   添加以可视方式表示菜单命令的图像。  
  
-   显示键盘快捷方式，以用于执行命令提供鼠标键盘代替。 例如，按 CTRL + C 执行**复制**命令。  
  
-   显示访问键，以提供了键盘替代方式鼠标菜单导航。 例如，按 ALT + F 选择**文件**菜单。  
  
-   显示分隔条来分组相关命令，并使菜单更具可读性。  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a>在菜单命令上显示一个复选标记  
  
-   设置其<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性`true`。  
  
     这还将设置<xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>属性`true`。 只有当您想要显示默认情况下，无论是否选中的菜单命令，请使用此过程。  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a>若要显示每个只需单击的状态更改的选中标记  
  
-   设置该菜单命令的<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>属性`true`。  
  
### <a name="to-add-an-image-to-a-menu-command"></a>若要将图像添加到菜单命令  
  
-   设置该菜单命令的<xref:System.Windows.Forms.ToolStripItem.Image%2A>到的映像名称的属性。 如果<xref:System.Windows.Forms.ToolStripItemDisplayStyle>此菜单命令属性设置为<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>，无法显示图像。  
  
> [!NOTE]
>  图像边距还可以显示一个复选标记是否您选择。 此外，你可以设置<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性使图像的`true`，并且该映像将在运行时显示阴影边框。  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a>若要显示的菜单命令的快捷键  
  
-   设置该菜单命令的<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>属性设置为所需的键盘相结合，例如 CTRL + O 如**打开**菜单命令和组<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>属性`true`。  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a>若要显示的菜单命令的自定义快捷键  
  
-   设置该菜单命令的<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>属性设置为所需的键盘相结合，例如 CTRL + SHIFT + O 而不是 SHIFT + CTRL + O，和组<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>属性`true`。  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a>若要显示的菜单命令的访问密钥  
  
-   当你将设置<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性菜单命令中，输入与号 (&) 你想要为访问键显示为带有下划线的字母前。 例如，键入`&Open`作为<xref:System.Windows.Forms.ToolStripItem.Text%2A>的菜单项的属性将导致显示为菜单命令**O**钢笔。  
  
     若要导航到此菜单命令，请按 alt 键，将焦点移到<xref:System.Windows.Forms.MenuStrip>，按菜单名称的访问密钥。 当菜单打开并显示带访问键的项时，你只需按下访问键来选择菜单命令。  
  
> [!NOTE]
>  避免定义重复的访问键，如两次在同一个菜单系统中定义 ALT + F。 不能保证重复的访问键的选择顺序。  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a>若要显示的菜单命令之间的分隔条  
  
-   在定义后你<xref:System.Windows.Forms.MenuStrip>和它将包含的项使用<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>或<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法将添加菜单命令和<xref:System.Windows.Forms.ToolStripSeparator>控件添加到<xref:System.Windows.Forms.MenuStrip>你希望的顺序。  
  
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
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [MenuStrip 控件概述](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
