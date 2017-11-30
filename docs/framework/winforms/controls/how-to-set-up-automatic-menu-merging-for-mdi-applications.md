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
# <a name="how-to-set-up-automatic-menu-merging-for-mdi-applications"></a>如何：为 MDI 应用程序设置自动菜单合并
以下过程提供的基本步骤用于设置中包含的多文档界面 (MDI) 应用程序的自动合并<xref:System.Windows.Forms.MenuStrip>。  
  
### <a name="to-set-up-automatic-menu-merging"></a>若要设置自动菜单合并  
  
1.  创建 MDI 父窗体通过设置其<xref:System.Windows.Forms.Form.IsMdiContainer%2A>属性`true`。  
  
2.  添加<xref:System.Windows.Forms.MenuStrip>到 MDI 父，设置其<xref:System.Windows.Forms.Form.MainMenuStrip%2A>属性， <xref:System.Windows.Forms.MenuStrip>。  
  
3.  创建 MDI 子窗体，并设置其<xref:System.Windows.Forms.Form.MdiParent%2A>到父窗体的名称的属性。  
  
4.  添加<xref:System.Windows.Forms.MenuStrip>到 MDI 子窗体。  
  
5.  在子窗体中，将设置<xref:System.Windows.Forms.ToolStripItem.Visible%2A>属性<xref:System.Windows.Forms.MenuStrip>到`false`。  
  
6.  将菜单项添加到子窗体的<xref:System.Windows.Forms.MenuStrip>你想要合并到父窗体的<xref:System.Windows.Forms.MenuStrip>时激活子窗体。  
  
7.  使用<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A>菜单上的属性中的子窗体的项<xref:System.Windows.Forms.MenuStrip>来控制如何将它们合并到父窗体。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [MenuStrip 控件概述](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
