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
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="ee6a8-102">如何：向 ToolStripMenuItem 添加增强功能</span><span class="sxs-lookup"><span data-stu-id="ee6a8-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="ee6a8-103">您可以通过以下方式增强 和<xref:System.Windows.Forms.MenuStrip><xref:System.Windows.Forms.ContextMenuStrip>控件的可用性：</span><span class="sxs-lookup"><span data-stu-id="ee6a8-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="ee6a8-104">添加复选标记以指定要素是打开还是关闭，例如标尺是沿字处理应用程序的边距显示，还是指示显示文件列表中的文件，例如**窗口**菜单上的文件。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="ee6a8-105">添加视觉上表示菜单命令的图像。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="ee6a8-106">显示快捷键，以提供用于执行命令的鼠标的键盘替代方案。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="ee6a8-107">例如，按 CTRL_C 执行**复制**命令。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="ee6a8-108">显示访问键，为菜单导航提供鼠标的键盘替代方案。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="ee6a8-109">例如，按 ALT+F 选择 **"文件**"菜单。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="ee6a8-110">显示分隔线以对相关命令进行分组，并使菜单更具可读性。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="ee6a8-111">在菜单命令上显示复选标记</span><span class="sxs-lookup"><span data-stu-id="ee6a8-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="ee6a8-112">将其<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="ee6a8-113">这还将<xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>属性设置到`true`。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="ee6a8-114">仅当希望菜单命令默认显示为选中时，才使用此过程，而不管是否选择了该命令。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="ee6a8-115">显示每次单击更改状态的复选标记</span><span class="sxs-lookup"><span data-stu-id="ee6a8-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="ee6a8-116">将菜单命令的属性<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="ee6a8-117">将图像添加到菜单命令</span><span class="sxs-lookup"><span data-stu-id="ee6a8-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="ee6a8-118">将菜单命令的属性<xref:System.Windows.Forms.ToolStripItem.Image%2A>设置为图像的名称。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="ee6a8-119">如果此<xref:System.Windows.Forms.ToolStripItemDisplayStyle>菜单命令的属性设置为<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>，则无法显示图像。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee6a8-120">如果愿意，图像边距也可以显示复选标记。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="ee6a8-121">此外，您可以将图像<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>的属性设置为`true`，并且图像将在运行时以填充边框出现在图像周围。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="ee6a8-122">显示菜单命令的快捷键</span><span class="sxs-lookup"><span data-stu-id="ee6a8-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="ee6a8-123">将<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>菜单命令的属性设置为所需的键盘组合，如 **"打开**"菜单命令的 CTRL_O，并将<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>该属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="ee6a8-124">显示菜单命令的自定义快捷键</span><span class="sxs-lookup"><span data-stu-id="ee6a8-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="ee6a8-125">将菜单命令的属性<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>设置为所需的键盘组合，如 CTRL_SHIFT_O 而不是 SHIFT_CTRL_O，并将<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>该属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="ee6a8-126">显示菜单命令的访问键</span><span class="sxs-lookup"><span data-stu-id="ee6a8-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="ee6a8-127">设置菜单命令的属性<xref:System.Windows.Forms.ToolStripItem.Text%2A>时，在要作为访问键下划线的字母之前输入一个 ampersand （&）。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="ee6a8-128">例如，键入`&Open`作为菜单项<xref:System.Windows.Forms.ToolStripItem.Text%2A>的属性将导致菜单命令显示为<u>O</u>笔。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="ee6a8-129">要导航到此菜单命令，请按 ALT 将焦点<xref:System.Windows.Forms.MenuStrip>放在 上，然后按菜单名称的访问键。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="ee6a8-130">当菜单打开并显示带有访问键的项目时，您只需按访问键即选择菜单命令。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee6a8-131">避免定义重复的访问键，例如在同一菜单系统中两次定义 ALT+F。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="ee6a8-132">无法保证重复访问密钥的选择顺序。</span><span class="sxs-lookup"><span data-stu-id="ee6a8-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="ee6a8-133">在菜单命令之间显示分隔符</span><span class="sxs-lookup"><span data-stu-id="ee6a8-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="ee6a8-134"><xref:System.Windows.Forms.MenuStrip>定义及其将包含的项目后，使用<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>或<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法按所需顺序将菜单命令和<xref:System.Windows.Forms.ToolStripSeparator>控件添加到 。 <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="ee6a8-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ee6a8-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee6a8-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="ee6a8-136">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="ee6a8-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
