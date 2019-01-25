---
title: 如何：Move ToolStripMenuItems
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 12554ee2225dbb186392b910ddfd7c2f69695e7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660211"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="578c2-102">如何：Move ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="578c2-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="578c2-103">在设计时，您可以将移动整个顶级菜单及其菜单项到其他位置<xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="578c2-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="578c2-104">您还可以顶级菜单之间移动单个菜单项或更改菜单中的菜单项的位置。</span><span class="sxs-lookup"><span data-stu-id="578c2-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="578c2-105">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="578c2-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="578c2-106">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="578c2-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="578c2-107">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="578c2-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="578c2-108">若要将顶级菜单和菜单项移动到另一个顶级位置</span><span class="sxs-lookup"><span data-stu-id="578c2-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="578c2-109">单击并按住鼠标左键在你想要移动的菜单上。</span><span class="sxs-lookup"><span data-stu-id="578c2-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2.  <span data-ttu-id="578c2-110">将插入点拖到预期的新位置之前的顶级菜单并释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="578c2-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="578c2-111">所选的菜单将插入点右移。</span><span class="sxs-lookup"><span data-stu-id="578c2-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="578c2-112">若要将顶级菜单及其菜单项移动到下拉列表位置</span><span class="sxs-lookup"><span data-stu-id="578c2-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="578c2-113">左键单击想要移动并按 CTRL + X，或右键单击该菜单并选择**剪切**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="578c2-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="578c2-114">在目标顶级菜单中，左键单击预期新位置上方的菜单项，按 CTRL + V，或右键单击预期新位置上方的菜单项并选择**粘贴**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="578c2-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="578c2-115">你将剪切的菜单将插入到所选的菜单项之后。</span><span class="sxs-lookup"><span data-stu-id="578c2-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="578c2-116">若要移动菜单使用项集合编辑器中的菜单项</span><span class="sxs-lookup"><span data-stu-id="578c2-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1.  <span data-ttu-id="578c2-117">右键单击包含你想要移动的菜单项的菜单。</span><span class="sxs-lookup"><span data-stu-id="578c2-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2.  <span data-ttu-id="578c2-118">从快捷菜单中，选择**编辑 Dropdownitem**。</span><span class="sxs-lookup"><span data-stu-id="578c2-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3.  <span data-ttu-id="578c2-119">在中**项集合编辑器**，左键单击想要移动的菜单项。</span><span class="sxs-lookup"><span data-stu-id="578c2-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4.  <span data-ttu-id="578c2-120">单击向上和向下箭头键移动菜单内的菜单项。</span><span class="sxs-lookup"><span data-stu-id="578c2-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5.  <span data-ttu-id="578c2-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="578c2-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="578c2-122">若要移动菜单项在菜单中使用键盘</span><span class="sxs-lookup"><span data-stu-id="578c2-122">To move a menu item within a menu using the keyboard</span></span>  
  
1.  <span data-ttu-id="578c2-123">按住 ALT 键。</span><span class="sxs-lookup"><span data-stu-id="578c2-123">Press and hold down the ALT key.</span></span>  
  
2.  <span data-ttu-id="578c2-124">单击并按住鼠标左键你想要移动的菜单项。</span><span class="sxs-lookup"><span data-stu-id="578c2-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3.  <span data-ttu-id="578c2-125">将菜单项拖动到新位置并释放鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="578c2-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="578c2-126">若要移动到另一个菜单的菜单项</span><span class="sxs-lookup"><span data-stu-id="578c2-126">To move a menu item to another menu</span></span>  
  
1.  <span data-ttu-id="578c2-127">左键单击想要移动并按 CTRL + X，或右键单击菜单项和选择的菜单项**剪切**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="578c2-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="578c2-128">左键单击将包含您剪切菜单项的菜单。</span><span class="sxs-lookup"><span data-stu-id="578c2-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3.  <span data-ttu-id="578c2-129">左键单击预期新位置之前的菜单项并按 CTRL + V，或右键单击预期新位置并选择之前的菜单项**粘贴**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="578c2-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="578c2-130">您剪切菜单项将插入所选的菜单项之后。</span><span class="sxs-lookup"><span data-stu-id="578c2-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="578c2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="578c2-131">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="578c2-132">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="578c2-132">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
