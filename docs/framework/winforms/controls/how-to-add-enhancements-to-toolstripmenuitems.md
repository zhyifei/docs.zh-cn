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
ms.openlocfilehash: 37843d27211bd07c2749b3e6fc14ec03d7bf570d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="3d8dd-102">如何：向 ToolStripMenuItem 添加增强功能</span><span class="sxs-lookup"><span data-stu-id="3d8dd-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="3d8dd-103">你可以增强的可用性<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>通过以下方式控件：</span><span class="sxs-lookup"><span data-stu-id="3d8dd-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="3d8dd-104">添加复选标记来指定是否打开或关闭，打开某项功能，如是否沿字处理应用程序，边距显示标尺或来表示文件的文件的列表中的哪正在显示，此类上**窗口**菜单。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="3d8dd-105">添加以可视方式表示菜单命令的图像。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="3d8dd-106">显示键盘快捷方式，以用于执行命令提供鼠标键盘代替。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="3d8dd-107">例如，按 CTRL + C 执行**复制**命令。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="3d8dd-108">显示访问键，以提供了键盘替代方式鼠标菜单导航。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="3d8dd-109">例如，按 ALT + F 选择**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="3d8dd-110">显示分隔条来分组相关命令，并使菜单更具可读性。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="3d8dd-111">在菜单命令上显示一个复选标记</span><span class="sxs-lookup"><span data-stu-id="3d8dd-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="3d8dd-112">设置其<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="3d8dd-113">这还将设置<xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="3d8dd-114">只有当您想要显示默认情况下，无论是否选中的菜单命令，请使用此过程。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="3d8dd-115">若要显示每个只需单击的状态更改的选中标记</span><span class="sxs-lookup"><span data-stu-id="3d8dd-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="3d8dd-116">设置该菜单命令的<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="3d8dd-117">若要将图像添加到菜单命令</span><span class="sxs-lookup"><span data-stu-id="3d8dd-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="3d8dd-118">设置该菜单命令的<xref:System.Windows.Forms.ToolStripItem.Image%2A>到的映像名称的属性。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="3d8dd-119">如果<xref:System.Windows.Forms.ToolStripItemDisplayStyle>此菜单命令属性设置为<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>，无法显示图像。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d8dd-120">图像边距还可以显示一个复选标记是否您选择。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="3d8dd-121">此外，你可以设置<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性使图像的`true`，并且该映像将在运行时显示阴影边框。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="3d8dd-122">若要显示的菜单命令的快捷键</span><span class="sxs-lookup"><span data-stu-id="3d8dd-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="3d8dd-123">设置该菜单命令的<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>属性设置为所需的键盘相结合，例如 CTRL + O 如**打开**菜单命令和组<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="3d8dd-124">若要显示的菜单命令的自定义快捷键</span><span class="sxs-lookup"><span data-stu-id="3d8dd-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="3d8dd-125">设置该菜单命令的<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>属性设置为所需的键盘相结合，例如 CTRL + SHIFT + O 而不是 SHIFT + CTRL + O，和组<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="3d8dd-126">若要显示的菜单命令的访问密钥</span><span class="sxs-lookup"><span data-stu-id="3d8dd-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="3d8dd-127">当你将设置<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性菜单命令中，输入与号 (&) 你想要为访问键显示为带有下划线的字母前。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="3d8dd-128">例如，键入`&Open`作为<xref:System.Windows.Forms.ToolStripItem.Text%2A>的菜单项的属性将导致显示为菜单命令**O**钢笔。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as **O**pen.</span></span>  
  
     <span data-ttu-id="3d8dd-129">若要导航到此菜单命令，请按 alt 键，将焦点移到<xref:System.Windows.Forms.MenuStrip>，按菜单名称的访问密钥。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="3d8dd-130">当菜单打开并显示带访问键的项时，你只需按下访问键来选择菜单命令。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d8dd-131">避免定义重复的访问键，如两次在同一个菜单系统中定义 ALT + F。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="3d8dd-132">不能保证重复的访问键的选择顺序。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="3d8dd-133">若要显示的菜单命令之间的分隔条</span><span class="sxs-lookup"><span data-stu-id="3d8dd-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="3d8dd-134">在定义后你<xref:System.Windows.Forms.MenuStrip>和它将包含的项使用<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>或<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法将添加菜单命令和<xref:System.Windows.Forms.ToolStripSeparator>控件添加到<xref:System.Windows.Forms.MenuStrip>你希望的顺序。</span><span class="sxs-lookup"><span data-stu-id="3d8dd-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d8dd-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d8dd-135">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="3d8dd-136">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="3d8dd-136">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
