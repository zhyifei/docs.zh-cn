---
title: 添加和删除具有 ContextMenu 组件的菜单项
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
ms.openlocfilehash: 989ab6d47ec761930a32f542b5fa1136e831f73d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746280"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="f4cb1-102">如何：使用 Windows 窗体 ContextMenu 组件添加和移除菜单项</span><span class="sxs-lookup"><span data-stu-id="f4cb1-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="f4cb1-103">说明如何在 Windows 窗体中添加和移除快捷菜单项。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="f4cb1-104">Windows 窗体 <xref:System.Windows.Forms.ContextMenu> 组件提供了与所选对象相关的常用命令的菜单。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="f4cb1-105">可以通过将 <xref:System.Windows.Forms.MenuItem> 对象添加到 <xref:System.Windows.Forms.Menu.MenuItems%2A> 集合来向快捷菜单添加项。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="f4cb1-106">你可以从快捷菜单中永久删除项;但是，在运行时，可能更适合隐藏或禁用这些项。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f4cb1-107">尽管 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ContextMenuStrip> 将功能替换并添加到以前版本的 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 控件中，但 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 会保留，以实现向后兼容性和将来使用（如果你选择）。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="f4cb1-108">从快捷菜单中删除项</span><span class="sxs-lookup"><span data-stu-id="f4cb1-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="f4cb1-109">使用 <xref:System.Windows.Forms.ContextMenu> 组件的 <xref:System.Windows.Forms.Menu.MenuItems%2A> 集合的 <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> 或 <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> 方法来删除特定菜单项。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
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
  
     <span data-ttu-id="f4cb1-110">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="f4cb1-110">-or-</span></span>  
  
2. <span data-ttu-id="f4cb1-111">使用 <xref:System.Windows.Forms.ContextMenu> 组件的 `MenuItems` 集合的 `Clear` 方法从菜单中删除所有项。</span><span class="sxs-lookup"><span data-stu-id="f4cb1-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f4cb1-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4cb1-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="f4cb1-113">ContextMenu 组件</span><span class="sxs-lookup"><span data-stu-id="f4cb1-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="f4cb1-114">ContextMenu 组件概述</span><span class="sxs-lookup"><span data-stu-id="f4cb1-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
