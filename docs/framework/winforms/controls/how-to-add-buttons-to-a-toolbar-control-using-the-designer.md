---
title: "如何：使用设计器向 ToolBar 控件添加按钮"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5339d946f771b7ba187813dd67860aaa63a21eb3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a><span data-ttu-id="d2a0b-102">如何：使用设计器向 ToolBar 控件添加按钮</span><span class="sxs-lookup"><span data-stu-id="d2a0b-102">How to: Add Buttons to a ToolBar Control Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="d2a0b-103"><xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="d2a0b-104">不可或缺的组成部分<xref:System.Windows.Forms.ToolBar>控件是你向其添加的按钮。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="d2a0b-105">这些可用于提供轻松访问菜单命令，或者，或者，您可以将它们放置在另一个区域中的应用程序以向你的菜单结构中均不提供的用户公开的命令的用户界面。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>  
  
 <span data-ttu-id="d2a0b-106">下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control.</span></span> <span data-ttu-id="d2a0b-107">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-107">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2a0b-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d2a0b-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d2a0b-110">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-buttons-at-design-time"></a><span data-ttu-id="d2a0b-111">若要在设计时添加按钮</span><span class="sxs-lookup"><span data-stu-id="d2a0b-111">To add buttons at design time</span></span>  
  
1.  <span data-ttu-id="d2a0b-112">选择 <xref:System.Windows.Forms.ToolBar> 控件。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-112">Select the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2.  <span data-ttu-id="d2a0b-113">在**属性**窗口中，单击<xref:System.Windows.Forms.ToolBar.Buttons%2A>属性来选择它，然后单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**工具栏按钮集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-113">In the **Properties** window, click the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it and click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="d2a0b-114">使用**添加**和**删除**按钮来添加和删除按钮从<xref:System.Windows.Forms.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-114">Use the **Add** and **Remove** buttons to add and remove buttons from the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
4.  <span data-ttu-id="d2a0b-115">配置的属性中的单个按钮**属性**编辑器右侧的窗格中显示的窗口。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-115">Configure the properties of the individual buttons in the **Properties** window that appears in the pane on the right side of the editor.</span></span> <span data-ttu-id="d2a0b-116">下表显示需要考虑一些重要属性。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-116">The following table shows some important properties to consider.</span></span>  
  
    |<span data-ttu-id="d2a0b-117">属性</span><span class="sxs-lookup"><span data-stu-id="d2a0b-117">Property</span></span>|<span data-ttu-id="d2a0b-118">描述</span><span class="sxs-lookup"><span data-stu-id="d2a0b-118">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|<span data-ttu-id="d2a0b-119">设置要显示在下拉列表工具栏按钮的菜单。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-119">Sets the menu to be displayed in the drop-down toolbar button.</span></span> <span data-ttu-id="d2a0b-120">工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-120">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span></span> <span data-ttu-id="d2a0b-121">此属性采用的实例<xref:System.Windows.Forms.ContextMenu>作为引用的类。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-121">This property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|<span data-ttu-id="d2a0b-122">设置是否部分推送切换式工具栏按钮。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-122">Sets whether a toggle-style toolbar button is partially pushed.</span></span> <span data-ttu-id="d2a0b-123">工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-123">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|<span data-ttu-id="d2a0b-124">设置是否切换式工具栏按钮当前处于按下状态。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-124">Sets whether a toggle-style toolbar button is currently in the pushed state.</span></span> <span data-ttu-id="d2a0b-125">工具栏按钮的<xref:System.Windows.Forms.ToolBarButton.Style%2A>属性必须设置为<xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>或<xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-125">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> or <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|<span data-ttu-id="d2a0b-126">设置工具栏按钮的样式。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-126">Sets the style of the toolbar button.</span></span> <span data-ttu-id="d2a0b-127">必须是中的值之一<xref:System.Windows.Forms.ToolBarButtonStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-127">Must be one of the values in the <xref:System.Windows.Forms.ToolBarButtonStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|<span data-ttu-id="d2a0b-128">显示了按钮的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-128">The text string displayed by the button.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|<span data-ttu-id="d2a0b-129">为按钮的工具提示显示的文本。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-129">The text that appears as a ToolTip for the button.</span></span>|  
  
5.  <span data-ttu-id="d2a0b-130">单击**确定**以关闭对话框并创建您指定的面板。</span><span class="sxs-lookup"><span data-stu-id="d2a0b-130">Click **OK** to close the dialog box and create the panels you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a0b-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2a0b-131">See Also</span></span>  
 <xref:System.Windows.Forms.ToolBar>  
 [<span data-ttu-id="d2a0b-132">如何：定义 ToolBar 控件按钮的图标</span><span class="sxs-lookup"><span data-stu-id="d2a0b-132">How to: Define an Icon for a ToolBar Button</span></span>](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [<span data-ttu-id="d2a0b-133">如何：触发工具栏按钮的菜单事件</span><span class="sxs-lookup"><span data-stu-id="d2a0b-133">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [<span data-ttu-id="d2a0b-134">ToolBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="d2a0b-134">ToolBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [<span data-ttu-id="d2a0b-135">ToolBar 控件</span><span class="sxs-lookup"><span data-stu-id="d2a0b-135">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
