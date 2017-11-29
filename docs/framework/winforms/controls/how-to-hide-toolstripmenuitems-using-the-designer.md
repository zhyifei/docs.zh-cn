---
title: "如何：使用设计器隐藏 ToolStripMenuItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9549fa11b3f019dce3cc77d5f6d1d08a8485f0cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="3fe6a-102">如何：使用设计器隐藏 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="3fe6a-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="3fe6a-103">隐藏菜单项是一种方法来控制你的应用程序的用户界面 (UI)，并限制用户命令。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="3fe6a-104">通常情况下，你将想要隐藏整个菜单的菜单项在其上的所有时不可用。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="3fe6a-105">这会带来较少的用户的干扰。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="3fe6a-106">此外，你可能想要同时隐藏和禁用的菜单或菜单项，如隐藏单独不会阻止用户使用的快捷键访问菜单命令。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="3fe6a-107">禁用菜单项的详细信息，请参阅[如何： 禁用 ToolStripMenuItems 使用设计器](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fe6a-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3fe6a-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3fe6a-110">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="3fe6a-111">若要隐藏顶级菜单及其子菜单项</span><span class="sxs-lookup"><span data-stu-id="3fe6a-111">To hide a top-level menu and its submenu items</span></span>  
  
1.  <span data-ttu-id="3fe6a-112">选择的顶级菜单项并设置其<xref:System.Windows.Forms.ToolStripItem.Visible%2A>或<xref:System.Windows.Forms.ToolStripItem.Available%2A>属性`false`。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="3fe6a-113">如果你隐藏顶级菜单项，都将隐藏该菜单中的所有菜单项。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="3fe6a-114">如果你单击以外的某处上<xref:System.Windows.Forms.MenuStrip>后设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>到`false`，整个顶级菜单项和及其子菜单项从窗体中，因此显示你的操作的运行时效果消失。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="3fe6a-115">若要在设计时显示隐藏的顶级菜单项，请单击<xref:System.Windows.Forms.MenuStrip>中**组件栏**中**文档大纲**，或在属性网格的顶部。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fe6a-116">极少数情况下将隐藏整个菜单合并方案中的多个文档界面 (MDI) 子菜单除外。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="3fe6a-117">若要隐藏子菜单项</span><span class="sxs-lookup"><span data-stu-id="3fe6a-117">To hide a submenu item</span></span>  
  
1.  <span data-ttu-id="3fe6a-118">选择的子菜单项并设置其<xref:System.Windows.Forms.ToolStripItem.Visible%2A>属性`false`。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="3fe6a-119">当隐藏子菜单项时，它将一直显示在设计时窗体上，以便可以轻松地选择它进行进一步的工作。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="3fe6a-120">它将实际被隐藏在运行时。</span><span class="sxs-lookup"><span data-stu-id="3fe6a-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe6a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fe6a-121">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [<span data-ttu-id="3fe6a-122">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="3fe6a-122">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="3fe6a-123">如何：使用设计器禁用 ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="3fe6a-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
