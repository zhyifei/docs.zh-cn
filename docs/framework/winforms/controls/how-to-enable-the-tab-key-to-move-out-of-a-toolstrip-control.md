---
title: 如何：启用 TAB 键能够移出 ToolStrip 控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: a98c8a54389daa898c877a08f8cc2cae46a11da9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663060"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>如何：启用 TAB 键能够移出 ToolStrip 控件
使用以下过程以使用户能够按 TAB 键移动共<xref:System.Windows.Forms.ToolStrip>到下一个控件的 tab 键顺序。  
  
 <xref:System.Windows.Forms.ToolStrip>接受 TAB 键和箭头键选择项中的第一个按<xref:System.Windows.Forms.ToolStrip>。 当用户在第二次按 TAB 键时下, 一个控件，用户会在 tab 键顺序中。  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>若要使用户能够按 TAB 键能够移出 ToolStrip 到下一个控件  
  
-   设置<xref:System.Windows.Forms.ToolStrip.TabStop%2A>的属性<xref:System.Windows.Forms.ToolStrip>到`true`。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
