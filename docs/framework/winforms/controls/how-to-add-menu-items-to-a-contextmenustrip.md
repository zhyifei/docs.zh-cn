---
title: "如何：向 ContextMenuStrip 添加菜单项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad9aa3ced90793b8051b377f499c94466bc3751a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="d8af6-102">如何：向 ContextMenuStrip 添加菜单项</span><span class="sxs-lookup"><span data-stu-id="d8af6-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="d8af6-103">可以将一个菜单项或多个项添加到的一次<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="d8af6-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="d8af6-104">若要向 ContextMenuStrip 添加一个菜单项</span><span class="sxs-lookup"><span data-stu-id="d8af6-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="d8af6-105">使用<xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>方法将添加到的一个菜单项<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="d8af6-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="d8af6-106">若要向 ContextMenuStrip 添加多个菜单项</span><span class="sxs-lookup"><span data-stu-id="d8af6-106">To add several menu items to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="d8af6-107">使用<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A>方法将添加到多个菜单项<xref:System.Windows.Forms.ContextMenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="d8af6-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8af6-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8af6-108">See Also</span></span>  
 [<span data-ttu-id="d8af6-109">ContextMenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="d8af6-109">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
