---
title: "如何：检测鼠标指针何时在 ToolStripItem 上"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 633b92bf6da837b3727001c621548fa58b230102
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>如何：检测鼠标指针何时在 ToolStripItem 上
使用以下过程来检测出何时鼠标指针位于<xref:System.Windows.Forms.ToolStripItem>。  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>若要检测指针何时在 toolstripitem  
  
-   使用<xref:System.Windows.Forms.ToolStripItem.Selected%2A>在其中的项的属性<xref:System.Windows.Forms.ToolStripItem.CanSelect%2A>是`true`。  
  
     这将阻止你无需同步<xref:System.Windows.Forms.ToolStripItem.MouseEnter>和<xref:System.Windows.Forms.ToolStripItem.MouseLeave>事件。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
