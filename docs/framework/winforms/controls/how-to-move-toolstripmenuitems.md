---
title: 如何：移动 ToolStripMenuItem
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
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039799"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="dfa24-102">如何：移动 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="dfa24-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="dfa24-103">在设计时, 可以将整个顶级菜单及其菜单项移动到上<xref:System.Windows.Forms.MenuStrip>的其他位置。</span><span class="sxs-lookup"><span data-stu-id="dfa24-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="dfa24-104">您还可以在顶级菜单之间移动各个菜单项, 或更改菜单中菜单项的位置。</span><span class="sxs-lookup"><span data-stu-id="dfa24-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="dfa24-105">将顶级菜单及其菜单项移到另一个顶级位置</span><span class="sxs-lookup"><span data-stu-id="dfa24-105">To move a top-level menu and its menu items to another top-level location</span></span>

1. <span data-ttu-id="dfa24-106">单击并按住鼠标左键, 在要移动的菜单上单击鼠标左键。</span><span class="sxs-lookup"><span data-stu-id="dfa24-106">Click and hold down the left mouse button on the menu that you want to move.</span></span>

2. <span data-ttu-id="dfa24-107">将插入点拖到预期新位置之前的顶级菜单, 然后松开鼠标左键。</span><span class="sxs-lookup"><span data-stu-id="dfa24-107">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>

     <span data-ttu-id="dfa24-108">选定的菜单将移动到插入点的右侧。</span><span class="sxs-lookup"><span data-stu-id="dfa24-108">The selected menu moves to the right of the insertion point.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="dfa24-109">将顶级菜单及其菜单项移至下拉位置</span><span class="sxs-lookup"><span data-stu-id="dfa24-109">To move a top-level menu and its menu items to a drop-down location</span></span>

1. <span data-ttu-id="dfa24-110">左键单击要移动的菜单, 按 CTRL + X, 或右键单击菜单并从快捷菜单中选择 "**剪切**"。</span><span class="sxs-lookup"><span data-stu-id="dfa24-110">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="dfa24-111">在目标顶级菜单中, 左键单击预期新位置上方的菜单项, 然后按 CTRL + V, 或右键单击预期新位置上方的菜单项, 然后从快捷菜单中选择 "**粘贴**"。</span><span class="sxs-lookup"><span data-stu-id="dfa24-111">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="dfa24-112">您剪切的菜单将插入到所选菜单项之后。</span><span class="sxs-lookup"><span data-stu-id="dfa24-112">The menu that you cut is inserted after the selected menu item.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="dfa24-113">使用 Items 集合编辑器在菜单内移动菜单项</span><span class="sxs-lookup"><span data-stu-id="dfa24-113">To move a menu item within a menu using the Items Collection Editor</span></span>

1. <span data-ttu-id="dfa24-114">右键单击包含要移动的菜单项的菜单。</span><span class="sxs-lookup"><span data-stu-id="dfa24-114">Right-click the menu that contains the menu item you want to move.</span></span>

2. <span data-ttu-id="dfa24-115">在快捷菜单中, 选择 "**编辑 DropDownItems**"。</span><span class="sxs-lookup"><span data-stu-id="dfa24-115">From the shortcut menu, choose **Edit DropDownItems**.</span></span>

3. <span data-ttu-id="dfa24-116">在**项集合编辑器**中, 单击要移动的菜单项。</span><span class="sxs-lookup"><span data-stu-id="dfa24-116">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>

4. <span data-ttu-id="dfa24-117">单击向上键和向下键可在菜单中移动菜单项。</span><span class="sxs-lookup"><span data-stu-id="dfa24-117">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>

5. <span data-ttu-id="dfa24-118">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="dfa24-118">Click **OK**.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="dfa24-119">使用键盘在菜单内移动菜单项</span><span class="sxs-lookup"><span data-stu-id="dfa24-119">To move a menu item within a menu using the keyboard</span></span>

1. <span data-ttu-id="dfa24-120">按住 ALT 键。</span><span class="sxs-lookup"><span data-stu-id="dfa24-120">Press and hold down the ALT key.</span></span>

2. <span data-ttu-id="dfa24-121">单击并按住鼠标左键, 在要移动的菜单项上单击鼠标左键。</span><span class="sxs-lookup"><span data-stu-id="dfa24-121">Click and hold the left mouse button on the menu item that you want to move.</span></span>

3. <span data-ttu-id="dfa24-122">将菜单项拖到新位置, 然后释放鼠标左键。</span><span class="sxs-lookup"><span data-stu-id="dfa24-122">Drag the menu item to the new location and release the left mouse button.</span></span>

## <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="dfa24-123">将菜单项移动到另一个菜单</span><span class="sxs-lookup"><span data-stu-id="dfa24-123">To move a menu item to another menu</span></span>

1. <span data-ttu-id="dfa24-124">左键单击要移动的菜单项, 然后按 CTRL + X, 或右键单击菜单项, 然后从快捷菜单中选择 "**剪切**"。</span><span class="sxs-lookup"><span data-stu-id="dfa24-124">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="dfa24-125">左键单击将包含您剪切的菜单项的菜单。</span><span class="sxs-lookup"><span data-stu-id="dfa24-125">Left-click the menu that will contain the menu item that you cut.</span></span>

3. <span data-ttu-id="dfa24-126">左键单击预期新位置之前的菜单项, 按 CTRL + V, 或右键单击预期新位置之前的菜单项, 然后从快捷菜单中选择 "**粘贴**"。</span><span class="sxs-lookup"><span data-stu-id="dfa24-126">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="dfa24-127">您剪切的菜单项将插入到所选菜单项之后。</span><span class="sxs-lookup"><span data-stu-id="dfa24-127">The menu item that you cut is inserted after the selected menu item.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfa24-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa24-128">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="dfa24-129">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="dfa24-129">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
