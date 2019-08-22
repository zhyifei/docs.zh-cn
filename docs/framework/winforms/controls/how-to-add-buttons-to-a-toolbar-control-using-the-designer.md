---
title: 如何：使用设计器向 ToolBar 控件添加按钮
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: 4d7a49633599aabc96153e4793e50c1a4d6d092d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666223"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a><span data-ttu-id="3dd17-102">如何：使用设计器向 ToolBar 控件添加按钮</span><span class="sxs-lookup"><span data-stu-id="3dd17-102">How to: Add Buttons to a ToolBar Control Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="3dd17-103"><xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="3dd17-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="3dd17-104"><xref:System.Windows.Forms.ToolBar>控件的一个组成部分是您向其中添加的按钮。</span><span class="sxs-lookup"><span data-stu-id="3dd17-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="3dd17-105">可以使用这些命令来轻松访问菜单命令或, 也可以将其放置在应用程序的用户界面的另一个区域中, 向用户提供菜单结构中不存在的命令。</span><span class="sxs-lookup"><span data-stu-id="3dd17-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>

<span data-ttu-id="3dd17-106">下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.ToolBar>包含控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="3dd17-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control.</span></span> <span data-ttu-id="3dd17-107">有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="3dd17-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-buttons-at-design-time"></a><span data-ttu-id="3dd17-108">在设计时添加按钮</span><span class="sxs-lookup"><span data-stu-id="3dd17-108">To add buttons at design time</span></span>

1. <span data-ttu-id="3dd17-109">选择 <xref:System.Windows.Forms.ToolBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="3dd17-109">Select the <xref:System.Windows.Forms.ToolBar> control.</span></span>

2. <span data-ttu-id="3dd17-110">在 "**属性**" 窗口中, <xref:System.Windows.Forms.ToolBar.Buttons%2A>单击属性以将其选中,然后![单击 "Visual Studio](./media/visual-studio-ellipsis-button.png)属性窗口中的省略号按钮 (...)" 以打开**ToolBarButton集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="3dd17-110">In the **Properties** window, click the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it and click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

3. <span data-ttu-id="3dd17-111">使用 "**添加**" 和 "**删除**" 按钮可在<xref:System.Windows.Forms.ToolBar>控件中添加和删除按钮。</span><span class="sxs-lookup"><span data-stu-id="3dd17-111">Use the **Add** and **Remove** buttons to add and remove buttons from the <xref:System.Windows.Forms.ToolBar> control.</span></span>

4. <span data-ttu-id="3dd17-112">在编辑器右侧窗格中显示的 "**属性**" 窗口中, 配置各个按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="3dd17-112">Configure the properties of the individual buttons in the **Properties** window that appears in the pane on the right side of the editor.</span></span> <span data-ttu-id="3dd17-113">下表显示要考虑的一些重要属性。</span><span class="sxs-lookup"><span data-stu-id="3dd17-113">The following table shows some important properties to consider.</span></span>

    |<span data-ttu-id="3dd17-114">属性</span><span class="sxs-lookup"><span data-stu-id="3dd17-114">Property</span></span>|<span data-ttu-id="3dd17-115">描述</span><span class="sxs-lookup"><span data-stu-id="3dd17-115">Description</span></span>|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|<span data-ttu-id="3dd17-116">设置要显示在下拉工具栏按钮中的菜单。</span><span class="sxs-lookup"><span data-stu-id="3dd17-116">Sets the menu to be displayed in the drop-down toolbar button.</span></span> <span data-ttu-id="3dd17-117">工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>。</span><span class="sxs-lookup"><span data-stu-id="3dd17-117">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span></span> <span data-ttu-id="3dd17-118">此属性采用<xref:System.Windows.Forms.ContextMenu>类的实例作为引用。</span><span class="sxs-lookup"><span data-stu-id="3dd17-118">This property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|<span data-ttu-id="3dd17-119">设置是否部分推送切换样式的工具栏按钮。</span><span class="sxs-lookup"><span data-stu-id="3dd17-119">Sets whether a toggle-style toolbar button is partially pushed.</span></span> <span data-ttu-id="3dd17-120">工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>。</span><span class="sxs-lookup"><span data-stu-id="3dd17-120">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|<span data-ttu-id="3dd17-121">设置切换样式的工具栏按钮当前是否处于按下状态。</span><span class="sxs-lookup"><span data-stu-id="3dd17-121">Sets whether a toggle-style toolbar button is currently in the pushed state.</span></span> <span data-ttu-id="3dd17-122">工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>或<xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>。</span><span class="sxs-lookup"><span data-stu-id="3dd17-122">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> or <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|<span data-ttu-id="3dd17-123">设置工具栏按钮的样式。</span><span class="sxs-lookup"><span data-stu-id="3dd17-123">Sets the style of the toolbar button.</span></span> <span data-ttu-id="3dd17-124">必须是<xref:System.Windows.Forms.ToolBarButtonStyle>枚举中的值之一。</span><span class="sxs-lookup"><span data-stu-id="3dd17-124">Must be one of the values in the <xref:System.Windows.Forms.ToolBarButtonStyle> enumeration.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|<span data-ttu-id="3dd17-125">按钮显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="3dd17-125">The text string displayed by the button.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|<span data-ttu-id="3dd17-126">作为按钮的工具提示显示的文本。</span><span class="sxs-lookup"><span data-stu-id="3dd17-126">The text that appears as a ToolTip for the button.</span></span>|

5. <span data-ttu-id="3dd17-127">单击 **"确定"** 以关闭对话框并创建指定的面板。</span><span class="sxs-lookup"><span data-stu-id="3dd17-127">Click **OK** to close the dialog box and create the panels you specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="3dd17-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dd17-128">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="3dd17-129">如何：定义工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="3dd17-129">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="3dd17-130">如何：工具栏按钮的触发器菜单事件</span><span class="sxs-lookup"><span data-stu-id="3dd17-130">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="3dd17-131">ToolBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="3dd17-131">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)
- [<span data-ttu-id="3dd17-132">ToolBar 控件</span><span class="sxs-lookup"><span data-stu-id="3dd17-132">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
