---
title: 如何：设置自动菜单合并为 MDI 应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
ms.openlocfilehash: 3aeaf9ee4818b6689905c10d2bd46fc887609c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549819"
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="0b93e-102">如何：设置自动菜单合并为 MDI 应用程序</span><span class="sxs-lookup"><span data-stu-id="0b93e-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="0b93e-103">以下过程提供的基本步骤用于设置在多文档界面 (MDI) 应用程序中使用自动合并<xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="0b93e-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="0b93e-104">若要设置自动菜单合并</span><span class="sxs-lookup"><span data-stu-id="0b93e-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="0b93e-105">创建 MDI 父窗体通过设置其<xref:System.Windows.Forms.Form.IsMdiContainer%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="0b93e-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="0b93e-106">添加<xref:System.Windows.Forms.MenuStrip>到 MDI 父，设置其<xref:System.Windows.Forms.Form.MainMenuStrip%2A>属性设置为的<xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="0b93e-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="0b93e-107">创建 MDI 子窗体，并设置其<xref:System.Windows.Forms.Form.MdiParent%2A>属性设置为父窗体的名称。</span><span class="sxs-lookup"><span data-stu-id="0b93e-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="0b93e-108">添加<xref:System.Windows.Forms.MenuStrip>到 MDI 子窗体。</span><span class="sxs-lookup"><span data-stu-id="0b93e-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="0b93e-109">在子窗体上设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>的属性<xref:System.Windows.Forms.MenuStrip>到`false`。</span><span class="sxs-lookup"><span data-stu-id="0b93e-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="0b93e-110">将菜单项添加到子窗体<xref:System.Windows.Forms.MenuStrip>你想要合并到父窗体的<xref:System.Windows.Forms.MenuStrip>时激活子窗体。</span><span class="sxs-lookup"><span data-stu-id="0b93e-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="0b93e-111">使用<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A>菜单上的属性项中的子窗体<xref:System.Windows.Forms.MenuStrip>来控制如何将它们合并到父窗体。</span><span class="sxs-lookup"><span data-stu-id="0b93e-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b93e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b93e-112">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="0b93e-113">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="0b93e-113">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
