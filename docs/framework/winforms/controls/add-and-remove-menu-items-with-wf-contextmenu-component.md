---
title: 如何：使用 Windows 窗体 ContextMenu 组件添加和移除菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 5d1862b1fc1398f0f8c2217b51c4efb93db639af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957021"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="37b01-102">如何：使用 Windows 窗体 ContextMenu 组件添加和移除菜单项</span><span class="sxs-lookup"><span data-stu-id="37b01-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="37b01-103">说明如何在 Windows 窗体中添加和移除快捷菜单项。</span><span class="sxs-lookup"><span data-stu-id="37b01-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="37b01-104">Windows 窗体<xref:System.Windows.Forms.ContextMenu>组件提供了与所选对象相关的常用命令的菜单。</span><span class="sxs-lookup"><span data-stu-id="37b01-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="37b01-105">可以通过将<xref:System.Windows.Forms.MenuItem>对象添加<xref:System.Windows.Forms.Menu.MenuItems%2A>到集合来向快捷菜单添加项。</span><span class="sxs-lookup"><span data-stu-id="37b01-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="37b01-106">你可以从快捷菜单中永久删除项;但是, 在运行时, 可能更适合隐藏或禁用这些项。</span><span class="sxs-lookup"><span data-stu-id="37b01-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="37b01-107">尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu>将功能替换为以前版本的和控件, 并将其保留以实现后向兼容性和将来使用 (如果你选择)。 <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="37b01-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="37b01-108">从快捷菜单中删除项</span><span class="sxs-lookup"><span data-stu-id="37b01-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="37b01-109">使用组件的<xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> <xref:System.Windows.Forms.Menu.MenuItems%2A>集合<xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> 的或方法可移除<xref:System.Windows.Forms.ContextMenu>特定菜单项。</span><span class="sxs-lookup"><span data-stu-id="37b01-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     <span data-ttu-id="37b01-110">或</span><span class="sxs-lookup"><span data-stu-id="37b01-110">-or-</span></span>  
  
2. <span data-ttu-id="37b01-111">`MenuItems`使用组件集合的方法从菜单中删除所有项。 `Clear` <xref:System.Windows.Forms.ContextMenu></span><span class="sxs-lookup"><span data-stu-id="37b01-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="37b01-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="37b01-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="37b01-113">ContextMenu 组件</span><span class="sxs-lookup"><span data-stu-id="37b01-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="37b01-114">ContextMenu 组件概述</span><span class="sxs-lookup"><span data-stu-id="37b01-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
