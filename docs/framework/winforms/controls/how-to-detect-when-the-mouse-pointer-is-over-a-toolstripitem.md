---
title: 如何：检测鼠标指针何时在 ToolStripItem 上
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 15a7562efd9a86a029754610ffd9e77c372d1ac2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530492"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>如何：检测鼠标指针何时在 ToolStripItem 上
使用以下过程来检测出何时鼠标指针位于<xref:System.Windows.Forms.ToolStripItem>。  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>若要检测指针何时在 toolstripitem  
  
-   使用<xref:System.Windows.Forms.ToolStripItem.Selected%2A>在其中的项的属性<xref:System.Windows.Forms.ToolStripItem.CanSelect%2A>是`true`。  
  
     这将阻止你无需同步<xref:System.Windows.Forms.ToolStripItem.MouseEnter>和<xref:System.Windows.Forms.ToolStripItem.MouseLeave>事件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
