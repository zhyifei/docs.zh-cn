---
title: 如何：向 Toolstripmenuitem 添加增强功能
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
ms.openlocfilehash: 68a926eba184d12d58e537d8db0a5baefb0fbe95
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719320"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="ae9fb-102">如何：向 Toolstripmenuitem 添加增强功能</span><span class="sxs-lookup"><span data-stu-id="ae9fb-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="ae9fb-103">你可以增强的可用性<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>中通过以下方式控件：</span><span class="sxs-lookup"><span data-stu-id="ae9fb-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="ae9fb-104">添加复选标记来指定是否打开或关闭，打开某项功能，如是否沿字处理应用程序的边距显示标尺，或以指示列表中的文件的文件上未显示，例如**窗口**菜单。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="ae9fb-105">添加直观地表示菜单命令的图像。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="ae9fb-106">显示键盘快捷方式，以提供用于执行命令的键盘代替鼠标。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="ae9fb-107">例如，按 CTRL + C 执行**复制**命令。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="ae9fb-108">显示访问密钥的菜单导航提供鼠标键盘替代方法。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="ae9fb-109">例如，按 ALT + F 将选择**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="ae9fb-110">显示分隔条以组相关的命令，并使菜单更具可读性。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="ae9fb-111">若要显示一个复选标记上的菜单命令</span><span class="sxs-lookup"><span data-stu-id="ae9fb-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="ae9fb-112">设置其<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="ae9fb-113">它还会设置<xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="ae9fb-114">仅当你想要显示为默认情况下，无论是否选中为选中的菜单命令，请使用此过程。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="ae9fb-115">若要显示与每次单击状态更改的选中标记</span><span class="sxs-lookup"><span data-stu-id="ae9fb-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="ae9fb-116">设置菜单命令<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="ae9fb-117">若要将图像添加到菜单命令</span><span class="sxs-lookup"><span data-stu-id="ae9fb-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="ae9fb-118">设置菜单命令的<xref:System.Windows.Forms.ToolStripItem.Image%2A>属性设置为映像的名称。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="ae9fb-119">如果<xref:System.Windows.Forms.ToolStripItemDisplayStyle>此菜单命令属性设置为<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>，不能显示该图像。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae9fb-120">图像边距还可以显示一个复选标记是否您选择。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="ae9fb-121">此外，可以设置<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性的映像`true`，和与阴影边框，该图像将显示在运行时。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="ae9fb-122">若要显示的菜单命令快捷键</span><span class="sxs-lookup"><span data-stu-id="ae9fb-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="ae9fb-123">设置菜单命令<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>属性设置为所需的键盘组合，例如 CTRL + O 则表示**开放**菜单命令，并设置<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="ae9fb-124">若要显示的菜单命令的自定义快捷键</span><span class="sxs-lookup"><span data-stu-id="ae9fb-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="ae9fb-125">设置菜单命令<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A>属性设置为所需的键盘组合，例如 CTRL + SHIFT + O 而不是 SHIFT + CTRL + O 和集<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="ae9fb-126">若要显示的菜单命令的访问密钥</span><span class="sxs-lookup"><span data-stu-id="ae9fb-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="ae9fb-127">当您将设置<xref:System.Windows.Forms.ToolStripItem.Text%2A>菜单命令属性中输入与号 (&) 想要访问密钥作为带有下划线的字母前。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="ae9fb-128">例如，如果键入`&Open`作为<xref:System.Windows.Forms.ToolStripItem.Text%2A>菜单项的属性将导致显示为菜单命令<u>O</u>笔。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="ae9fb-129">若要导航到此菜单命令，请按 alt 键，将焦点设置到<xref:System.Windows.Forms.MenuStrip>，按菜单名称的访问密钥。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="ae9fb-130">当菜单打开并显示带访问键的项时，只需按下访问键来选择菜单命令。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae9fb-131">避免定义重复的访问密钥，如两次在同一个菜单系统中定义 ALT + F。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="ae9fb-132">不能保证重复的访问键的选择顺序。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="ae9fb-133">若要显示的菜单命令之间的分隔条</span><span class="sxs-lookup"><span data-stu-id="ae9fb-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="ae9fb-134">定义后你<xref:System.Windows.Forms.MenuStrip>和它将包含的项使用<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>或<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法添加的菜单命令和<xref:System.Windows.Forms.ToolStripSeparator>控件添加到<xref:System.Windows.Forms.MenuStrip>中所需的顺序。</span><span class="sxs-lookup"><span data-stu-id="ae9fb-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae9fb-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae9fb-135">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="ae9fb-136">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="ae9fb-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
