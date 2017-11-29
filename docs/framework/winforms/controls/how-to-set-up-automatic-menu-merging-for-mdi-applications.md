---
title: "如何：为 MDI 应用程序设置自动菜单合并"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- Merging [Windows Forms], automatic menu
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e99aed38ed6c3af3424c264631f0eaf27e46af7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a><span data-ttu-id="eacc3-102">如何：为 MDI 应用程序设置自动菜单合并</span><span class="sxs-lookup"><span data-stu-id="eacc3-102">How to: Set Up Automatic Menu Merging for MDI Applications</span></span>
<span data-ttu-id="eacc3-103">以下过程提供的基本步骤用于设置中包含的多文档界面 (MDI) 应用程序的自动合并<xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="eacc3-103">The following procedure gives the basic steps for setting up automatic merging in a multiple-document interface (MDI) application with <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
### <a name="to-set-up-automatic-menu-merging"></a><span data-ttu-id="eacc3-104">若要设置自动菜单合并</span><span class="sxs-lookup"><span data-stu-id="eacc3-104">To set up automatic menu merging</span></span>  
  
1.  <span data-ttu-id="eacc3-105">创建 MDI 父窗体通过设置其<xref:System.Windows.Forms.Form.IsMdiContainer%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="eacc3-105">Create the MDI parent form by setting its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="eacc3-106">添加<xref:System.Windows.Forms.MenuStrip>到 MDI 父，设置其<xref:System.Windows.Forms.Form.MainMenuStrip%2A>属性， <xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="eacc3-106">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI parent, setting its <xref:System.Windows.Forms.Form.MainMenuStrip%2A> property to that <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
3.  <span data-ttu-id="eacc3-107">创建 MDI 子窗体，并设置其<xref:System.Windows.Forms.Form.MdiParent%2A>到父窗体的名称的属性。</span><span class="sxs-lookup"><span data-stu-id="eacc3-107">Create an MDI child form, and set its <xref:System.Windows.Forms.Form.MdiParent%2A> property to the name of the parent form.</span></span>  
  
4.  <span data-ttu-id="eacc3-108">添加<xref:System.Windows.Forms.MenuStrip>到 MDI 子窗体。</span><span class="sxs-lookup"><span data-stu-id="eacc3-108">Add a <xref:System.Windows.Forms.MenuStrip> to the MDI child form.</span></span>  
  
5.  <span data-ttu-id="eacc3-109">在子窗体中，将设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>属性<xref:System.Windows.Forms.MenuStrip>到`false`。</span><span class="sxs-lookup"><span data-stu-id="eacc3-109">On the child form, set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
6.  <span data-ttu-id="eacc3-110">将菜单项添加到子窗体的<xref:System.Windows.Forms.MenuStrip>你想要合并到父窗体的<xref:System.Windows.Forms.MenuStrip>时激活子窗体。</span><span class="sxs-lookup"><span data-stu-id="eacc3-110">Add menu items to the child form's <xref:System.Windows.Forms.MenuStrip> that you want to merge into the parent form's <xref:System.Windows.Forms.MenuStrip> when the child form is activated.</span></span>  
  
7.  <span data-ttu-id="eacc3-111">使用<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A>菜单上的属性中的子窗体的项<xref:System.Windows.Forms.MenuStrip>来控制如何将它们合并到父窗体。</span><span class="sxs-lookup"><span data-stu-id="eacc3-111">Use the <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> property on the menu items in the child form's <xref:System.Windows.Forms.MenuStrip> to control how they merge into the parent form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacc3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eacc3-112">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="eacc3-113">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="eacc3-113">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
